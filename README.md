# vue Tutorials

### 事前準備
1. 在 vs code 內安裝插件方便開發(非必要)
    - jshint：js代碼規範檢查。
    - Beautify：一鍵美化代碼的插件。
    - Vetur：.vue文件識別插件。-Javascript(ES6) code snippets：ES6語法提示。
    - Auto Rename Tag：自動重命名標籤。標籤都是成對出現的，開始標籤修改了，結束標籤也會跟著修改。
    - Auto Close Tag：自動閉合標籤。針對一些非標準的標籤，這個插件還是很有用的。
    - vue helper：一些Vue代碼的快捷代碼。
    - vscode-icons：可選。提供了很多類型的文件夾icon，不同類型的文件夾使用不同的icon，會讓文件查找更直觀。
    - open in browser：可選。右鍵可以選擇在默認瀏覽器中打開當前網頁。

2. 開發環境
   Vue安裝和使用，vue的安裝大體上分成三種方式，第一種是通過script標籤引用的，第二種是通過npm(node package manager)來安裝，第三種是通過vue-cli命令行來安裝。作為初學者，建議直接通過第一種方式來安裝，把心思集中在vue的學習上，而不是安裝上。

   ```javascript
   # 開發環境
   <script src="https://cdn.jsdelivr.net/npm/vue"></script>
   
   # 或者是指定版本號
   <script src="https://cdn.jsdelivr.net/npm/vue@2.6.10/dist/vue.js"></script>
   
   # 或者是下載代碼保存到本地
   <script src="lib/vue.js"></script>
   
   # 生產環境，使用壓縮後的文件
   <script src="https://cdn.jsdelivr.net/npm/vue@2.6.10/dist/vue.min.js"></script>
   ```
3. 如要使用Vue-Router

    ```javascript
       # 加載最新版的
       <script src="https://unpkg.com/vue-router/dist/vue-router.js"></script>
       # 加載指定版本的
       <script src="https://unpkg.com/vue-router@3.0.7/dist/vue-router.js"></script>
       # 下載到本地
       <script src="../../lib/vue-router.js"></script>
       # 使用npm安裝
       1. npm install vue-router
       2. npm install -g vue-router //Global
    ```

### node環境配置

#### nvm安裝

`nvm（Node Version Manager）`是一個用來管理`node`版本的工具。我們之所以需要使用`node`，是因為我們需要使用`node`中的`npm(Node Package Manager)`，使用`npm`的目的是為了能夠方便的管理一些前端開發的包！`nvm`的安裝非常簡單，步驟如下：

1. 到這個鏈接下載`nvm`的安裝包：`https://github.com/coreybutler/nvm-windows/releases`。
2. 然後點擊一頓下一步，安裝即可！
3. 安裝完成後，還需要配置環境變量。在`我的電腦->属性->高級系統設置->環境變量->系統環境變量->Path`下新建一個，把`nvm`所處的路徑填入進去即可！
4. 打開`cmd`，然後輸入`nvm`，如果沒有提示沒有找不到這個命令。說明已經安裝成功！
5. `Mac`或者`Linux`安裝`nvm`請看這裡：`https://github.com/creationix/nvm`。也要記得配置環境變量。

`nvm`常用命令：

1. `nvm node_mirror [url]`：設置`nvm`的鏡像。
2. `nvm npm_mirror [url]`：設置`npm`的鏡像。

#### node安裝

安裝完`nvm`後，我們就可以通過`nvm`來安裝`node`了。這裡我們安裝`10.16.0`版本的的`node.js。

```
nvm install 10.16.0
```

如果你的網絡夠快，那以上命令在稍等片刻之後會安裝成功。如果你的網速很慢，那以上命令可能會發生超時。因為`node`的服務器地址是`https://nodejs.org/dist/`，這個域名的服務器是在國外。因此會比較慢。因此我們可以設置一下`nvm`的源。

```
nvm node_mirror https://npm.taobao.org/mirrors/node/
nvm npm_mirror https://npm.taobao.org/mirrors/npm/
```

#### npm

`npm(Node Package Manager)`在安裝`node`的時候就會自動的安裝了。當時前提條件是你需要設置當前的`node`的版本：`nvm use 10.16.0`。然後就可以使用`npm`了.

### 初始化

#### 安裝包

安裝包分為全局安裝和本地安裝。全局安裝是安裝在當前`node`環境中，在可以在cmd中當作命令使用。而本地安裝是安裝在當前項目中，只有當前這個項目能使用，並且可以通過require引用。安裝的方式只有`-g`參數的區別：

```
npm install vue   # 本地安裝
npm install vue --save   # 本地安裝，並且保存到package.json的dependice中
npm install vue --save-dev # 本地安裝，並且保存到package.json的dependice-dev中
npm install vue -g   #全局安裝
npm install -g @vue/cli  #全局安裝vue-cli
```

#### 本地安裝

1. 將安裝包放在`./node_modules`下（運行npm命令時所在的目錄），如果沒有`node_modules`目錄，會在當前執行`npm`命令的目錄下生成`node_modules`目錄。
2. 可以通過`require()`來引入本地安裝的包。

#### 全局安裝

1. 將安裝包放在`/usr/local`下或者你`node`的安裝目錄。
2. 可以直接在命令行里使用。

#### 卸載包

```
npm uninstall [package]
```

#### 更新包

```
npm update [package]
```

#### 搜索包

```
npm search [package]
```

#### 使用淘寶鏡像

`npm`的服務器在國外。那麼可以安裝一下`cnpm`，並且指定鏡像為淘寶的鏡像：

```
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

那麼以後就可以使用cnpm來安裝包了！

#### 手動安裝npm

有時候使用`nvm`安裝完`node`後，`npm`沒有跟著安裝，這時候可以到`https://github.com/npm/cli/releases`下載`6.10.1`的版本。然後下載完成後，解壓開來，放到`v10.16.0/node_modules`下，然後修改名字為`npm`，並且把`npm/bin`中的`npm`和`npm.cmd`兩個文件放到`v10.16.0`根目錄下。

### 視圖CLI

#### 目的

`vue-cli`是和`vue`進行深度組合的工具，可以快速幫我們創建`vue`項目，並且把一些腳手架相關的代碼給我們創建好。真正使用`vue`開發項目，都是用`vue-cli`來創建項目的。

#### 安裝

`Vue CLI`需要`Node.js 8.9`或更高版本(推薦`8.11.0+`)。`node`環境安裝後，直接通過`npm install -g @vue/cli`即可安裝。安裝完成後，輸入`vue --version`，如果出現了版本號，說明已經下載完成。

#### 用命令行創建項目

1. 在指定路徑下使用`vue create [项目名称]`創建項目。
2. 會讓你選擇要安裝哪些包（默認是`Babel`和`ESLint`），也可以手動選擇。
3. 如果在安裝的時候比較慢，可以在安裝的時候使用淘寶的鏈接：`vue create -r https://registry.npm.taobao.org [项目名称]`。
4. 如果實在不想在創建項目的時候都指定淘寶鏈接，可以在當前用戶目錄下，找到`.npmrc`，然後設置`registry=https://registry.npm.taobao.org`。

#### 用界面創建項目

1. 打開`cmd`，進入到你項目存儲的路徑下。然後執行`vue ui`，就會自動打開一個瀏覽器界面。
2. 按照指引進行選擇，然後一頓下一步即可創建。

#### 項目結構介紹

1. `node_modules`：本地安裝的包的文件夾。

2. `public`：項目出口文件。

3. 
   src：項目源文件：

   - `assets`：資源文件，包括字體，圖片等。
- `components`：組件文件。
   - `App.vue`：入口組件。
   - `main.js`：`webpack`在打包的時候的入口文件。
   
4. `babel.config.js`：`es*`轉低級`js`語言的配置文件。

5. `package.json`：項目包管理文件。

#### 組件定義和導入

1. 定義：組件定義跟之前的方式是一模一樣的。只不過現在模板代碼專門放到`.vue`的`template`標籤中，所以不再需要在定義組件的時候傳入`template`參數。另外，因為需要讓別的組件使用本組件，因此需要用`export default`將組件對象進行導出。
2. 導入：因為現在組件是在不同的文件中。所以如果需要引用，那麼必須進行導入。用`ES6`語法的`import XXX from XXX`。

#### 局部樣式

默認情況下在`.vue`文件中的樣式一旦寫了，那麼會變成全局的。如果只是想要在當前的組件中起作用，那麼可以在`style`中加上一個`scoped`屬性即可。示例代碼如下：

```css
<style scoped>
.info{
   background-color: red;
}
</style>
```

#### 使用`sass`語法

很多小伙伴在寫樣式代碼的時候，不喜歡用原生`css`，比較喜歡用比如`sass`或者`less`，這裡我們以`sass`為例，我們可以通過以下兩個步驟來實現：

1. 安裝`loader`：`webpack`在解析`scss`文件的時候，會去加載`sass-loader`以及`node-loader`，因此我們首先需要通過`npm`來安裝一下：

```
npm install node-sass@4.12.0 --save-dev
npm install sass-loader@7.0.3 --save-dev
```

2. 指定`sass`語言：在指定`style`的時候，添加`lang="scss"`屬性，這樣就會將`style`中的代碼識別為`scss`語法。