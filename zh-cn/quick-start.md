# 快速开始

?> 本章节致力于开发者快速上手SDK，并且搭建出可运行的场景。



## 1. 导入插件

当我们新建一个新的工程后，需要将目标版本的ViewerSDK导入到工程中，可以通过以下途径获取ViewerSDK：

- [GIT地址]("")
- [二进制地址]("")



## 2. 切换平台

切换好需要导出的平台，ViewerSDK会处理相关的脚本开关。如果是导出Android平台，请先查看之前章节，安装、更新需求的Vuforia版本。



## 3. 准备资源

### iOS（可选）

iOS如果需要使用`Image Anchor`的话，需要将项目中的xMarker打印出来，并且测量记录图片实际尺寸（xMarker使用A4纸打印实际尺寸为0.288m）。

### Android

Android的准备分为两部分：

#### Vuforia License的准备

Vuforia SDK需要申请一个免费License才能正常使用：

1. 在[Vuforia Developer Portal](https://developer.vuforia.com/)中注册一个账号，然后依次进入Develop - License Manager - Get Development Key。

2. 按步骤建立完License后，点击选择刚刚建立的License，能够获得License Key，在稍后的开发中会用到。

3. 回到Unity中，按下Command(Control) + Shift + V 打开`VuforiaConfiguration`，填入LicenseKey。至此License的准备完成。

   

####  **(可选)** Vuforia ImageTarget的准备

当你需要使用`Image Anchor`的时候，才需要准备Vuforia Image Target。

Image Target的使用也是需要Vuforia License，没有准备好License的话，按照上一步先申请License。

?> 在Viewer SDk中，已经准备好了xMarker的ImageTarget材料，如果想直接使用xMarker做`Image Anchor`，不需要额外准备。

1. 在[Vuforia Developer Portal](https://developer.vuforia.com/)登录一个账号，然后依次进入Develop - Target Manager - Add Database 进行新建数据库。

2. 选择Device类型并且输入数据库名称后，点击Create创建数据库。

3. 点击进入创建的数据库，选择Add Target。

4. 选择Single Image 类型，上传图片文件（注意只能是png或者jpg）。

   Width填实体图片真实的尺寸信息，并且为这个Target命名后点击Add增加新的图片。

   ?> 在这里识别图需要选择特征多、重复性小的图片

   添加完成Image Target后，可以Database中看到Target的Rating，评分越高的图片识别效果越好。推荐只是评分在4星以上的图片作为`Image Anchor`。

5. 添加完成后，选中需要的ImageTarget，点击Download Database进行下载。弹出来的选项框需要选择Unity Editor。

   ![](https://ximmerse-1253940012.cos.ap-guangzhou.myqcloud.com/viewsdk/sdkvuforia-databaes-download-target.png)



## 4. Ground based

`Ground based`既无图像锚点，使用识别地面平面确定物体位置的应用场景。



 1. 新建场景，删除场景中的摄像机。

	2. 选择`GameObject/Viewer SDK/1.ViewerCamera`新建一个Viewer Camera。

    如果使用Android平台，第一次新建Viewer Camera时会提示是否导入Vuforia相关资源，点击导入即可。

    ![](https://ximmerse-1253940012.cos.ap-guangzhou.myqcloud.com/viewsdk/sdkvuforia-import-assets.png)

	3. 选择`GameObject/Viewer SDK/2.PlaneManager`新建一个Plane Mannager。

	4. 选择`GameObject/3D Object/Cube`新建一个小方块。

	5. 选择场景中出现的`Content Anchor`，将小方块拖到Tracked Object上。

	6. 至此`Ground based`的应用场景设置完毕。

## 5. Image Based

`Image based`既加入图像锚点，使用图像作为物体锚点，辅助回中的应用场景。

`Image based`的设置基于`Ground based`基础之上，先按4中设置好`Ground based`的场景。



1. 选择`Content Anchor`，并且勾选image anchor。

   ![](https://ximmerse-1253940012.cos.ap-guangzhou.myqcloud.com/viewsdk/sdkcontent-stage-inspector.png)

2. 根据开发平台的不同会出现不同的内容进行设置。

   - Android

     在Android平台下，用户可以选择指定设定好的Image Target Behaviour对象，或者是手动指定Database以及ImageTarget以自动生成。

     我们在样例中选择SDK中自带的xMarker，你也可以导入之前设置的Image Target的UnityPackage。

     ![](https://ximmerse-1253940012.cos.ap-guangzhou.myqcloud.com/viewsdk/sdkcontent-anchor-android-settings.png)

   - iOS

     在iOS平台下，用户需要指定`ArReferenceImage`，我们在这里指定SDK中自带的xMarker，你也可以导入自定义的`ArReferenceImage`。

     ![](https://ximmerse-1253940012.cos.ap-guangzhou.myqcloud.com/viewsdk/sdkcontent-anchor-iOS-settings.png)

3. 自此，Image based的应用场景设置完成。