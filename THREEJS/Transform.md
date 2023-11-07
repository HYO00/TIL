### position (위치)

THREE.Vector3 객체로 나타내며, X, Y 및 Z 좌표를 가진다. 

mesh.position.set(x, y, z)를 사용하여 객체의 위치를 설정

### scale (크기)

THREE.Vector3 객체로 나타내며, X, Y 및 Z 축을 따라 크기를 지정

mesh.scale.set(scaleX, scaleY, scaleZ)를 사용하여 객체의 크기를 조정

### rotation (회전)

객체를 X, Y 및 Z 축을 따라 회전


rotation은 THREE.Euler 객체로 나타내며, 각각의 회전 축을 정의하는 순서와 각도를 지정


#### reorder? 
THREE.Euler 객체에서 사용되는 메서드로, 각 축의 회전 순서를 지정하는 데 사용
Euler 회전은 "XYZ" 순서로 정의
예를 들어, mesh.rotation.reorder('YXZ')를 호출하면 mesh.rotation이 YXZ 순서로 회전하도록 설정
