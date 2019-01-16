# cordova-plugin-image-picker



Thank you very much for the source support provided by Nandun (https://github.com/nanchen2251) and Banchichen (https://github.com/banchichen).

Open source is not easy, thank you. Cordova Exchange Group: 273613165



Thank you very much for the source support provided by Southern dust and Banchichen.



One supports multiple selections. The album realizes the functions of photography, preview, image compression and so on.



This is a picture selector, he can preview the selected picture. He can also take pictures.



Function



- Select pictures

- Photograph

- Preview selected pictures

Picture compression



Requirements for Installation



- Cordova Version >= 6.0.0

- Cordova-Android >= 6.0.0

- Cordova-iOS >= 4.0.0



Installation



- `cordova plugin add cordova-plugin-image-picker-pro`




Note: Android build, see [Android Notes] (#Android Notes).



Be careful: Android build, please look at it. [android Matters needing attention] (#android Matters needing attention)




# Android Video Demo

- [Click View Video (Youku)] (http://v.youku.com/v_show/id_XMjg0NDg0NDIyMA==.html)



# iOS Video Demo

- [Click View Video (Youku)] (http://v.youku.com/v_show/id_XMjg0NDg0NTU4OA==.html)



Finished product drawing



Android | iOS |

|:------------------------::::--------------------------------------------------------------------------------------------------------------

<img src=". / screenshots/android.png" width= "270px" height= "480"> <img src=". / screenshots/ios.jpg" width= "270px" height= "480"> |



Usage mode

[A rough Cordova demo] (https://github.com/giantss/ImagePickerDemo)



```javascript

ImagePicker. getPictures (function (result) {

Alert (JSON. stringify (result);

}, function (err) {

Alert (ERR);

}, {

Maximum Images Count: 9,

Width: 1920,

Height: 1440,

Quality: 100

};

` ` ` `



The results are as follows:

` ` ` `

{

"Images": [

"Path": "/ data/user/0/com.pushsoft.im2/cache/ImagePicker/152783817455118.jpg"

"Width": 720,

"Height": 1280,

"Size": 104871// file size (in bytes)

}, {

"Path": "/ data/user/0/com.pushsoft.im2/cache/ImagePicker/152783817464525.jpg"

"Width": 720,

"Height": 1280,

"Size": 109873

]

"Is Origin": false // whether or not the original graph

}

` ` ` `



To use this plug-in in ionic, you need to declare: `declare let Image Picker: any'.




Parameter implication



Configuration parameter | Parameter implication |

|:--------------------------------------------------------------------------------------------------------------------------------------------------------------

Maximum ImagesCount | Multiple Selection Limited Quantity, default 9 |

Width | Set the width of the picture to 1920 by default |

Height | Set the height of the picture to 1440 by default |

Quality | Picture quality default 80 |



Note:



- Parameters are optional and default values are used if they are not passed.

- If the width > 0 and height > 0: Android compressed graph may be larger than the original graph or the compression rate is not high (for example, 4MB, 2MB after compression), you can set quality lower, such as 50; quality parameters will be ignored under iOS;

- If width < 0 or height < 0: then the plug-in returns the compressed image, the compression logic is close to Wechat, and the appropriate resolution and compression quality are automatically selected. This method is recommended. Compression libraries use [Luban] (https://github.com/Curzibn/Luban) and [Luban-iOS] (https://github.com/GuoZhiQiang/Luban_iOS). If you encounter problems such as unclear compression, please mention issues on their projects.

- At runtime, there is a radio button "original image" on the selection interface. When selected, the returned image is the uncompressed original image.



Notes for # Android

# # Android Matters needing attention



- Remove the installed old plug-ins first



- If build reports the following error

` ` ` `

Error: resource and roid: attr/dialog Corner Radius not found

Error: resource and roid: attr/font Variation Settings not found

Error: resource and roid: attr/ttcIndex not found

` ` ` `



Use [cordova-android-support-gradle-release] (https://github.com/dpa99c/cordova-android-support-gradle-release), the Android Support library version of the plug-in unification project:

` ` ` `

Cordova plugin add cordova-android-support-gradle-release -- variable ANDROID_SUPPORT_VERSION={required version}

` ` ` `

The `{required version} `value is similar to `25. +', `26. +', `27. +'.



- If you use low-level versions of Cordova and Gradle, you will report errors that do not support `implementation'.

For Cordova 7.1.0 and below (corresponding to Cordova-Android@6.3.0 and below), please change `implementation'in `cordova-plugin-ImagePicker\ src android\ imagepicker.gradle` to `compile',

Because the lower version of Cordova-Android uses the lower version of Gradle and does not support `implementation'.



- If the build is still unsuccessful

` ` ` `

$cordova platform RM Android

` ` ` `