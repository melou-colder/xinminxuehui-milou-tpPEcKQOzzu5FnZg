
# 一.matcap材质


这个材质不会受到光照影响，但是如果图片本身有光就可以一直渲染这个图片本来的样子，用来将一个图片纹理渲染到物体上的材质


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625171.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625171.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625188.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625188.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625194.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625194.png)


代码实现


加载模型后，开启纹理渲染，并把它的材质变为这个材质，并且贴上纹理图


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625204.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625204.png)


# 二.Lambert材质


Lambert网格材质是Three.js中最基本和常用的材质之一。本文将详细介绍Lambert网格材质的定义、特点、应用以及使用方法。


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625215.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625215.png)


简单来说就是这个材质当你设置好各种贴图之后 实现凹凸不平地面等是比较好的


设置好Lambert材质后，打一个光进来，会发现是漫反射哑光的反射类似于


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625230.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625230.png)


# 三.phong材质


PHONG材质是Three.js中常用的一种材质，它是一种基于Phong光照模型的材质，可以用于实现高光和阴影效果。Phong光照模型是一种基于漫反射、镜面反射和环境反射的光照模型，可以用于模拟真实物体的光照效果。


比如涂了漆面的木材，光滑的材质


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625490.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625490.png)


设置为phone材质，在设置高光颜色就可以形成对点光源的反射


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625522.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625522.png)


设置好环境贴图后


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625545.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625545.png)


代码操作


创建光源，把一个平面设置成phone材质


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625619.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625619.png)


添加环境贴图


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625676.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625676.png)


光滑的反射就出来了


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625729.gif)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625729.gif)


## 1\.实现玻璃水晶效果


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625242.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625242.png)


加载模型，设置环境光，把这个模型改为phone材质，并且设置两个折射率


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625302.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625302.png)


envmap是环境贴图


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625325.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625325.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625342.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625342.png)


如果想要折射效果还需要把环境贴图改为折射球形，上下不一样注意


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625370.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625370.png)


当把上面的反射变为折射后，这里的反射率也变为了折射率


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625748.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625748.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625924.gif)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625924.gif)


# 四.基础材质详解


## 1\.标准网格材质


在 Three.js 中，MeshBasicMaterial 是一个用于创建基本材质的类。它能够让您快速创建不需要光照效果的几何体，并且配置非常简单，可以使用颜色、透明度和纹理等属性来自定义材质。MeshBasicMaterial 在 Three.js 中非常重要，因为它是创建简单3D图形的常用材质之一，而且渲染速度很快，能够让您的应用程序保持流畅的交互体验。如果您想要创建更复杂的3D图形，了解 MeshBasicMaterial 是非常有用的，因为它是其他更复杂材质的基础。


注意：标准网格材质需要设定环境贴图


这里做一个记录，系统性的介绍一下各种贴图的作用，在之前的材质也有各种贴图，但是标准是最齐全的能够达到漫反射也能镜反射


加载一个剑的模型


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625604.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625604.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625625.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625625.png)


先上环境贴图


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625505.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625505.png)


粗糙度为1，漫反射


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625947.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625947.png)


粗糙度为0，镜反射


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626151.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626151.png)


金属度为0


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626370.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626370.png)


金属度为1


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626430.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626430.png)


还原默认，先贴上贴图


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626706.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626706.png)


金属度贴图和金属度是一个相乘的关系，越大就越金属


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626174.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626174.png)法线贴图实现凹凸不平的效果


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626625.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626625.png)


凹凸贴图同理，两个只能设置一个


置换贴图可以让顶点有一个起伏的效果，上面是看起来，这个是真起来


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626803.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626803.png)


粗糙度贴图可以让其光滑


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626973.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626973.png)


注意：真实环境只需要导入进来就是这个样子，不需要一个一个贴图，只是有时候改可以了解


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626292.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626292.png)


代码实现


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626512.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626512.png)


创建环境贴图，背景一定要添加


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626366.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626366.png)


## 2\.物理网格材质


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626673.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626673.png)


物理材质就是能够在刚才标准材质的基础上新增更多的功能


**透光率**


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626798.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626798.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626110.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626110.png)


当粗糙度为0，很光滑的时候就完全透明了


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626255.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626255.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626292.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626292.png)**厚度**


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626772.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626772.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626960.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626960.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626108.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626108.png)


**折射率，反射率**


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626330.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626330.png)


**衰减颜色，距离**


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626360.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626360.png)


衰减距离越小，就越快到达衰减颜色


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626609.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626609.png)


偏红色


注意：衰减颜色最好都设置1以下不要整的


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626791.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626791.png)


**厚度贴图**


呈现一个不均匀的厚度


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626125.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626125.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626259.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626259.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625729.gif)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291625729.gif)


**清漆效果与清漆透明度**


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626406.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626406.png)


单纯设置一个清漆强度为1后


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626710.gif)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626710.gif)


清漆光滑度，1漫反射，0镜反射


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626265.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626265.png)


map就是通过纹理决定哪些地方要清漆哪些地方不要


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626281.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626281.png)


中间光滑，周围不清漆


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626313.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626313.png)


注意此时应该粗糙度为1，到时候纹理会乘以粗糙度，如果为0始终 都是光滑


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626363.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626363.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626389.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626389.png)


法线贴图


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626515.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626515.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626619.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626619.png):[wgetcloud加速器官网下载](https://longdu.org)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626679.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626679.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626891.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626891.png)


## 3\. 布料织物材料光泽效果


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626189.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626189.png)


创建一个物理材质球体


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626254.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626254.png)


设置光泽及颜色后


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626314.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626314.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626392.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626392.png)


光泽粗糙程度


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626959.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626959.png)


设置纹理贴图


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626316.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626316.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626347.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626347.png)


## 4\.肥皂泡、油滴、蝴蝶翅膀等薄膜的虹彩效应


反射出各种颜色的材质


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626448.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626448.png)


这种效果实际是有两层组成，外面一层负责反射折射


创建一个基本球体，有粗糙度，透明度，还有一层厚度


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626615.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626615.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626156.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626156.png)


设置彩虹色，反射率和彩虹色折射率


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626270.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626270.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626425.gif)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626425.gif)


薄膜厚度范围


默认


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626744.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626744.png)


设置薄膜厚度贴图


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626807.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626807.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626955.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626955.png)


## 5\.清除物体\_几何体\_材质\_纹理保证性能和内存不泄漏


比如这里不断创建一个随机材质，随机几何体的物体，不断回调自身


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626045.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626045.png)


此时cpu使用率和内存大小都在不断增加，到一定程度就会网页崩溃


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626095.gif)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626095.gif)


要优化这种情况就是


每一帧渲染完毕，render.render就是渲染的语句，就去清除掉物体几何体等


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626238.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626238.png)


## 6\.巧用物理发光属性打造逼真IPHONE产品


在很多建模软件直接导出来给到3D导入会发现有些属性发光等会缺失，这是因为两者有些内容并不兼用，所以这个时候通常是加载到three的编辑器里面，进行编辑之后，满意之后再导出到three里面进行模型加载


刚加载进来


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626256.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626256.png)


找到屏幕材质，设置好之后导出


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626906.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626906.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626095.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626095.png)


加载进来就行了


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626164.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626164.png)


## 7\.修改模型光泽效果打造逼真室内场景


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626214.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626214.png)


刚导入进来


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626670.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626670.png)


设置光泽光泽颜色


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626808.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626808.png)


毛绒效果，法线贴图


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626870.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626870.png)


控制角度


如果让用户随意去转动很容易穿帮


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626925.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626925.png)


首先设置起始位置


可以添加轨道控制器来辅助查看


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626303.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626303.png)


设置相机初始位置，以及一开始看向的角度，x轴是横向看多宽，y是看多高，要设置lookat一开始看的角度还得配合控制器


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626221.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626221.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626272.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626272.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626293.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626293.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626379.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626379.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626452.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626452.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626481.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626481.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626561.gif)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626561.gif)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626551.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626551.png)


垂直的最小角度是网上旋转，最大角度是往下旋转


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626501.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626501.png)


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626565.gif)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626565.gif)


水平左右的角度


[![](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626528.png)](https://heymar.oss-cn-chengdu.aliyuncs.com/undefined202411291626528.png)


  * [一.matcap材质](#%E4%B8%80matcap%E6%9D%90%E8%B4%A8)
* [二.Lambert材质](#%E4%BA%8Clambert%E6%9D%90%E8%B4%A8)
* [三.phong材质](#%E4%B8%89phong%E6%9D%90%E8%B4%A8)
* [1\.实现玻璃水晶效果](#tid-DKQcKm)
* [四.基础材质详解](#%E5%9B%9B%E5%9F%BA%E7%A1%80%E6%9D%90%E8%B4%A8%E8%AF%A6%E8%A7%A3)
* [1\.标准网格材质](#tid-Znap46)
* [2\.物理网格材质](#tid-KzbzkE)
* [3\. 布料织物材料光泽效果](#tid-GiF6Bi)
* [4\.肥皂泡、油滴、蝴蝶翅膀等薄膜的虹彩效应](#tid-HeHQYW)
* [5\.清除物体\_几何体\_材质\_纹理保证性能和内存不泄漏](#tid-wXiEz8)
* [6\.巧用物理发光属性打造逼真IPHONE产品](#tid-ayDA5f)
* [7\.修改模型光泽效果打造逼真室内场景](#tid-jEPb2t)

   \_\_EOF\_\_

   ![](https://github.com/heymar)Heymar  - **本文链接：** [https://github.com/heymar/p/18577025](https://github.com)
 - **关于博主：** 评论和私信会在第一时间回复。或者[直接私信](https://github.com)我。
 - **版权声明：** 本博客所有文章除特别声明外，均采用 [BY\-NC\-SA](https://github.com "BY-NC-SA") 许可协议。转载请注明出处！
 - **声援博主：** 如果您觉得文章对您有帮助，可以点击文章右下角**【[推荐](javascript:void(0);)】**一下。
     
