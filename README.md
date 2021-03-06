# channel-challengers-example

## Summary
Channel Open Api 와 Webhook을 사용해서 간단한 소환봇을 호출하는 어플리케이션입니다.

## How to run

1. 프로젝트에 사용되는 디펜던시를 설치합니다.
```
yarn install
```
2. `packages/webhook` 폴더 내의 `.env` 파일에 open api를 사용할 수 있도록 access-key, access-secret을 추가합니다.
필요한 키값은 https://developers.channel.io/docs/what-is-open-api 를 참고하여 생성해주세요. 예시는 아래와 같습니다. (쌍따옴표를 지우지 마세요)
```
CHANNEL_ACCESS_KEY="your_access_key"
CHANNEL_ACCESS_SECRET="your_access_secret"
```

3. `package/webhook/index.ts`의 `summonTargetManagerInfo`을 적절히 수정하여 openApi 권한을 얻은 채널의 매니저 정보를 담고 있도록 변경합니다.
4. Webhook 을 쏠 수 있도록 https://developers.channel.io/docs/what-is-webhook 를 참고하여 url을 등록해둡니다. url은 나중에 수정할 수 있습니다.
5. `packages/webhook` 폴더에서 `yarn run compile`후 `yarn run start`를 실행합니다.
6. Webhook을 받기 위해서는 로컬 서버로 사용할 수 없으므로, `ngrok`이나 `heroku` 등을 사용해서 로컬 서버를 인터넷으로 서빙해주세요. 그 후 해당 url을 Channel의 Webhook에 등록합니다
7. 서버가 올바르게 떴다면, 팀챗의 공개 그룹에 @회장 이라고 보내보세요! 3번에서 수정한 매니저가 호출된다면 성공입니다.
