# imgpicker

Hello Everyone,
By using imgpicker library you can get image from your local storage of device.# imgpicker
You can pick image here with correct rotation!
You can use Camera and take and get image with correct rotation.


To use this library,

Step 1.  Add maven in allprojects Project level build.gradle file.
allprojects {
    repositories {
    .
    .
    .
    maven { url 'https://jitpack.io' }
    }
}

Step 2.  Add dependency and Sync

    implementation 'com.github.KrupeshDobariya:imgpicker:0.1.1'


Step 3. Declare and Initialize and use requestPermission method in activity oncreate in which you want to use it.


 
        FileUtils fileUtils;
        fileUtils = new FileUtils(this);
        fileUtils.requestPermission();

Step 4.
  fileUtils.deviceImagesRequest();  // This method will open Images from your device
      
Step 5.
        try {
            fileUtils.cameraRequest();  // This method will open Camera from your device
            } catch (IOException e) {
               e.printStackTrace();
            }
            
            
            
Step 6. Add this method in Activity


    @Override
    public void onActivityResult(int requestCode, int resultCode, Intent data) {
        if (requestCode == PICK_IMAGE && resultCode == Activity.RESULT_OK) {
            fileUtils.onPickImageActivityResult(img,data);   
            //It will pick image and show image
            // img is ImageView where you want show your image
            //
        } else if (resultCode == RESULT_OK && requestCode == CAMERA_REQUEST) {
            try {
                fileUtils.onCameraActivityResult(img)
                  //It will pick image and show image from camera capture
            // img is ImageView where you want show your captured image
           
                         } catch (Exception e) {
                e.printStackTrace();
            }

        }
    }


Thanks a lot!

You can check sample project!




            
      
      
      
      













