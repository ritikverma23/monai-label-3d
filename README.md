# monai-label-3d

MONAI Label is a server-client system that facilitates interactive medical image annotation by using AI. It is an open-source and easy-to-install ecosystem that can run locally on a machine with single or multiple GPUs. Both server and client work on the same/different machine. It shares the same principles with MONAI.

## Installing Monai Label
1. pip install monailabel

2. Making Virtual Environment on Conda
   
   conda activate monai
  
3. pip install monailabel                                     (if you were getting error in starting)


### Git Checkout (developer mode)

git clone https://github.com/Project-MONAI/MONAILabel

pip install -r MONAILabel/requirements.txt

set PATH=$PATH:`pwd`/MONAILabel/monailabel/scripts

## docker
docker run --gpus all --rm -ti --ipc=host --net=host projectmonai/monailabel:latest bash

## Initiating server
### download radiology app and sample dataset
monailabel apps --download --name radiology --output apps
monailabel datasets --download --name Task09_Spleen --output datasets

### start server using radiology app with deepedit model enabled
monailabel start_server --app apps/radiology --studies datasets/Task09_Spleen/imagesTr --conf models deepedit

Now run it on local host
![image](https://user-images.githubusercontent.com/58775305/174988782-8017ca23-e11b-4d7a-ad83-c6d79d080cd8.png)

Copy the url or address of local host and now open 3D Slicer.
In 3D slicer after installing MONAILABEL in Active Learning, select Module - MONAILabel from module list.
Now plugin your address that you had copied in MONAILabel Server. your dataset of spleen will be visible after 'hitting click on Next Sample,![image](https://user-images.githubusercontent.com/58775305/174989644-b266369d-2882-4eee-bb85-f8fc306a0cfd.png)
After plugin just check on your server is it updated?![image](https://user-images.githubusercontent.com/58775305/174990384-b11eeec7-77df-43a9-8c88-4fcb51358b07.png)
it will look something like above image, After this select ROI(Region of Interest and paint it for training)
then just update the selected area and train it.


#### References
more you can see on [First](https://pypi.org/project/monailabel/),  [Second](https://github.com/Project-MONAI/MONAILabel/tree/main/plugins/slicer)
