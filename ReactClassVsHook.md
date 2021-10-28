# Class Component VS Function Component

React 目前有兩種方式寫成組件分別是 Class 或是 Functional

兩整方式的差別在於

|  特性   | Functional | class |
| -----   | ---------  | ----- |
| 生命週期 | 所有生命週期行為集成在 useEffect | 有較多的生命週期行為可以操作 |
| 代碼量 | 簡潔 | 較多細部行為 |
| 類繼成 | 不需要 | 需要繼承 React.Component |
| 渲染 | 直接返回 html | 需要透過 render 方法 |
| 速度 | 編成速度快 | 需轉編譯 |
| props 的操作 | props 不會受到外部因素影響, 只在 function 中處理 props 狀態  | this.props 外部狀態影響, 因為 Class 的 this 一直在變化 |

## 生命週期  
    類組件提供較多細部操作的生命週期例如 componentDidMount 、 componentDidUpdate 、 componentWillUnmount。

    而 Hook 將這些行為集成到 Effect 實現 Function Component 生命週期的方案  


### 用法
   
* useState() :

    ```js
    function Counter() {
        // useState(0) 用法同 class construct 中的 this.state = { count: 初始值 }
        // count 用法同 class 中的 this.state.count
        // setCount 用法同 class 中的 this.setState({ count: 新值 })
        const [count , setCount] = useState(0) // 初始值為 ０

        // setCount 更新新的count值並渲染
        // 每按一次 button 取的舊count值(prevCount) ＋ 1 並 setCount
        return(<>
            Count: {count}
            <button onClick={() => setCount(prevCount => prevCount + 1)}>+</button>
        <>)
    }
    ```

* useEffect() :

    ```js
    function Counter() {
        //userEffect 同 class 中的 componentDidMount
        userEffect(() => {
            // 組建渲染後執行的區塊

            //return function 同 class 中的 componentWillUnmount
            return () => {
                // 組件銷毀後執行的區塊
            }
        
        // 依賴 (dependent) 在每次畫面渲染時比對前一次依賴值是否依樣
        // dependent改變後才重新執行 effect 降低效能耗損
        },[dependent])
        
        return <h1> Hello <h1>
    }
    ```
## Redux Hook
* 將 App 包含在 `<Provider>` 組件中 :

    ```js
    const store = createStore(rootReducer);

    ReactDOM.render(
        <Provider store = {store}>
            <App />
        </Provider>
    )
    ```
* 使用選擇器取的 Redux 儲存的數據 :

    ```js
    function Counter() {
        // 取得 store 中 counter 數據
        const counter = userSelector(() => state.counter)
        return <div>{counter}</div>
    }
    ```
* useDispatch :

    ```js
    function Counter(value) {
        // 透過 Dispatch 產生 dispatch方法
        const dispatch = useDispatch()

        //onClick 時使用 dispatch 發送 Action type 觸發 reducer 
        return (<>
            <div>{value}</div>)
            <button onClick={()=> dispatch({type: 'ACTION_TYPE'})}>
                Click
            </button>
            <>
    }
    ```
