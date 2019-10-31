20181401 나종우

[컴파일 환경]
Visual Studio 2017
Microsoft DirectX SDK (June 2010) // 프로젝트 속성의 Include Directory, Library Directory에 경로 설정

[코드 변경]
bool CSphere::hasIntersected(CSphere& ball)
void CSphere::hitBy(CSphere& ball)
bool CWall::hasIntersected(CSphere& ball)
void CWall::hitBy(CSphere& ball)