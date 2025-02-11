## 1. root-context 수정
구글링의 결과로 characterEncoding=UTF-8을 추가해도 한글깨짐 현상은 해결되지 않음.

결국 코드내에서 데이터를 출력해봄.
``` java
public int save(BoardDTO boardDTO) {
        System.out.println(boardDTO);
        return sql.insert("Board.saveBoard", boardDTO);
    }
```
한글이 잘나온다..

## 2. Database 문제구나 하고 MySQL 접속 후 utf 설정
회사 컴퓨터다보니 윈도우 환경이었고 my.ini를 찾아 직접 수정해줌.
설치 방법에 따라 my.ini 경로가 다르다.

![Image](https://github.com/user-attachments/assets/8bce1629-60ef-4a5f-aef6-bf2a08a0c841)<br>
![Image](https://github.com/user-attachments/assets/6adde751-dad2-48b2-8bd1-883e97464ec4)

## 3. MySQL 완전히 다시시작
내 PC -> 관리 -> MySQL 다시시작


## 4. 해결
![Image](https://github.com/user-attachments/assets/caedff87-d4ed-4736-b164-8d3342127648)
