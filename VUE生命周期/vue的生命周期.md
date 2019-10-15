# VUE 的生命周期
    vue的生命周期也就是vue对象的生命周期
## beforeCreate()创建前
    
## created()创建后

## beforeMount()挂载前

## mounted()挂载后

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

直接执行生命周期，会打印出前4个，也就是说会打印前4个周期函数；如果没有el(元素实例)，则只会执行beforeCreate()和created()两个周期函数

![lifecycle.png](0)