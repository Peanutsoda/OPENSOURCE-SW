# 오픈소스SW 리눅스 명령어 조사 과제

## 1. top
> 시스템의 프로세스/메모리 사용 상태를 5초의 간격으로 업데이트하여 출력하는 명령어

`top [option]`

#### top 명령어의 주요 option
- -b : 배치모드로 정보를 출력한다. 실시간 상화 대화형모드로 정보를 화면에 일렬로 출력한다.
- -d delay : 지정한 시간(delay 초)의 간격으로 정보를 업데이트하여 출력한다.
- -i idle : 토글값이 off일 때, idle 프로세스나 좀비 프로세스 정보를 출력하지 않는다.
- -n num : 지정한 시간(num)만큼 업데이트 정보를 출력한다.
- -p pid : 지정한 프로세스 ID(pid)의 정보만을 출력한다.
- -q : 시간의 간격 없이 계속하여 업데이트 정보를 출력한다.
- -s : 몇 개의 대화식 명령을 비활성화한다.
- -S : 누적된 정보를 출력한다.


## 2. ps
> 프로세스의 현재 상태를 출력하는 명령어

`ps [option]`

#### ps 명령어의 주요 option
- -e : 시스템의 모든 프로세스를 표시한다.
- -f : 전체 형식으로 프로세스 정보를 표시한다.
- -u  [user name] : 지정된 사용자의 프로세스를 표시한다.
- -p [process ID] : 지정된 프로세스 ID의 프로세스를 표시한다.
- -l : 긴 형식으로 프로세스를 표시한다.
- -a : 터미널과 연관된 프로세스와 다른 사용자의 프로세스를 표시한다.
- -x : 터미널과 연관되지 않은 프로세스도 포함하여 표시한다.

#### ps 명령어의 상태 코드
> ps 명령어를 쓰면 프로세스의 상태를 나타는 코드가 같이 나타단다. 
- R (Running): 프로세스가 실행 중이거나 실행을 위해 준비되어 있다.
- S (Sleeping): 프로세스가 대기 상태에 있으며, 특정 이벤트나 조건이 발생할 때까지 활성화되지 않는다.
- T (Stopped): 프로세스가 중지되었거나 트레이스/디버그 중인 상태
- Z (Zombie): 프로세스가 종료되었지만, 부모 프로세스에 의해 아직 회수되지 않은 상태.
- D (Uninterruptible Sleep): 프로세스가 디스크 입출력과 같은 시스템 활동에 의해 대기 상태에 있으며, interrupt 할 수 없는 상태
<img src = "https://github.com/Peanutsoda/OPENSOURCE-SW/assets/156788371/dada647f-afc9-4923-962a-39830b296a36" width = "80%">

## 3. jobs
> 현재 쉘에서 실행 중인 작업들의 목록을 보여주는 명령어

`jobs [option]`

#### jobs 명령어의 주요 option
- -j : 작업 번호를 지정하여 해당 작업의 상태를 확인할 수 있다.
> MacOS에서는 -j 옵션이 없다.
- -l : 작업 상세 정보(작업 번호, 프로세스 ID, 상태, 시작 시간 등)를 출력한다.
- -p : 작업에 할당된 프로세스 ID를 출력한다.
- -s : 모든 작업의 상태를 출력합니다.
- -r : 현재 중지된 작업을 다시 시작한다.
  
`ex) jobs -r %1`
> 1번 작업이 다시 시작된다.

## 4. kill
> 프로세스를 종료하는 명령어

`kill [option] <process ID>`

#### kill 명령어의 주요 option
- -s <signal> : 특정 시그널(signal)을 사용하여 프로세스를 종료한다.
- -l, --list : 지원되는 시그널(signal) 목록을 출력한다.
- -a, --all : 현재 사용자에 속한 모든 프로세스를 종료한다.
- -q, --queue : 프로세스에 시그널을 보내는 대신 시그널을 대기열에 추가한다.

> kill 명령어는 간단하고 빠르게 프로세스를 종료할 수 있지만
>
> 잘못 사용하면 의도치 않은 프로세스 종료될 수 있고, 데이터 손실 등의 문제가 발생할 수 있다.

## 참고 자료
<https://terms.naver.com/entry.naver?docId=4125861&cid=59321&categoryId=59321>

<https://terms.naver.com/entry.naver?docId=4125773&cid=59321&categoryId=59321>

<https://bluesharehub.com/linux-ps-command/>

<https://blog.naver.com/rfs2006/223231213559>

<https://gr-st-dev.tistory.com/210>
