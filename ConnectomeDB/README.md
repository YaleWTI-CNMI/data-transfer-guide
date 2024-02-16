ConnectomeDB is a data management platform where users can access, explore and download the latest datasets from the Human Connectome Project.
The instruction below shows how to download HCP_1200 from ConnectomeDB to one of the YCRC clusters. 

1. If you haven't had an account from ConnectomeDB, register for a new account at [ConnectomeDB website](https://db.humanconnectome.org).
2. Once your get your account, sign in to the website.
3. If you don't have the Aspera connect plugin installed in your browser and the Aspera connect app on you PC, 
you will see a message from the ConnectomeDB homepage which reminds you about the missing software components.
Follow the instructions to install the plugin and the app.
4. Accept the "Open Access Terms" for WU-Minn HCP Data - 1200 Subjects.
5. Now you will see "Amazon S3 Access Enabled". Click the button to generate an AWS access ID and secret access key. 
6. On the cluster where you will download the datasets, configure aws with your AWS ID and access key.
```bash
$ module load awscli
$ aws configure
AWS Access Key ID [None]: #############
AWS Secret Access Key [None]: ##########################
Default region name [None]: us-east-1
Default output format [None]: 
```
Provide the access key and secret key you obtained in step 5 when prompted to do so. The region name is `us-east-1`.

7. Now you can view and download the HCP_1200 datasets
```bash
$ aws s3 ls s3://hcp-openaccess/HCP_1200/100206/MNINonLinear/Results/tfMRI_WM_LR/tfMRI_WM_LR_Atlas_MSMAll.dtseries.nii
$ aws s3 cp s3://hcp-openaccess/HCP_1200/100206/MNINonLinear/Results/tfMRI_WM_LR/tfMRI_WM_LR_Atlas_MSMAll.dtseries.nii .
```
