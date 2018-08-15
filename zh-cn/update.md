# 插件更新

?> 此章节作用于指导开发者进行Vuforia 7.2.23版本更新。

!> 如果你没有制作Android应用的需求，你可以跳过此章节。

## 提要

在Viewer SDK中，我们使用了Vuforia SDK作为Android的桥梁。

Vuforia在7.2.23中解放了对ARKit/ARCore的支持，以获取更稳定的设备融合数据，展示出更优质的显示结果。

因此，基于程序接口的兼容性，我们在Viewer SDK中，将Vuforia的要求版本提升到了7.2.23。

## 升级

此处我们将逐步解说在OSX下如何将7.1.x的Vuforia版本升级到7.2.23以上。

1. 首先我们需要拥有一个安装好Vuforia的组件、版本在2018.1.0以上的Unity。在Building setting - XR settings中开启Vuforia Augmented Reality选项。

   ![](https://ximmerse-1253940012.cos.ap-guangzhou.myqcloud.com/viewsdk/sdkvufoiral-buildsetting.png)

2. 应用Vuforia之后，会在项目中生成一个包含Vuforia Configuration的Resources目录。![](https://ximmerse-1253940012.cos.ap-guangzhou.myqcloud.com/viewsdk/sdkvuforia-config.png)

3. 选择VuforiaConfiguration，会看到有更新提示。![](https://ximmerse-1253940012.cos.ap-guangzhou.myqcloud.com/viewsdk/sdkvuforia-update-config.png)

4. 点击下载更新安装包，根据提示更新。

5. **注意！**如果是使用UnityHub安装Unity的OSX用户，需要注意Vuforia的安装包只能安装在~/Application/Unity的UnityEditor中。请手动将Unity/Hub/内的对应版本Editor移到Unity文件夹中，安装完成后再移回原目录。
