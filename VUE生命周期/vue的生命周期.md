# VUE 的生命周期
    vue的生命周期也就是vue对象的生命周期
## beforeCreate()创建前
**gf**:在实例初始化之后，数据观测 (data observer) 和 event/watcher 事件配置之前被调用。
**ps**:打印$el的结果：undefined；
不要在这里进行修改数据等
## created()创建后
    打印$el的结果：undefined；
    最早也要在这里进行修改数据
    在这个函数后，会判断el是否挂载在实例上，如果没有，则需要等待我们调用vm.$mount(el)这个方法来进行挂载；
    之后再判断是否有template组件，如果有，则会调用 render 函数；render就是template组件；它是在beforeMount()和mounted()之间执行；
## beforeMount()挂载前
    打印$el的结果：<div id="root"></div>
## mounted()挂载后
    打印$el的结果：<div>0</div>
## beforeUpdate()更新前
    数据更新才会触发
## updated()更新后
    数据更新才会执行
## activated()
    和keep-alive有关
## deactivated()
    和keep-alive有关
## beforeDestroy()销毁前

## destroyed()销毁后

直接执行生命周期，会打印出前4个，也就是说会打印前4个周期函数；如果没有el(元素实例)，则只会执行beforeCreate()和created()两个周期函数。

在beforeCreate()和created()生命周期内是无法进行DOM操作的，因为拿不到节点；

mounted()挂载后 这个函数后可以进行操作
前四个周期函数，只会被调用一次

renderError () {
  ‘在开发时，会被调用，打包上线后，不会被调用，render函数报错的时候会报错，本组件的render函数出错才会报错，不受其他组件影响，例如父子组件里，就不会受影响’
}

erroCaptured () {
  收集错误，如果在根目录写，其他子组件的错误也会收集到，就是会向上冒泡，除非，子组件阻止事件冒泡，并且正式版本也可以用
}

![lifecycle.png](0)