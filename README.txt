20181401 나종우


[컴파일 환경]
Visual Studio 2017
Microsoft DirectX SDK (June 2010) // 프로젝트 속성의 Include Directory, Library Directory에 경로 설정함


[컴파일 방법]
1. VirtualLego.sln을 Visual Studio 2017로 불러온다.
2. 솔루션을 빌드하고 실행한다. (Ctrl+F5)
3. 오류가 나면 프로젝트 속성 - 일반 - Windows SDK 버전을 자신의 PC에 깔린 버전으로 바꾼다.


[코드 변경]
1. bool CSphere::hasIntersected(CSphere& ball)
수학적인 공식을 사용해 공과 공 사이의 충돌 여부를 감지하여 결과를 반환하게 만들었습니다.
실수 오차로 인한 잘못된 결과를 방지하기 위해 epsilon을 사용했습니다.

2. void CSphere::hitBy(CSphere& ball)
공과 공이 충돌하고 있다면 수학적인 공식을 사용해 두 공의 속도 벡터를 변환시키도록 만들었습니다.
이때 프레임 간의 시간 간격으로 인해 충돌 위치에 오차가 있을 수 있어서, 역추적을 통해 실제 충돌 위치를 찾도록 구현했습니다.
공과 공의 충돌은 비탄성 충돌이므로, 적당한 반발 계수를 가정하여 속도가 그만큼 줄어들도록 만들었습니다.
DirectX에서 지원하고 있는 벡터 자료형과 벡터 연산 함수를 활용했습니다.

3. bool CWall::hasIntersected(CSphere& ball)
수학적인 공식을 사용해 벽과 공 사이의 충돌 여부를 감지하여 결과를 반환하게 만들었습니다.
실수 오차로 인한 잘못된 결과를 방지하기 위해 epsilon을 사용했습니다.
DirectX에서 지원하고 있는 벡터 자료형을 활용했습니다.

4. void CWall::hitBy(CSphere& ball)
벽과 공이 충돌하고 있다면, 가로 방향 벽인지 세로 방향 벽인지에 따라 구분해 공의 속도의 방향을 변환시키도록 만들었습니다.
벽과 공의 충돌은 비탄성 충돌이므로, 적당한 반발 계수를 가정하여 속도가 그만큼 줄어들도록 만들었습니다.

5. 원래 코드에서 주석 해제하라고 써있던 부분을 주석 해제하여 벽과 공의 충돌 시에 위치 보정이 되도록 만들었습니다.