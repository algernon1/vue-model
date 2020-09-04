# vue-model
1.安装axios插件
cnpm i axios --save

2.安装vant插件
cnpm i vant --save

3.安装lib-flexible插件  自适应布局
cnpm i lib-flexible

4.安装sass-loader,node-sass编译插件  适配布局
cnpm i sass-loader --save-dev   版本过高可能报错this.getResolve is not a function
cnpm i node-sass --save-dev


5.安装postcss-pxtorem插件  适配布局
cnpm i postcss-pxtorem --save-dev


//添加resetPage指令，防止input失焦界面下方留白
Vue.directive('resetPage', {
  inserted: function(el) {
    // 监听键盘收起事件
    document.body.addEventListener('focusout', () => {
      if (/(iPhone|iPad|iPod|iOS)/i.test(navigator.userAgent)) {
        // 软键盘收起的事件处理
        setTimeout(() => {
          const scrollHeight =
            document.documentElement.scrollTop || document.body.scrollTop || 0
          window.scrollTo(0, Math.max(scrollHeight - 1, 0))
        }, 100)
      }
    })
  }
})