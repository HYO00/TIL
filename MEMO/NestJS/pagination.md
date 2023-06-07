### pagination


```jsx
@Get('/notice')
  async getNoticePosts(@Query('page') page): Promise<PrismaPost[]> {
    if (page === 'all') {
      return this.postService.getAllNoticePosts();
    } else {
      return this.postService.getNoticePosts(page);
    }
  }
```

```jsx
async getNoticePosts(page: number): Promise<any> {
    if (!page) {
      throw new NotFoundException('잘못된 api 요청');
    }
    const pageSize = 10;
    const skip = (page - 1) * pageSize || 0;
    const take = pageSize;

    const [posts, total] = await Promise.all([
      this.prismaService.post.findMany({
        where: {
          board: {
            board_type: 'notice',
          },
        },
        skip,
        take,
        orderBy: {
          created_at: 'desc',
        },
      }),
      this.prismaService.post.count({
        where: {
          board: {
            board_type: 'notice',
          },
        },
      }),
    ]);
    const totalPages = Math.ceil(total / pageSize);

    return {
      page,
      pageSize,
      total,
      totalPages,
      posts,
    };
  }
```
