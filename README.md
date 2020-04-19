# rasp-models
This contains the model definitions (WRF models and GM/RASP files).

## Pre Requisites
1. You have built the host/container and have working models from [elsewhere](https://github.com/wargoth/rasp-gm). This means you have the shell variable **$BASEDIR** set. You have also got working binaries, *NCL*, and can run without any segmentation faults or missing shared libraries. 

2. You have the region template folder structure ready for the model. If not, copy and expand the compressed archive **region.TEMPLATE.tar.gz** found in this repository and place in **$BASEDIR**. This will provide the symbolic links and folders required for output required for the various run scripts.

## Steps
To use these, do the following. In this case we are assuming it is the **EI12** model to use.

1. Change to the base directory (**$BASEDIR**) and clone the repository to the root (**$BASEDIR**) of your host.

```
git clone https://github.com/RASPWeather/rasp-models.git
```
2. Copy the EI12 model files to your base directory. For example:
```
cp -r $BASEDIR/rasp-models/EI12.tar.gz $BASEDIR
```
3. Expand the archive file.
```
tar xvfz $BASEDIR/EI12.tar.gz
```
4. Finally, check the model **README.md** file in the folder for the model (if it has one) to find out any specifics for that model. 

5. You are now done! Now go and try the model.

# Miscellaneous
## Models for Tomorrow Or Further Away
Some models have more than one **rasp.run.parameters.[model]** and have +1 or +2 on the end. These files are used to allow the model to run ahead in the future. So **+1** is tomorrow and **+2** is two days off. In this case, as an example for tomorrow, create the model as above, rename the directory the model to model+1.  As an exmaple, **UK12** becomes **UK12+1**. Then you can run a model for the next day using the tool:
```
runGM UK12+1
```
