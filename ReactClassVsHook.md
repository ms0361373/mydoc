# Class Component VS Function Component

React 目前有兩種方式寫成組件分別是 Class 或是 Functional

兩整方式的差別在於

|  特性   | Functional | class |
| -----   | ---------  | ----- |
| 生命週期 | 所有生命週期行為集成在useEffect | 有較多的生命週期行為可以操作 |
| 代碼量 | 簡潔 | 較多細部行為 |
| 類繼成 | 不需要 | 需要繼承React.Component |
| 渲染 | 直接返回Html | 需要透過render方法 |
| 速度 | 編成速度快 | 需轉編譯 |
| props的操作 | props不會被改變 | this.props會受到狀態改變而變化 |

# 生命週期  
類組件提供較多細部操作的生命週期例如 componentDidMount 、 componentDidUpdate 、 componentWillUnmount。

而Hook 將這些行為集成到 Effect 實現 Function Component 生命週期的方案  


# 用法   
useState() :

```js
    function Counter() {
        const [count , setCount] = useState(0) // 初始值為 ０
        return(<>
            // setCount 更新 count 並渲染
            Count: {count}
            // 每按一次 button prevCount ＋ 1 並 setCount
            <button onClick={() => setCount(prevCount => prevCount + 1)}>+</button>
        <>)
    }
```

useEffect() :

    function a() {
        userEffect(() => {
            // 組建渲染後執行

            return () => {
                // 組件銷毀後執行
            }
        },[dependent]) // (dependent) 值被改變時重新建立 Effect
        
        return <h1> Hello <h1>
    }

# Redux Hook
將 App 包含在 < Provider > 組件中

    const store = createStore(rootReducer);

    ReactDOM.render(
        <Provider store={store}>
            <App />
        </Provider>
    )
使用選擇器取的 Redux 儲存的數據

    function Counter() {
        // 取得 store 中 counter 數據
        const counter = userSelector(() => state.counter)
        return <div>{counter}</div>
    }
useDispatch:

    function Counter(value) {
        // 取得 store 中 counter 數據
        const counter = useDispatch()
        return (<>
            <div>{value}</div>)
            <button onClick={()=> dispatch({type: 'ACTION_TYPE'})}>
                Click
            </button>
            <>
    }
