Image Cropping Layout
=======

[![badge](https://img.shields.io/badge/android%20arsenal-crop--image--layout-brightgreen.svg)](http://android-arsenal.com/details/1/3182#)

A light-weight image cropping layout, allowing UI customization and cropping box update listener. Image and the selected area (cropping box) is scale and fit into the predefined area.

> Current Version: 1.0.5


![image-crop](https://raw.githubusercontent.com/yulu/crop-image-layout/master/doc/crop-image.gif)


Import
------

```
dependencies {
    compile 'me.littlecheesecake:croplayout:1.0.5'
    ...
}
```

Usage
-----

```java
EditPhotoView imageView = (EditPhotoView) findViewById(R.id.editable_image);
EditableImage image = new EditableImage(this, R.drawable.photo2);
image.setBox(new ScalableBox(25,180,640,880));

imageView.initView(this, image);

imageView.setOnBoxChangedListener(new OnBoxChangedListener() {
    @Override
    public void onChanged(int x1, int y1, int x2, int y2) {
        //TODO: cropping box updated 
    }
});
```

UI Customization
--------

```xml
<me.littlecheesecake.croplayout.EditPhotoView
    android:id="@+id/editable_image"
    android:layout_width="300dp"
    android:layout_height="200dp"
    android:layout_margin="20dp"
    android:background="#fff"
    crop:crop_corner_color="#45B4CA"
    crop:crop_line_color="#d7af55"
    crop:crop_shadow_color="#77ffffff"/>
```

![image_attr](https://raw.githubusercontent.com/yulu/crop-image-layout/master/doc/crop_attr.png)


Known Issue
---------

- actual cropping of the image is not implemented, but only update the selected area (cropping box)
- crop box will be reset to the full image after rotation
- image zoom-in is not supported

Developed By
------------
Yu Lu @[littlecheesecake.me](http://littlecheesecake.me)

License
-------

    Copyright 2016 Yu Lu
 
    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at
 
        http://www.apache.org/licenses/LICENSE-2.0
 
    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
