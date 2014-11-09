<!--
This work is licensed under the Creative Commons Attribution-ShareAlike 3.0 Unported License.
To view a copy of this license, visit http://creativecommons.org/licenses/by-sa/3.0/ or send
a letter to Creative Commons, 444 Castro Street, Suite 900, Mountain View, California, 94041, USA.
-->

# 배포판 얻기

[배포판 다운로드](downloads.html)를 눌러 배포판을 다운로드 합니다.

혹은 소스로 부터 직접 빌드할 수 있다면 [github 저장소](https://github.com/vert-x/vert.x)에서 소스를 clone 합니다.
그리고 [`BUILD_README.md`](https://github.com/vert-x/vert.x/blob/master/BUILD_README.md)를 읽어보세요.

# 사전 준비

* 운영체제. Vert.x 는 Linux, OSX 혹은 Windows에서 잘 동작합니다.

* Vert.x 는 JDK 1.7.0 이상을 필요로 합니다. Oracle의 공식 배포판을 사용할 수 있고 OpenJDK 버전도 사용가능합니다. JDK 의 실행파일 디렉토리를 `PATH` 환경변수에 등록합니다.

# Vert.x 설치하기

위와 같이 준비를 마쳤다면 아래와 같이 Vert.x 를 설치할 수 있습니다.

1. 다운로드 한 배포판을 적당한 위치에 압축해제합니다.
2. Vert.x 의 `bin` 디렉토리를 `PATH` 환경변수에 추가합니다.

예를 들면

    tar -zxf ~/Downloads/vert.x-2.0.0-final.tar.gz

혹은

    unzip ~/Downloads/vert.x-2.0.0-final.tar.gz

## 버전 확인하기

올바르게 설치되었는지 확인하기 위해 `vertx version` 명령으로 버전을 출력시켜 봅시다.

    $ vertx version
    vert.x 2.0.0-final (built ...)

위와 같이 표시가 될 것입니다.

# 테스트

간단한 웹 서버를 작성하여 잘 설치되었는지 테스트 해 봅시다.

아래 코드를 텍스트 에디터로 복사하여 `server.js` 로 저장합니다.

    var vertx = require('vertx');

    vertx.createHttpServer().requestHandler(function(req) {
      req.response.end("Hello World!");
    }).listen(8080, 'localhost');

저장한 위치에서 콘솔을 열고 아래와 같이 타이핑 해 봅시다.

    vertx run server.js

브라우저를 열고 <a href="http://localhost:8080">http://localhost:8080</a>에 접속해 봅시다.

브라우저에 "Hello World!" 가 나타난다면 모든 준비를 마친 것입니다.
