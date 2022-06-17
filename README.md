# apps-important

image taking by bitmap 

  Photo.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Intent iCamera=new Intent(MediaStore.ACTION_IMAGE_CAPTURE);
                try{
                    startActivityForResult(iCamera,CameraRequestCode);}
                catch (ActivityNotFoundException e) {
                    // display error state to the user
                }
            }
        });

    }
    private final int CameraRequestCode=100;


    @Override
    protected void onActivityResult(int requestCode, int resultCode, @Nullable Intent data) {
        super.onActivityResult(requestCode, resultCode, data);

        if(resultCode==RESULT_OK && requestCode==CameraRequestCode){
                //for camera
                Bitmap img= (Bitmap) data.getExtras().get("data");
                Profile.setImageBitmap(img);


        }
