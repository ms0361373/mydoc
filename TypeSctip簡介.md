# TypeScript
引入 Java 或 C# 類似的強型別概念

## 優點
1. 可以在編譯時幫助檢查語法是否打錯，或是型別對應不正確
2. 代碼可讀性不需要添加註解，閱讀時方便理解需要傳入的 parameter type 和 return type
3. 自動完成、導入

## 範例
* 型別註釋  
![js型別註釋](img/js型別註釋.png)  
![ts型別註釋](img/ts型別註釋.png)

* 靜態型別檢查  

    ```js
    // js
    function getUserName(userInfo){
        return userInfo.name;
    }
    
    // ts
    // 定義參數的 interface
    interface UserInfo {
        id:       number
        name:     string
        isExpire: boolean
    }
    function getUserName(userInfo: UserInfo): string {
        return userInfo.name;
    }
    ```
* 型別錯誤提示 :

    ![ts型別檢查](img/ts型別檢查.png)  

* 未定義屬性檢查 :  

    ![未定義屬性拋錯](img/未定義屬性拋錯.png)  

* 錯別字檢查 :  

    ![錯別字](img/錯別字.png)  


* 常數運用提升可讀性 :  
    
    ```js    
    // 未使用 Enum
    const handleUserStatus = (status) => {
        switch(status){
            case 0:
                // is online ...
                return;
            case 1:
                // is offline ...
                return;
        }
    }

    //使用 Enum 
    enum UserStatus {
        online = 0,
        offline = 1
    }

    // 增加參數可讀性
    const handleUserStatus = (status) => {
        switch(status){
            case UserStatus.online:
                // is online ...
                return;
            case UserStatus.offline:
                // is offline ...
                return;
        }
    }
    ```

* 定義可選參數 :

    ```js
    // 參數加上`?`定義可選參數，使用時可以決定傳不傳參數 
    function getUserName(userInfo?: UserInfo): string {
        return userInfo ? userInfo.name : 'default';
    }

    getUserName(); // 未傳參數返回 'default'
    ```

* 變數型別兼容 :

    ```js
    // 定義變數型別為 string or number
    let value: string | number = 'Hi'
    value = 0
    ```