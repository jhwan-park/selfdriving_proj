## 1. 파일 전송 방법

### 1-1. 네트워크 연결

라즈베리파이와 노트북을 동일한 Wi-Fi에 연결합니다.

### 1-2. 라즈베리파이 준비

라즈베리파이에서 SSH 기능을 활성화합니다.

라즈베리파이 터미널에서 IP 주소를 확인합니다.

```bash
hostname -I
```

파일을 저장할 폴더를 생성합니다. 이미 존재하면 그대로 사용합니다.

```bash
mkdir -p ~/project
```

### 1-3. Windows PowerShell 실행

노트북에서 Windows PowerShell을 실행합니다. 관리자 권한은 필요하지 않습니다.

현재 입력창이 다음과 같은 Windows 프롬프트인지 확인합니다.

```text
PS C:\Users\사용자이름>
```

SSH로 라즈베리파이에 접속한 상태라면 다음 명령으로 빠져나옵니다.

```bash
exit
```

### 1-4. 파일 전송

Windows PowerShell에서 다음 명령을 실행합니다.

아래 예시의 IP 주소와 파일 경로를 실제 환경에 맞게 변경합니다.

```powershell
scp "C:\python_practice\py_CNN\CNNtest.py" pjh@172.20.10.7:~/project/
```

- `"C:\python_practice\py_CNN\CNNtest.py"`: 노트북에 저장된 파일의 전체 경로
- `pjh`: 라즈베리파이 사용자 이름
- `172.20.10.7`: 라즈베리파이 IP 주소
- `~/project/`: 라즈베리파이 홈 폴더 안의 `project` 폴더

최초 연결 시 접속 대상 IP가 맞는지 확인하고 `yes`를 입력합니다.

비밀번호를 요청하면 라즈베리파이 계정 비밀번호를 입력합니다.
입력 중에는 글자나 별표가 표시되지 않습니다.

전송률이 `100%`로 표시되고 오류 없이 종료되면 전송이 완료된 것입니다.

> 대상 폴더에 같은 이름의 파일이 있으면 덮어씁니다.

### 1-5. 전송된 파일 확인

Windows PowerShell에서 라즈베리파이에 SSH로 접속합니다.

```powershell
ssh pjh@172.20.10.7
```

접속 후 저장 폴더로 이동하여 파일 목록을 확인합니다.

```bash
cd ~/project
ls
```

목록에 `CNNtest.py`가 있는지 확인합니다.

### 1-6. 파이썬 파일 실행

라즈베리파이에 접속한 상태에서 실행합니다.

```bash
python3 CNNtest.py
```

프로그램을 중지하려면 `Ctrl+C`를 누릅니다.

SSH 접속을 종료하려면 다음 명령을 입력합니다.

```bash
exit
```
