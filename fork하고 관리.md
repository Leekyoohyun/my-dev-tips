# 1. GitHub UI나 GH CLI로 포크 떠오기<br>
```gh repo fork HopeTail-Teamproject/HopeTail-BE --clone```<br>

```cd HopeTail-BE```<br>

# 2. origin(=내 포크), upstream(=원본) 확인<br>
```git remote -v```<br>
- origin  https://github.com/내아이디/HopeTail-BE.git (fetch)<br>
- origin  https://github.com/내아이디/HopeTail-BE.git (push)<br>

# (원하면) upstream 추가<br>
```git remote add upstream https://github.com/HopeTail-Teamproject/HopeTail-BE.git```<br>
```git fetch upstream```<br>

# 3. 로컬용 main 브랜치는 그대로 main 으로 쓰고,
개발하다가 원본 최신화하려면:
```git checkout main```<br>
```git merge upstream/main```<br>

# 4. 작업 후<br>
```git push origin main   # 내 포크에만 반영```<br>

내 포크(=origin) 에 푸시해도 원본엔 영향 없고<br>

필요할 때만 upstream 으로 원본 변경사항을 당겨올 수 있습니다.<br>

# 5. upstream으로 가져오기<br>
1. 최초 1회만<br>
```git remote add upstream https://github.com/HopeTail-Teamproject/HopeTail-BE.git```<br>

2. 업데이트할 때마다<br>
```git fetch upstream```<br>
```git checkout main```<br>
```git merge upstream/main    # 또는 git rebase upstream/main```<br>
```git push origin main```<br>

가장 간단하게는 GitHub 상에서 Fork 해 오는 방법이에요. 이렇게 하면<br>

원본 저장소를 내 계정으로 복제(fork)<br>

내 계정에 생긴 포크를 git clone<br>

이제 로컬에서 origin 은 내 포크, 필요하면 upstream 으로 원본을 추가<br>

내 포크(origin)에 푸시해도 원본 저장소에는 전혀 영향이 없어요<br>
