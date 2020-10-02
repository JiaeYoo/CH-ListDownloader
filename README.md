# Vlive List Downloader
유명한 동영상 다운로드 프로그램인 [youtube-dl]('https://github.com/ytdl-org/youtube-dl')을 이용해 여러 동영상을 동시에 다운로드 할 수 있게 도와줍니다.
<br/>
따라서 이 프로그램을 이용하려면 [youtube-dl]('https://github.com/ytdl-org/youtube-dl')이 필수적으로 요구됩니다.
<br/><br/>
***

## Changelog

### v1.1

 - 프로그램이 종료된 후 재시작되어도 이전 진행상황을 유지합니다.

### v1.2
 - windows에서 log.json이 삭제되지 않던 문제 해결.
 - ID, PW에 특수문자가 포함될 경우 escape될 수 있었던 문제 해결
 - 리스트의 데이터가 숫자가 아닌 경우에 대한 예외처리
 - 프로세스를 데몬 프로세스로 변경하여 Linux 환경에서 CTRL+C로 프로세스가 종료되지 않는 문제를 해결함.
 <br>
 
[eugenee03](https://github.com/eugenee03) 님이 기여해주셨습니다.

<br>

***

## youtube-dl 다운로드 가이드
<br/>
UNIX 시스템 유저는 이 방법으로 다운로드할 수 있습니다.

    sudo curl -L https://yt-dl.org/downloads/latest/youtube-dl -o /usr/local/bin/youtube-dl
    sudo chmod a+rx /usr/local/bin/youtube-dl
또는 이 방법으로도 다운로드할 수 있습니다.

    sudo wget https://yt-dl.org/downloads/latest/youtube-dl -O /usr/local/bin/youtube-dl
    sudo chmod a+rx /usr/local/bin/youtube-dl
Windows 시스템 유저는 [.exe 파일을](https://yt-dl.org/latest/youtube-dl.exe) 다운로드할 수 있습니다. 파일은 PATH에 등록된 경로에 있어야 하지만, `%SYSTEMROOT%\System32` 에는 두면 안됩니다.<br/><br/>
**`C:\Windows`에 두는 것을 권장합니다. 이외 경로에 배치하는 경우, 동작을 보장하지 않습니다.**
<br/>
<br/>
***
## Vlive List Downloader 다운로드 가이드
<br/>

프로젝트의 소스코드를 [직접 다운로드해]('https://github.com/') 실행합니다.<br/>
이 프로젝트는 `python 3.8.3`과 python의 패키지 `openpyxl-3.0.5` 가 사용되었습니다. 이 방법을 통해 openpyxl을 설치할 수 있습니다.

    pip install openpyxl==3.0.5

***
<br/>

## Vlive List Downloader 사용법

**Note!** 프로그램 실행 전 터미널에서 `youtube-dl --version` 을 입력해 `youtube-dl`이 정상적으로 동작하는지 확인해 주세요. 입력할 ID와 PW는 
[Vlive 프로필 설정](https://vlive.tv/my/profile) 의 `계정 설정` 에서 등록한 이메일과 패스워드여야 합니다.

<br/><br/>

### 1. 프로젝트 폴더에 위치한 `credentials.json` 파일을 문서 편집기로 열어주세요. 
<br/>

### 2. 모든 필드에 필요한 정보를 입력해주세요.

    {
    "id": "lovelyz@lovelyz8.com",
    "pw": "password",
    "list": "list.xlsx",
    "multiprocess": ""
    }

<br/>
`list`는 다운로드할 동영상 목록이 있는 파일입니다. `xlsx/xlsm/xltx/xltm` 포맷을 지원하며, 동영상 ID는 파일의 `Sheet 1`, `Column 2`에 위치해야 합니다.<br/>
`multiprocess` 필드는 동시에 작동할 youtube-dl의 수를 설정하며, 큰 값일 수록 동시에 많은 양의 동영상을 다운로드합니다. 이 필드가 공백일 경우 하나의 프로세스만 동작합니다.<br/><br/>

**Note!** `multiprocess` 값이 5 이상일 경우 로그인에 실패하는 경우가 보고되었습니다. 이 문제를 수정하기 전까진 `multiprocess`를 3 이하로 설정하는 것을 권장합니다.
<br/><br/>

### 3. 실행 파일이나 소스코드와 같은 경로에 `list.xlsx` 파일을 배치해주세요
<br/>

### 4. 프로그램을 실행해 주세요.
<br/>

소스코드가 있는 디렉토리에서 터미널에 이렇게 입력하세요.

    python main.py

***
<br/>
단기간 제작한 프로젝트라 많은 부분이 빈약합니다. PR해 부족한 부분을 채워주세요!
<br/><br/>

`jiaeyoo0521@gmail.com` 으로 언제든지 연락하실 수 있습니다.
