## 笔记

1. index.js 路由

原代码
```
<main>
  <Route exact path="/" component={Home} />
  <Route exact path="/about-us" component={About} />
</main>
```

调整后代码
```
<main>
  <Switch>
    <Route exact path="/" component={Home} />
    <Route exact path="/about-us" component={About} />
    <Redirect from="" to="/" />
  </Switch>
</main>
```

在网页版本 "" 和 “/” 都能正常的显示 Home 的页面，
但是，在 electron 中， 默认进入的是 "" 页面，
所以，开始时，并不会渲染 Home 组件。

这时，需要用 Switch 进行跳转。