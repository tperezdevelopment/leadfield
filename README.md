1- Description:
This pipeline was created to automate leadfield creation for individual models. The main script follows all the steps to resolve the Direct Problem of EEG. Also, the process includes Laplacian matrix estimation for its application in the solution of the Inverse Problem.

2-Parameters:
2.1-Input data structure:
The input data requires to be organized by Subjects. Each Subject will have a folder, into this folder will be a json file named jsonParams.json. The jsonParams.json contains all the input parameters to define (See 2.2 section).  
The output parameters (See 2.3 section), will be saved in the output folder that contains the result by Subjects.
2.2-Input parameters in jsonParams.json:
anatFormat: This variable specifies the format of the anatomical data. (1? Freesurfer and 2? HCP). By default option 1, freesurfer.

anatFolderName: The folder name that contains the anatomical data. This field is required.

channelFile: Path of the file that contains all the information about the channels. 

labelsChannel: Cell array with a subset of channels labels. That can be in 3 differents ways: 
              1- Declaring the cell array into the same Json file
              2- Declaring the name of the file in matlab(.mat) format saves the cell array.
	3-Or declaring the name of the file in .txt format that saves the cell array.

By default option 2, .mat file. 
             
nVertHead: Number of vertices for the scalp during the process. This field is required.

nVertCortex: Number of vertices for the cortex during the process. This field is required.

sourcespace: Space location of the sources. (1?Surface or 2?Volumen). This field is not required. By default option 1, Surface.  

typeModel: Type of model to calculate the leadfield. (1- OpenMEEG or 2-Shell sphere)



2.3-Output files:
Ke.mat: File with the Leadfield’s matrix.
Sources.mat: File with all the information about the sources.
Cortex.mat: File with the information about the individual cortex.
Le.mat: File with Laplacian’s matrix.
Channels.mat: File with the structure which contains all the information about the projected channels on the scalp.
Scalp.mat: Contains all the information about the scalp model used (Vertices and Faces).
OuterSkull.mat: Contains all the information about the outer skull model used (Vertices and Faces).
InnerSkull.mat: Contains all the information about the inner skull model used (Vertices and Faces).
Stats.mat: Contains the results of the quality control test.
Log.txt: Contains the logs.

