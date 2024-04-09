### 컴포넌트

: React 어플리케이션에서 UI를 구성하는 기본 단위(최소한의 단위), 작은 단위의 코드로 이루어져 있고 각 컴포넌트는 각각의 기능을 가지고 있음 / 각 부분을 재사용 가능한 조각으로 UI를 나눈 것과 같음

- 기존의 웹 프레임워크는 MVC방식으로 분리하여 관리해 각 요소의 의존성이 높아 재활용이 어려움. 하지만 컴포넌트는 MVC의 뷰를 독립적으로 구성해 재사용할 수 있고 이를 통해 새로운 컴포넌트를 쉽게 만들 수 있음

#### 컴포넌트 구성요소

1. property(props)
   : 부모 컴포넌트에서 자식 컴포넌트에 전달되는 데이터, 프로퍼티 값은 자식 컴포넌트에서 수정할 수 없음

2. state
   : 컴포넌트의 상태를 저장하고 수정가능한 데이터

3. context
   : 부모 컴포넌트에서 생성해 모든 자식 컴포넌트에게 전달하는 데이터

- 컴포넌트는 데이터(props)를 입력받아 View(state) 상태에 따라 DOM Node를 출력하는 함수, props라는 임의의 입력을 받은 후, 화면에 어떻게 표시되는지 기술하는 React 엘리먼트를 반환

함수 컴포넌트, 클래스 컴포넌트가 있음

### 함수 컴포넌트

#### 사용하는 이유

1. Hooks : React v16이후 Hooks를 통한 state 및 LifeCycle 관리가 가능해짐. Hooks의 useState를 사용해 state를 관리할 수 있고 useEffect를 사용해 LifeCycle을 관리할 수 있다.
2. 직관적인 코드 : 자바스크립트의 함수 선언, 화살표 함수를 그대로 사용하기 때문에 개발자에게 직관적이다.
3. 메모리 자원 효율 : 클래스 컴포넌트에 비해 함수 컴포넌트가 비교적 메모리 자원을 작게 사용한다.

#### 사용 방법

- Js 함수이기 때문에 함수 컴포넌트라고 한다. props를 받아서 UI를 렌더링하고 각각의 렌더링된 엘리먼트를 반환한다.
- function으로 컴포넌트를 정의하고 return문에 JSX코드를 반환

```
import React from 'react'

function Hey(props){
	return <h1>Are you alright? {props.name}</h1>;
}

export default Component;

또는

const Hey = () => {
	return (
    	<div>
        	Hey!
        </div>
    );
}
```

### 클래스 컴포넌트

- class로 정의하고 render()함수에서 jsx코드를 반환

1. class 키워드로 클래스 컴포넌트를 생성
2. React.Component를 상속
3. render() 메소드를 필수로 사용하고 메소드 안에서 JSX를 반환
4. state, props, refs, 컴포넌트 메소드, 생명주기 메소드를 사용할 때 this로 프로퍼티를 참조하여 사용

#### 사용 방법

```
import React, {Component} from 'react'

class Hey extends React.Component {
	render() {
    	return <h1> How are you, {this.props,name} </h1>;
    }
}

export default Component;
```

#### 클래스 컴포넌트 생명주기(Lifecycle)

1. 마운팅(Mounting)

컴포넌트의 인스턴스가 생성되고 DOM에 삽입될 때 시작됨
호출되는 메소드 : constructor(), static getDerivedStateFromProps(), render(), componentDidMount()

2. 업데이트(Update)

컴포넌트가 props 또는 state의 변경으로 인해 다시 렌더링될 때 시작됨

호출되는 메소드 : static getDerivedStateFromProps(), shouldComponentUpdate(), render(), getSnapshotBeforeUpdate(), componentDidUpdate()

3. 언마운틴(Unmounting)

컴포넌트가 DOM에서 제거될 때 시작됨

호출되는 메소드 : componentWillUnmount()

### 컴포넌트 렌더링 과정

```
function Hey(props) {
	return <h1> it's me, {props.name}</h1>;
}
const root = ReactDom.createRot(document.getElementById('root'));
const element = <Hey name="Soyoon" />;
root.render(element);
```

1. <Hey name = "Soyoon" /> 엘리먼트로 root.render()를 호출함
2. {name: "Soyoon"}을 props로 하여 Hey 컴포넌트를 호출
3. Hey 컴포넌트가 < h1> it's me, Soyoon<h1/ > 엘리먼트를 반환
4. ReactDOM은 < h1>it's me, Soyoon<h1/ >엘리먼트와 일치하도록 DOM을 효율적으로 업데이트
