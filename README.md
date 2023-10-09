# 프리코스 맛보기 - 패널티 킥 게임 ⚽️

❗️코끼리끼리 팀에서 직접 만든 문제로, 우아한테크코스 프리코스의 진행 방식과 다소 차이가 있을 수 있습니다.❗️

## 🔍 진행 방식

- 미션은 **기능 요구 사항, 프로그래밍 요구 사항** 두 가지로 구성되어 있다.
- 기능을 구현하기 전에 기능 목록을 만들고, 기능 단위로 커밋 하는 방식으로 진행한다.
- 기능 요구 사항에 기재되지 않은 내용은 스스로 판단하여 구현한다.

---

## 🚀 기능 요구 사항

패널티 킥 게임은 5번 골대를 향해 공을 차서 골키퍼를 피해 공을 넣는 게임이다.

두명의 플레이어(플레이어1과 플레이어2)가 패널티 킥을 차서 더 많이 골을 넣은 플레이어가 우승한다.

- 골대를 3등분하여 왼쪽은 1, 중간은 2, 오른쪽은 3으로 한다.
- 골키퍼(컴퓨터)는 5번의 위치를 랜덤으로 선택한다. 플레이어는 컴퓨터가 생각한 위치를 피해 숫자(위치)를 입력한다.
- 플레이어1이 먼저 공을 찰 위치를 5번 입력하고, 그 다음 플레이어2가 5번 입력한다.
- 사용자가 잘못된 값을 입력한 경우 `throw`문을 사용해 예외를 발생시킨후 애플리케이션은 종료되어야 한다.

### 입출력 요구 사항

### 입력

- 1~3 사이의 숫자 5개 (숫자 사이는 공백으로 구분한다)
- 예시) 1 1 2 2 3

### 출력

- 최종 결과를 골을 넣으면 O, 골을 넣지 못하면 X를 출력한다.

```
플레이어1 : OOXXO
플레이어2 : XOXXX
```

- 최종 결과를 출력한다.

```
플레이어1이(가) 우승했습니다🎉
```

- 무승부일 경우

```
무승부입니다.
```

- 게임 시작 문구 출력

```
패널티 킥 게임을 시작합니다.
총 5번의 위치를 입력해주세요.
```

### 실행 결과 예시

```
패널티 킥 게임을 시작합니다.
총 5번의 위치를 입력해주세요.
플레이어1 : 1 3 2 2 1
플레이어2 : 2 3 1 2 3

게임 결과
플레이어1 : XOXXX
플레이어2 : OOXXO
플레이어2이(가) 우승했습니다🎉
```

---

## 🎯 프로그래밍 요구 사항

- Node.js 14 버전에서 실행 가능해야 한다. **Node.js 14에서 정상적으로 동작하지 않을 경우 0점 처리한다.**
- 프로그램 실행의 시작점은 `App.js`의 `play` 메서드이다. 아래와 같이 프로그램을 실행시킬 수 있어야 한다.

**예시**

```javascript
const app = new App();
app.play();
```

- `package.json`을 변경할 수 없고 외부 라이브러리(jQuery, Lodash 등)를 사용하지 않는다. 순수 Vanilla JS로만 구현한다.
- [JavaScript 코드 컨벤션](https://github.com/woowacourse/woowacourse-docs/tree/main/styleguide/javascript)을 지키면서 프로그래밍 한다
- 프로그램 종료 시 `process.exit()`를 호출하지 않는다.

### 라이브러리

- [MissionUtils 라이브러리](https://github.com/woowacourse-projects/javascript-mission-utils#mission-utils)에서 제공하는 `Random` 및 `Console` API를 사용하여 구현해야 한다.
  - Random 값 추출은 [MissionUtils 라이브러리](https://github.com/woowacourse-projects/javascript-mission-utils#mission-utils)의 `Random.pickNumberInRange()`를 활용한다.
  - 사용자의 값을 입력 받고 출력하기 위해서는 [MissionUtils 라이브러리](https://github.com/woowacourse-projects/javascript-mission-utils#mission-utils)에서 제공하는 `Console.readLine`, `Console.print`를 활용한다.

#### 사용 예시

```javascript
const computer = [];
while (computer.length < 3) {
  const number = MissionUtils.Random.pickNumberInRange(1, 9);
  if (!computer.includes(number)) {
    computer.push(number);
  }
}
```

---

## ✏️ 과제 진행 요구 사항

- 미션은 [javascript-penalty-kick](https://github.com/jw-r/javascript-penalty-kick) 저장소를 Fork & Clone해 시작한다.
- **기능을 구현하기 전 `docs/README.md`에 구현할 기능 목록을 정리**해 추가한다.
- **Git의 커밋 단위는 앞 단계에서 `docs/README.md`에 정리한 기능 목록 단위**로 추가한다.
  - [커밋 메시지 컨벤션](https://gist.github.com/stephenparish/9941e89d80e2bc58a153) 가이드를 참고해 커밋 메시지를 작성한다.
