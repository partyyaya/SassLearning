## SASS 知識點

### 安裝
- 1. 安裝 VSCODE
- 2. 安裝插件 Live Sass Compiler 
    - 此插件可按下右下的 watch sass 進行編譯
    - 當開始 watching 時會自動生成對應的css檔(可利用分欄功能觀看編譯後效果)
- 3. scss 與 sass 區別在於 sass 沒有括弧與分號

### 變量
- 1. 可以使用 $ 來宣告變量
    - 要放在最頂部否則編譯器讀不到變量
- 2. 可以進行加減乘除計算

### 嵌套與代碼拆分或引入
- 1. 嵌套:可以使用多層 {} 生產重複代碼
- 2. 拆分與引入
    - 創建由 _ 為開頭的scss檔案(不會被編譯)
    - 並在要引入的文件使用 @import '不含底線的檔名' 即可引入該scss文件(記得引入順序)

### Mixin混入的使用
- 1. 透過 @mixin your_mixin_name {} 將相同的代碼抽取出來
    - 可以傳變量:@mixin your_mixin_name($param) {}
    - 可以設預設值::@mixin your_mixin_name($param: 600px) {}
- 2. 透過 @include your_mixin_name 將之前聲名的mixin加入在scss區塊內
    - 可以傳變量:@include your_mixin_name($param) {}
    - 若mixin有預設值且include不傳變量則可直接使用:@include your_mixin_name

### 媒體查詢與Mixin配合使用
- 1. 透過 mixin 將 @media screen 加入到裡面
- 2. 使用 @content 取得 @include 裡面內容
- 3. 生成對應的樣式

### & 字符使用
- 會延續上一層的屬姓名進行串接
```scss
.test{
  &__item{
    color: white;
  }
}

// 編譯過後:
.test__item {
  color: white;
}
```