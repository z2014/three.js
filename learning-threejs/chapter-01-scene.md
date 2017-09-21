## scene(场景)

#### 1.什么是场景呢？
从我的理解来看，它是一个容器，用来承载页面上各个对象（灯光，立方体等）的容器，有点类似于我们页面中的document，有了它你才能够在页面中添加元素进去
#### 2.涉及场景的api
场景作为一个最底层的容器，api相对较少让我们来看一下他如何使用

##### (1).初始化一个场景
```
var scene = new THREE.Scene()
```
##### (2).向场景中添加元素
```
scene.add(camera)
```
##### (3).向场景中去除元素
```
scene.remove(camera)
```
##### (4).获取场景中的元素
```
scene.children
```
##### (5).根据元素name从场景中直接获取
```
scene.getObjectByName("name")
```
##### (6).对场景中的子元素进行遍历
```
scene.traverse(callback)//对场景中的每一个子元素都会执行一遍callback（参数是obj)
```
##### (7).雾化效果
```
scene.fog = new THREE.Fog(white, 0.015, 100)//雾化呈线性，参数分别为颜色，近距离，远距离
scene.fog = new THREE.FogExp2(white, 0.01)／／雾化呈指数增长，参数分别为颜色，浓度
```
##### (8).场景中所有物体的材质(本身每个元素都会有自己的材质，当设置该属性后，场景中所有材质都变成一样的)
```
scene.overrideMaterial = new THREE.MeshLambertMaterial({color:white})
```

对于场景这个概念的理解，主要在于它是一个容器，它本身是一个对象树，如果子对象还有对象，那么方法6还会继续向下遍历