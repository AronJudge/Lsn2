## 换肤的思路

1. 需要知道xml到View 怎么解析的 
2. 如何拦截系统的创建流程？ setFactory2 可以拦截  
   - 可参考https://github.com/AronJudge/TextToButton
3. 拦截后怎么做？ 重写系统的创建过程的代码  
4. 收集View以及属性 每个Activity的View 及属性都需要收集
5. 创建皮肤包 -- apk  
6. 使用  只用插件的res（插件的 java、res）
   1. 系统的资源是如何加载的？ Resources、Assetmanager
   2. 通过Hook技术，创建一个Assetmanager 专门加载皮肤包的资源
   3. 通过 反射 addAssetPath 方法放入皮肤包的路径 从而得到 加载皮肤包资源的 Assetmanager 
   4. 首先通过 app的资源id --》 找到 app的资源name --》 皮肤包的资源id

## ## 换肤前

![image-20220511210144926](https://user-images.githubusercontent.com/30100887/167868573-3dd027ef-8f71-4a42-9cfa-7d319a6abda6.png)

![image-20220511210210749](https://user-images.githubusercontent.com/30100887/167868801-7fd5d230-ec6f-4509-ab52-b6b2ab8d40dd.png)


## 换肤后


![image-20220511220122237](https://user-images.githubusercontent.com/30100887/167868829-22967326-373f-4bfc-91c9-b1f9c105b454.png)

