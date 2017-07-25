
## 微信端页面需要注意的问题

1. 首先，我们需要知晓微信端的html页面不同于手机端和pc端，一般情况下都是用html5做的。

2. 既是微信端，就要适应不同的手机尺寸，又要保证在不同手机上字体大小是不变的，我们需要加上禁止缩放的css样式。我选择把样式加在body上面。

```css

   body{
       -webkit-text-size-adjust:100%;
       -ms-text-size-adjust:100%;
   }

```

3. 还有就是一些标签的问题了，表单中最常用的input框，在ios上，点击Input框，框的背景颜色会变灰。我们需要设置高亮颜色为 #000.

```css
    input{
        -webkit-tap-heighlight-color:rgba(0,0,0,0)
    }
```

4. 同时，因为手机上总会出现各种奇怪的样式，我们需要将手机的样式去掉。

```css
   input[type="tel"],input[type="button"],input[type="data"],input[type="text"],input[type="password"]{
       -webkit-appearance:none;
   }
```

5. 我们将表单元素的手机端样式去除之后，会导致checkbox显示不出样式来，我们还需要将input[type=checkbox]时的手机选样式表现设为checkbox.

```css
   input[type="checkbox"]{
        -webkit-appearance:checkbox;
   }
```

6. 在测试微信端页面的实际显示效果时，安卓手机，一定要用微信测试，不可用手机自带浏览器，苹果手机用微信和其他浏览器均可以。在微信端测试时，可以利用微信的扫一扫，在火狐浏览器地址栏中点击右侧的二维码小图标，生成一个二维码。用微信扫一扫就可以。