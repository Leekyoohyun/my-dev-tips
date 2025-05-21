## upstream 에서 최신 커밋 가져오기<br>

```git fetch upstream```<br>
내 로컬 브랜치에 병합<br>

main 브랜치 기준이라면:<br>
```git checkout main```<br>
```git merge upstream/main```<br>

```git merge upstream/develop```<br>
충돌 해결 후<br>

```git push origin main  ```<br>
이제 원본 저장소에 새 커밋이 올라오면, 3~5 단계를 반복해서 내 리포지토리도 최신 상태로 유지할 수 있습니다.
