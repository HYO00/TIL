# CPU스케줄링 알고리즘

목표 : 스캐줄링 알고리즘을 통해 프로세스들을 스케줄링하는 실질적인 방법 학습하자! 

## CPU스케줄링 알고리즘 대표 7가지

### 1. 선입 선처리 스케줄링

FCFS (First Come First Served) 

- **준비큐에 삽입된 순서대로 처리**하는 비선점 스케줄링
- CPU를 먼저 요청한 프로세스부터 CPU할당
- 단점: 프로세스들이 CPU를 기다리는 시간이 매우 길어질수 있다. (호위효과)

### 2. 최단 작업 우선 스케줄링

SJF (Sortest Job First) 

- CPU 사용이 짧은 프로세스 먼저 실행 후 CPU 사용이 긴 프로세스는 나중에 실행
    
    ⇒ 호위효과 방지
    
- 선점형 비선점형 둘다 구현 가능 기본적으로 비선점형

### 3. 라운드 로빈 스케줄링

RR (Round Robin) 

- 선입 선처리 + 타임슬라이스 (time slice)
- 타임슬라이스: 각 프로세스가 CPU를 사용할 수 있는 시간
- 정해진 time slice 시간 동안 돌아가며 CPU를 이용하는 선점형 스케줄링
    - 큐에 삽입된 프로세스들은 순서대로 정해진 시간만큼 만 CPU이용
    - 정해진 시간 안에 프로세스가 완료되지 않았다면 다시 큐의 맨 뒤에 삽입(문맥 교환)
- 타임 슬라이스의 크기가 중요

### 4. 최소 잔여 시간 우선 스케줄링

SRT (Shortest Remainig Time) 스케줄링

- 최단 작업 우선 스케줄링 + 라운드 로빈 스케줄링
- 최단 작업 우선 스케줄링: 작업 시간이 짧은 프로세스부터 처리
- 라운드 로빈 스케줄링: 정해진 타임 슬라이스만큼 돌아가며 처리
- 정해진 시간만큼 CPU를 이용하며 다음 CPU를 사용할 프로세스로는 남은 작업 시간이 가장 적은 프로세스를 선택

### 5. 우선순위 스케줄링

- 프로세스들에 우선순위 부여, 우선순위 높은 프로세스부터 실행
- 우선순위 같다면? 프로세스들은 선입 선처리로 스케줄링
- 최단 작업 우선 스케줄링, 최소 잔여 시간 스케줄링은 넓은 의미에서 우선순위 스케줄링이라 볼수 있다.

문제점 

- 기아(starvation) 현상
- 우선순위 높은 프로세스만 계속 실행
- 우선순위 낮은 프로세는 (준비 큐에 먼저 삽입되었음에도 불구하고) 실행 연기됨

보완 

- 기아(starvation) 현상을 방지 하기 위한 에이징(aging)기법
- 오랫동안 대시한 프로세스의 우선순위를 점차 높이는 방식
- 대기 중인 프로세스의 우선순위를 높인다. 4
    - 우선순위가 낮아도 점차 우선순위가 높아진다.

### 6. 다단계 큐 스케줄링

Multilevel queue 스케줄링

- 우선순위 스케줄리의 발전된 형태
- 우선순위 별로 준비 큐를 여러 개 사용하는 스케줄링 방식
    - 우선순위가 가장 높은 큐에 있는 프로세스들 먼저 처리
    - 우선순위가 가장 높은 큐가 비면 그 다음 우선순위 큐에 있는 프로세스 처리
- 큐 별로 스케줄링을 달리 적용해 프로세를 유형별로 쉽게 처리한다.
    
    <img width="500px" src="https://user-images.githubusercontent.com/79884004/234149068-c74d84ab-6451-4a98-aab6-70cdae1e4f7f.png"/>
 
    
- 프로세스는 Q간 이동 불가
    - 우선순위가 낮은 프로세스는 지속적으로 실행 연기
    - 기아 현상 발생

### 7. 다단계 피드백 큐 스케줄링

Multilevel feddback queue 스케줄링

- 다단계 큐 스케줄링의 발전된 형태
- 큐 간의 이동이 가능한 다단계 큐 스케줄링

타임 슬라이스 동안 끝나지 못한 프로세는 낮은 우선순위로 이동 

1. 준비상태 큐를 가장 높은 우선순위 queue에 삽입 
2. 자기 차례 시 CPU 할당 받아 실행 
3. 실행이 끝나지 않았으면 다음 우선순위 queue로 이동 반복

CPU 집중 프로세스의 우선순위는 상대적으로 낮아지고 

입출력 집중 프로세의 우선순위는 상대적으로 높아진다. 

- 다단계 피드백 큐 스케줄링 에이징 기법 적용 가능

정리 

어떤 프로세스의 CPU 시간이 길면 우선순위 낮아짐 

어떤 프로세스가 낮은 우선순위 큐에 너무 오래 있으면 우선순위 높이기

CPU 스케줄링 방식의 가장 일반적인 형태이다.
