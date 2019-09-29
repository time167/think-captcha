# think-captcha

thinkphp6 验证码类库

## 安装
> composer require time167/think-captcha

## 使用
> 类库默认为应用注册了一个验证码路由规则和验证规则，可查看CaptchaService.php

### 在控制器中输出验证码
在控制器的操作方法中使用
~~~
public function captcha()
{
	return captcha();
}
~~~

### 模板里输出验证码

在模板文件中使用
~~~
<div>{:captcha_img()}</div>
~~~
或者
~~~
<div><img src="{:captcha_src()}"/></div>
~~~
> 上面两种的最终效果是一样的

### 控制器里验证

使用TP的内置验证功能即可
~~~
$this->validate($data, [
    'captcha|验证码'=>'require|captcha'
]);
~~~
或者手动验证
~~~
if(!captcha_check($captcha)){
 //验证失败
};
~~~

### 带参使用验证码，可自行查看源码