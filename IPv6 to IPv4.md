### 특정 IP 접근을 허용해달라고 하는데, IPv4로 주어짐.

계속 IP를 출력해보면 IPv6로 읽음 -> IPv4로 읽게 만들자

Run Configurations -> (x) = Arguments -> VM arguments에 ``` -Djava.net.preferIPv4Stack=true ``` 추가

![Image](https://github.com/user-attachments/assets/7d65aca9-362c-400a-b250-6b05375fb4a8)
