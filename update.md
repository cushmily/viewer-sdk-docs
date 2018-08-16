# Update Plugins

?>  This section is intended to guide developers in the Vuforia 7.2.23 release.

!>  If you don't have a need to make an Android app, you can skip this section.

## Summary

In the Viewer SDK, we used the Vuforia SDK as a bridge for Android.

Vuforia release ARKit/ARCore support in 7.2.23 to obtain more stable device fusion data and show better quality results.

Therefore, based on the compatibility of the program interface, we have upgraded the required version of Vuforia to 7.2.23 in the Viewer SDK.



## Upgrade

Here we will gradually explain how to upgrade the Vuforia version of 7.1.x to 7.2.23 or higher under OSX.



1.  First we need to have a installed Vuforia component, Unity version is above 2018.1.0.

   Check the Vuforia Augmented Reality option in the Building setting - XR settings.

   ![](https://ximmerse-1253940012.cos.ap-guangzhou.myqcloud.com/viewsdk/sdkvufoiral-buildsetting.png)

   

2.  After applying Vuforia, a Resources directory containing `Vuforia Configuration` will be generated in the project.

   ![](https://ximmerse-1253940012.cos.ap-guangzhou.myqcloud.com/viewsdk/sdkvuforia-config.png)

   

3.  Select `VuforiaConfiguration` and you will see an update prompt.

   ![](https://ximmerse-1253940012.cos.ap-guangzhou.myqcloud.com/viewsdk/sdkvuforia-update-config.png)

   

4.  Click to download the update installation package and follow the prompts to update.

!> If you are using UnityHub to install Unity OSX users, you need to be aware that the Vuforia installation package can only be installed in the UnityEditor of ~/Application/Unity. Please manually move the corresponding version Editor in Unity/Hub/ to the Unity folder, and then move back to the original directory after the installation is complete.