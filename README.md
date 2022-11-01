# Quaternion,Euler-Angles
<h2> Euler Angles</h2>
3차원 공간의 절대 좌표를 기준으로 물체의 회전을 측정하는 방식<br>
<h3>장점</h3>
- X,Y,Z 세 개의 축을 기준으로 회전하기에 직관적이고 조작이 쉽다.<br>
- 180도가 넘는 회전도 표현할 수 있다.<br>
<h3>단점</h3>
- 계산하는데 드는 비용이 크다.<br>
- 짐벌 락이 발생할 수 있다.<br>
<h4>짐벌 락(Gimbal-lock)</h4>
오일러 각은 먼저 회전한 축이 회전하지 않은 축을 함께 회전시키는데 이로 인해 두번째로 회전한 축의 결과로 첫번째 축과 세번째축이 겹칠수 있는데 이 상태를 짐벌 락이라한다.<br><br>
<h2> Quaternion</h2>
4개의 수로 이루어져있으며 각 성분은 축이나 각도를 의미하는것이 아닌 하나의 벡터와 하나의 스칼라를 의미한다.<br>
오일러 각이 회전순서에 기반하는 반면 쿼터니언은 세 축을 동시에 회전시키기에 짐벌 락 현상이 발생하지 않는다<br>
<h3>장점</h3>
- 계산하는데 드는 비용이 적다.<br>
- 짐벌 락 문제가 발생하지 않는다.<br>
<h3>단점</h3>
- 쿼터니언을 이용한 회전은 하나의 방향에서 다른 방향으로 측정되기에 180도 보다 큰 회전을 표현할 수 없다.<br>
- 직관적으로 이해하기 어렵다.<br><br>
<h2>Unity</h2>
Quaterniton.Euler(float x, float y, float z);<br>
오일러각을 쿼터니언으로 변환 시켜준다.<br><br>
Quaternion.LookRotation(Vec3 forward, Vec3 upward);<br>
두 번째 인자인 upward는 디폴트 인자가 세팅되어있으며 첫 번째 인자에 방향 벡터를 입력하면 자신의 위치 기준으로 해방 방향벡터를 바라보게한다.<br><br>
Quaternion.Slerp(Quaternion a, Quaternion b, float t);<br>
a 와 b를 정하면 t 비율만큼 회전값을 리턴해준다.<br>
주로 회전이나 방향을 보간할 때 주로 쓰인다.
Quaternion.lerp(Quaternion a, Quaternion b, float t);<br>
a 와 b를 정하면 t 비율만큼 회전값을 리턴해준다.<br>
Lerp는 선형 보간법이고 Slerp는 구면 선형 보간법이다.
