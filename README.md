* 对 lib-flexible 进行了改造（其实就加了两行代码，见commit），更简单易用。

# 原理
3.75 为设计稿宽度/100,现在所有适口都是理想视口，设备宽度/设计稿宽度 为 css 宽度 的放大倍数，根据rem 的特性，将HTML的 font-size设置为该值，又因 HTML font-size 最小为 12px，故将该倍数乘以 100。相应css 尺寸 则为设计稿内的宽度/100 rem.
# 1px 解决方案

```scss
@minxin border($width,$style,$color) {
  [data-dpr='1'] & {
    border: $width $style $color;
  }
  [data-dpr='2'] & {
    border: $width/2 $style $color;
  }
 [data-dpr='1'] & {
    border: $width/3 $style $color;
  }
}
```

font-size background-image 同理


# amfe-flexible

[Classic edition (0.3.2)](https://github.com/amfe/lib-flexible/tree/master)

## Usage

#### Install

`npm i -S amfe-flexible`

#### Import

```html
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, minimum-scale=1, user-scalable=no">
<script src="./node_modules/amfe-flexible/index.js"></script>
```

You can inline this file with [inline-source](https://npmjs.org/package/inline-source).

#### Develop

Use [postcss-adaptive](https://www.npmjs.com/package/postcss-adaptive).

## License

(The MIT License)

Copyright (c) 2016 Alibaba MFE

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
