## **🍀 로또 게임**

---

### **⭕ 주요 기능**

1. **로또 구매 금액 입력**:
    - 사용자가 로또 구매 금액 입력
    - 금액이 **1,000원 단위인지 확인**하고, 올바르지 않을 경우 예외를 발생
    - 금액이 1,000원 단위일 경우 구매 가능한 로또 개수를 계산하여 출력

2. **로또 번호 생성**:
    - 로또를 구매하면, 1부터 45 사이의 중복 없는 숫자 6개가 랜덤으로 생성되어 각 로또에 할당
    - 생성된 번호는 오름차순 정렬

3. **당첨 번호 및 보너스 번호 입력**:
    - 사용자가 쉼표(,)로 구분된 6개의 당첨 번호를 입력
    - 중복되지 않고 1부터 45 사이의 숫자인지 검증
    - 보너스 번호는 당첨 번호와 중복되지 않도록 확인

4. **당첨 결과 계산**:
    - 각 로또와 당첨 번호를 비교하여 **일치하는 번호 개수**와 **보너스 번호 일치 여부**에 따라 등수 결정
    - 매칭 결과에 따라 상금을 계산하고, 전체 상금의 합을 통해 수익률 계산

5. **결과 출력**:
    - 각 등수별 당첨된 로또 개수와 총 수익률을 계산하여 출력

---

### **⭕ 프로그램 구조 요구사항**

### **1. `Application.java`**

- 프로그램의 진입점

### **2. Controller**

- **`LottoController.java`**:
    - 로또 게임의 전체 흐름을 제어하는 컨트롤러 클래스
    - 사용자로부터 입력을 받아 모델에 전달 및 게임 진행 관리
    - 로또 구매 금액, 당첨 번호, 보너스 번호 입력을 받아 검증 후, 당첨 결과를 계산하고 View에 전달하여 출력

### **3. Model**

- **`LottoGame.java`**:
    - 로또 게임의 모델, 로또 구매와 당첨 결과 계산을 관리하는 클래스
    - 로또 리스트 관리, 당첨 번호와의 매칭 결과에 따라 각 로또의 당첨 결과 계산
- **`Lotto.java`**:
    - 로또 객체를 정의하는 클래스
    - 각 로또에 6개의 번호 부여, 번호와 보너스 번호와의 매칭 여부를 계산하는 메서드 포함
- **`Prize.java`**:
    - 로또 당첨 결과와 관련된 Enum 클래스
    - 매칭되는 번호 개수와 보너스 번호 여부에 따라 등수 관리

### **4. View**

- **`InputView.java`**:
    - 사용자와의 상호작용을 담당하는 입력 클래스
    - 로또 구매 금액, 당첨 번호, 보너스 번호를 입력받고, Controller에 전달
- **`OutputView.java`**:
    - 게임 결과를 사용자에게 보여주는 출력 클래스
    - 각 로또 번호, 당첨 결과, 최종 수익률 출력

### **5. `InputValidator.java`**

- 입력값의 유효성을 검증하는 클래스

---

### **⭕ 시스템 흐름**

1. **사용자 입력 단계**:
    - 사용자로부터 로또 구매 금액을 입력받아, 구매 가능한 로또 개수를 계산하고 표시한다.
    - 당첨 번호와 보너스 번호를 입력받고, 각 입력값에 대한 검증을 진행한다.
2. **로또 생성 및 당첨 확인 단계**:
    - 로또 번호를 생성하여 각 로또가 당첨 번호와 매칭되는 개수를 확인한다.
    - 매칭 결과에 따라 등수를 계산하고 각 등수에 해당하는 로또 개수를 집계한다.
3. **결과 출력 단계**:
    - 등수별 당첨 로또 개수와 총 수익률을 계산하여 출력한다.
---

### **⭕ 예외 상황**

- **빈 문자열 입력**
- **잘못된 금액 입력** : 1000원 단위가 아니거나 문자가 들어온 경우
- **잘못된 당첨 번호 형식 입력** : 문자 혹은 쉼표가 아닌 구분자로 입력한 경우
- **중복된 보너스 번호 입력**
- **1~45 범위 밖의 숫자 입력**
