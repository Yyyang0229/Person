# VUE 的生命周期
    vue的生命周期也就是vue对象的生命周期
## beforeCreate()创建前
**GF：** 在实例初始化之后，数据观测 (data observer) 和 event/watcher 事件配置之前被调用。

**PS：** 打印$el的结果：undefined；
不要在这里进行修改数据等
## created()创建后
**GF：** 在实例创建完成后被立即调用。在这一步，实例已完成以下的配置：数据观测 (data observer)，属性和方法的运算，watch/event 事件回调。然而，挂载阶段还没开始，$el 属性目前不可见

**PS：** 打印$el的结果：undefined；
    最早也要在这里进行修改数据
    在这个函数后，会判断el是否挂载在实例上，如果没有，则需要等待我们调用vm.$mount(el)这个方法来进行挂载；
    之后再判断是否有template组件，如果有，则会调用 render 函数；render就是template组件；它是在beforeMount()和mounted()之间执行；
## beforeMount()挂载前
**GF：** 在挂载开始之前被调用：相关的 render 函数首次被调用。
**该钩子在服务器端渲染期间不被调用。**

**PS：** 打印$el的结果：<div id="root".></div.>
## mounted()挂载后
**GF：** el 被新创建的 vm.$el 替换，并挂载到实例上去之后调用该钩子。如果 root 实例挂载了一个文档内元素，当 mounted 被调用时 vm.$el 也在文档内。

注意 mounted **不会**承诺所有的子组件也都一起被挂载。如果你希望等到整个视图都渲染完毕，可以用 vm.$nextTick 替换掉 mounted：

mounted: function () {
  this.$nextTick(function () {

    // Code that will run only after the
    // entire view has been rendered
  })
}
**该钩子在服务器端渲染期间不被调用。**
**PS：** 打印$el的结果：<div.>0</div.>
## beforeUpdate()更新前
**GF：** 数据更新时调用，发生在虚拟 DOM 打补丁之前。这里适合在更新之前访问现有的 DOM，比如手动移除已添加的事件监听器。
**该钩子在服务器端渲染期间不被调用，因为只有初次渲染会在服务端进行。**
**PS：** 数据更新才会触发
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