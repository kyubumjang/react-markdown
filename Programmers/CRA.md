# CRA

Create React App은 React로 어플리케이션을 만들 수 있는 가장 빠른 방법입니다. 웹팩을 포함한 빌드 설정을 직접 하지 않아도 되기 때문에 엄청나게 편한 방법입니다. 그래서 이 방법으로 리액트를 시작하는 경우가 많죠! 공식 문서에도 새로운 리액트 앱을 만들 때 추천하는 방법입니다.

[CRA 공식 Github](https://github.com/facebook/create-react-app#create-react-app-)를 참고해서 설치해보세요!

만들고 나면 다음과 같은 형태로 구성이 됩니다.

```markdown
my-app
├── README.md
├── node_modules
├── package.json
├── .gitignore
├── public
│ ├── favicon.ico
│ ├── index.html
│ └── manifest.json
└── src
├── App.css
├── App.js
├── App.test.js
├── index.css
├── index.js
├── logo.svg
└── serviceWorker.js
└── setupTests.js
```

아주 쉽게 리액트 앱을 만들 수 있죠?

**자 그러면 본격적으로 살펴볼까요?**

리액트 앱을 실행하게 되면 public에 있는 index.html을 통해 들어가게 됩니다. 그리고 빌드 된 JS 파일이 이 html파일에 주입되게 됩니다. 그리고 이어서 index.js는 이 리액트 앱의 시작점이라고 할 수 있습니다. 그리고 안쪽에 App이 있는데 이 App 컴포넌트가 이 리액트 앱의 가장 제일 위에 있는 최상위(root) 컴포넌트라고 할 수 있습니다.

# JSX

조금 특이한점이 이 App.js 파일은 자바스크립트 파일인데 html처럼 보이는 것이 있습니다. 이 html처럼 보이는 것은 가상 돔을 정의한 것이라고 볼 수 있습니다. 이런 포맷을 JSX라고 부릅니다.
html의 class를 jsx에서는 className으로 쓰는데 이는 js 내에서 class는 예약어이기 때문입니다.

그리고 jsx에서는 반드시 최상위 요소가 하나여야합니다. 이는 가상돔에서 컴포넌트 변화를 효율적으로 감지하기 위한 규칙입니다. 만약 여러 요소가 필요하다면 이 두 요소를 상위에서 한번 더 감싸줘야합니다. 혹은 React.Fragment`<>`를 사용할 수 있습니다.

jsx 에서는 표현식은 물론이고 조건이나 반복을 할 수도 있습니다. 표현식을 넣기 위해서는 brace`{}`로 감싸주면 됩니다. 표현식을 넣어 동적으로 동작할 수 있도록 만들어 줄 수 있습니다. 조건의 경우 `&&`을 사용해서 AND연산을 하여 조건부로 렌더링을 할 수 있습니다. 또한 삼항 연산자를 사용할 수 도 있는데 `조건? true일 경우 : false일 경우` 이런 식으로 렌더링을 해줄 수 있습니다. 반복의 경우를 살펴보면 map을 사용해서 내부에서 배열의 순회하며 렌더링을 할 수 있습니다. react에서 jsx 내에서 반복을 할 때는 꼭 key를 적어주는게 좋습니다. 왜냐하면 key가 가상돔에서 id라고 볼 수 있어서 key를 적어줘야 react에서 성능 최적화를 해줄 수 있습니다.

```javascript
import logo from './logo.svg';
import './App.css';

function App() {
	return (
		<div className='App'>
			<header className='App-header'>
				<img src={logo} className='App-logo' alt='logo' />
				<p>
					Edit <code>src/App.js</code> and save to reload.
				</p>
				<a
					className='App-link'
					href='https://reactjs.org'
					target='_blank'
					rel='noopener noreferrer'
				>
					Learn React
				</a>
			</header>
		</div>
	);
}

export default App;
```
