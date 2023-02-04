# grass-bot

- 1일 1커밋을 꿈꾸는 개발자를 위한 grass-bot

---

### Github Actions

- Github Actions는 Workflow 자동화를 위한 도구입니다.
- `PR`, `push` 등의 이벤트는 물론이며, `CI/CD`에 활용할 수 있습니다. cron으로 스케쥴을 설정해 일정 시간마다 작동하는 workflow 도 작성할 수 있습니다. 암호화된 변수는 `secrets`을 활용할 수 있습니다.

### Schedule

- 일정 시간마다, workflow가 동작하도록 합니다. cron 식을 사용하여 주기를 설정할 수 있습니다.
  - "분 시 일 월 주" (리눅스/유닉스 크론 표현식에서는 5개 필드가 사용됩니다.)
  - "0 0 \* \* \*" (매일 0시 0분)
  - "30 1 25 \* \*" (매달 25일 01시 30분)
  - "10 10-19 ? \* MON,FRI" (매주 월, 금요일 10시와 19시 사이 10분마다)

### Workflow

- respository checkout

  - [actions/checkout@v2](https://github.com/actions/checkout) 라는 패키지를 활용합니다.
  - checkout 할 레포지토리는 `{{user_id}}/{{project_name}}@{{version}}` 형태로 작성합니다. (라이브러리 레포 참고) 혹은 `${{ github.repository }}` 으로 현재 레포를 가리킬 수 있습니다.
  - token은 깃허브에서 발급받은 개인 Token을 넣어주는 자리이며, 민감한 정보이므로 `Secret`을 활용합니다.
  - setting -> secrets -> Actions 에 토큰을 Name(시크릿명) Value(토큰값) 형태로 저장하여 `${{ secrets.{SECRETNAME} }}` 으로 활용합니다.

- file add, config, commit, push worklow

  - config 부분에 본인의 github user.email 과 user.name을 작성하면... 당신은 비가 오나 눈이 오나 1일 1커밋을 하는 개발자가 되었습니다! 🤖

---

### 후기

1일 1커밋에 대한 저의 생각은 끝이 없었습니다.

단순히 초록 잔디밭을 채우기 위해 억지로 1일 1커밋을 하는 것이 무슨 의미가 있을까? 그래도 빼곡히 채워진 커밋 내역이 만족감을 준다면 그 자체로 좋은 것 아닐까?

처음에는 초록 잔디밭이 멋져 보여서 시작한 1일 1커밋이 알고리즘 공부에 대한 동기부여가 되었습니다. 하루에 한 문제씩 풀어보자는 새로운 목표로 자리잡았기 때문입니다. 장난스럽게 시작한 Grass bot 개발은 github actions 를 좀 더 잘 활용하기 위한 동기부여가 된 것 같습니다.

본인 스스로가 어떤 가치를 부여하느냐에 따라 하고 있는 일의 가치가 결정되는 것 같습니다. 1일 1커밋이 저에게는 동기부여가 된 것처럼이요. 앞으로도 제가 개발하는 서비스에서 Why를 고민하고, 가치를 개발하는 개발자로 성장할 것입니다 🥳
