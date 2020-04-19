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
   # 开发环境
   <script src="https://cdn.jsdelivr.net/npm/vue"></script>
   
   # 或者是指定版本号
   <script src="https://cdn.jsdelivr.net/npm/vue@2.6.10/dist/vue.js"></script>
   
   # 或者是下载代码保存到本地
   <script src="lib/vue.js"></script>
   
   # 生产环境，使用压缩后的文件
   <script src="https://cdn.jsdelivr.net/npm/vue@2.6.10/dist/vue.min.js"></script>
   ```
   
   

