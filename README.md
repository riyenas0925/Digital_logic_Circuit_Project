# Digital_logic_Circuit_Project

## ‘상’ 단계 (10점 만점)
* Clock : 1-bit, 10MHz 클락을 사용한다. (period=100ns)
* Up : 1-bit, 1이 입력되면 Power state가 변한다.
* On/Off : 1-bit, 1이 입력되면 시스템이 ON 되며, 0이 입력되면 시스템은 OFF 된다.
* Rotation : 1-bit, 1이 입력되면 현재 출력이 특정 주기를 가지는 신호로 변하며. 또 다시
1이 입력되면 기존 신호로 복귀한다.
* Down : 1-bit, 1이 입력되면 Power state가 변한다.
### 출력
* Power State : 3-bit, 현재의 바람세기와 회전을 의미한다.
### 동작
* State machine을 이용하여 Power state의 상태를 변경한다.
* On일 때, Up에 입력이 들어오는 횟수에 따라 미풍(001)->약풍(010)->강풍(100)이 출력된
다. (단, 강풍일 때 입력이 들어와도 강풍을 유지한다)
* Off일 때, Power state는 항상 0의 값을 가진다. 이 상태에서 Up에 1이 입력되더
라도 출력은 0을 유지한다.
* 미풍 상태에서 Rotation에 1이 입력되면 주기가 6 Clock인 신호가 생성된다.
* 약풍 상태에서 Rotation에 1이 입력되면 주기가 4 Clock인 신호가 생성된다.
* 강풍 상태에서 Rotation에 1이 입력되면 주기가 2 Clock인 신호가 생성된다.
* 특정 바람세기의 Rotation state에서 Power state가 변하면 바뀐 바람세기의 Rotation
state가 출력된다.
* Rotation에 입력 1이 한 번 더 들어오면 회전이 멈춰 주기를 갖는 신호에서 기존의 일정
한 파형으로 변경된다.
* 정지상태에서 Rotation에 1이 입력되면 아무 영향을 주지 않는다.
* Rotation, Up, Down의 입력이 동시에 들어오지 않는다.
* Down에 1이 입력되면 바람의 세기가 한 단계씩 줄어든다.
