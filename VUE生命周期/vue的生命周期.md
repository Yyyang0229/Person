# VUE 的生命周期
    vue的生命周期也就是vue对象的生命周期
## beforeCreate()创建前
    打印$el的结果：undefined；
    不要在这里进行修改数据等
## created()创建后
    打印$el的结果：undefined；
    最早也要在这里进行修改数据
    在这个函数后，会判断el是否挂载在实例上，如果没有，则需要等待我们调用vm.$mount(el)这个方法来进行挂载；
    之后再判断是否有template组件，如果有，则会调用 render f
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
在beforeCreate()和created()生命周期内是无法进行DOM操作的，因为拿不到节点；mounted()挂载后 这个函数后可以进行操作
前四个周期函数，只会被调用一次

![lifecycle.png](0)