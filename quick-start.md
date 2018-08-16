# Quick Start

?>  This chapter is dedicated to developers getting started with the SDK and building a working scenario.



## 1. Import SDK

After we create a new project, we need to import the target version of ViewerSDK into the project. 

You can get the ViewerSDK by the following methods :

- [GIT]("")
- [Binary]("")



## 2. Switch Platform

Switch to the target platform, ViewerSDK will handle relevant scripts. 

If you are exporting the Android platform, please check the previous chapter to install and update the Vuforia version of the requirement.



## 3. Prepare Assets

### (Optional)iOS

 If you need to use `Image Anchor` in iOS, you may print the `xMarker` in the project folder and measure the actual size of the recorded image (xMarker uses A4 paper to print the actual size of 0.288m).



### Android

Android preparation is divided into two parts:

 

#### Prepare for Vuforia License

 The Vuforia SDK needs to apply for a license to use it properly:

1.  Register an account in the [Vuforia Developer Portal](https://developer.vuforia.com/) and go to Develop - License Manager - Get Development Key.

   

2. After the license is created in the following steps, click to select the license you just created to obtain the license key, which will be used in later development.

   

3. Go back to Unity and press Command(Control) + Shift + V to open `VuforiaConfiguration` and fill in the LicenseKey. 

   At this point, the preparation of the license is completed.

   

#### **(Optional)** Prepare for Vuforia ImageTarget

You need to prepare Vuforia Image Target only when you use `Image Anchor`.

Image target is also required to use the Vuforia License. 

If the license is not ready, apply for the license as described in the previous step.

?>  In Viewer SDk, xMarker's ImageTarget material is already prepared. If you want to use xMarker directly as `Image Anchor`, you can skip this.

1.  Log in to an account on the [Vuforia Developer Portal](https://developer.vuforia.com/) and go to Develop - Target Manager - Add Database to create a new database.

   

2. After selecting the Device type and entering the database name, click Create to create the database.

   

3. Click into the created database and select Add Target.

   

4.  Select the Single Image type and upload the image file (note that it can only be png or jpg).

   Width field fills in the real size information of the entity picture, and after naming this Target, click Add to add a new picture.

   

   ?>  The picture need to be uploaded here requires a picture with many features and small repeatability.

   

   After adding the `Image Target`, you can see the Target's Rating in the Database. 

   The higher the score, the better the image recognition effect. 

   It is recommended to use the image above 4 stars as `Image Anchor`.

   

5.  After adding `Image Target`, select the desired `Image Target` and click Download Database to download. 

   The option box that pops up needs to select Unity Editor.

   ![](https://ximmerse-1253940012.cos.ap-guangzhou.myqcloud.com/viewsdk/sdkvuforia-databaes-download-target.png)



## 4. Ground based

`Ground based`, ie, no image anchor, uses an scenario that identifies the ground plane to determine the position of the object.



1.  Create a new scene and delete the MainCamera in the scene.

   

2. Select `GameObject/Viewer SDK/1.ViewerCamera` to create a new Viewer Camera.

   

3. If you use the Android platform, you will be prompted to import Vuforia related resources when you first create a new Viewer Camera. Click Import.

   ![](https://ximmerse-1253940012.cos.ap-guangzhou.myqcloud.com/viewsdk/sdkvuforia-import-assets.png)

   

4.  Select `GameObject/Viewer SDK/2.PlaneManager` to create a new Plane Mannager.

   

5.  `Select GameObject/3D Object/Cube` to create a new small Cube.

   

6. Select the `Content Anchor` that appears in the scene and drag the small square onto the Tracked Object field.

   

7. At this point, the `Ground based` scene setup if finished.

## 5. Image Based

Similar to the `Ground based`, `Image based` uses `Image Anchor` as a object anchor, and assists the user to recenter.

`Image based` is based on `Ground based`, set up the `Ground based` scene first.

1.  Select `Content Anchor` and check `use image anchor`.

   ![](https://ximmerse-1253940012.cos.ap-guangzhou.myqcloud.com/viewsdk/sdkcontent-stage-inspector.png)

   

2. Different content will be set up depending on the development platform.

   - Android

     On the Android platform, the user can choose to specify the  Image Target Behaviour object, or manually set the Database and ImageTarget to generate Image Target Behaviour automatically.

     We select the xMarker that comes with the SDK in the sample. You can also import the UnityPackage of the Image Target that was previously set.

     ![](https://ximmerse-1253940012.cos.ap-guangzhou.myqcloud.com/viewsdk/sdkcontent-anchor-android-settings.png)

   - iOS

     On the iOS platform, the user needs to specify the `ArReferenceImage`.

     Here we specify the xMarker that comes with the SDK. You can also import a custom `ArReferenceImage`.

     ![](https://ximmerse-1253940012.cos.ap-guangzhou.myqcloud.com/viewsdk/sdkcontent-anchor-iOS-settings.png)

     

3.  Since then,` Image based` scene setup is complete.