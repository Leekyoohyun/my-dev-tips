## HTTP Health Check 또는 HTTP 응답 테스트<br>
HTTP 응답 테스트를 위한 명령어<br>

```curl -i http://api.hopetail.com/health```<br>
```curl -i https://api.hopetail.com/health```<br>

aws ec2에서 대상그룹, 로드밸런서가 자꾸 unhealthy가 뜨면서 서버가 튕김.<br>

이를 위해 health 컨트롤러 생성해서 경로 설정을 하고 200 을 받는거 테스트하려고 만듬<br>
