## SWAP 메모리 사용하기
gradlew 빌드하는 데 너무 많은 시간이 걸리거나, 빌드가 멈춰서 터미널 또한 멈추는 현상 발생함~<br>

aws 프리티어를 사용하면 어쩔 수 없는 문제라고 하고 Spring 자체가 메모리를 많이 쓰기 때문에 swap 메모리 설정을 해주자.

1. swap메모리 추가<br>
```$ sudo dd if=/dev/zero of=/swapMem bs=128M count=16```<br>
```$ sudo chmod 600 /swapMem```<br>

2. swap메모리를 swap 파일로 포맷<br>
  ``` $ sudo mkswap /swapMem```<br>
   
3. SWAP 메모리를 활성화<br>
 ```$ sudo swapon /swapMem```<br>
 ```$ sudo swapon -s```<br>

4. SWAP 메모리 자동 활성화(추가되어있음 서버 껐다켜도)<br>
```$ sudo vi /etc/fstab ```<br>
```# 마지막 행에 추가하기```<br>
```/swapfile swap swap defaults 0 0```<br>

5.SWAP 관련 명령어<br>
```# 메모리 삭제```<br>
```sudo rm -r swapMem```<br>
```# 메모리 비활성화```<br>
```$ sudo swapoff swapMem```<br>

```# 전체 메모리 비활성화```<br>
```$ sudo swapoff -a```<br>
