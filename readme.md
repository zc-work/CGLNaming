# CGLNaming
This repository contains data and code for our ICECCS 2022 paper "Combining Global and Local Representations of Source Code for Method Naming". 

###Data:
We already put the processed data in the compressed package. You can obtain the code that we parse Java code from [here](https://github.com/zc-work/java2graph)

You can also get the processed data from [google drive](https://zhoucong-my.sharepoint.com/:f:/g/personal/o_xoffice_top/ElKSjYlRsntBuLLRoP3zQbEBjjJ-i-tbyg_FiPx_GqUErg?e=diOQIm).

###Training/Testing Models:
We only provide our `CD` model code here. Other models can be easily obtained by modifying this basis.


```
$ cd scripts/DATASET_NAME
```

where, choices for DATASET_NAME are ["java"]

To train/evealuate the GTrans model, run:

```
$ bash transformer-js.sh 0 code2jdoc
```
where, 0 means GPU_ID. 

#### Running experiments on CPU/GPU/Multi-GPU
- If GPU_ID is set to -1, CPU will be used.
- If GPU_ID is set to one specific number, only one GPU will be used.
- If GPU_ID is set to multiple numbers (e.g., 0,1,2), then parallel computing will be used.

###Generated log files
While training and evaluating the models, a list of files are generated inside a `DATASET_NAME-tmp` directory. The files are as follows.
- **MODEL_NAME.mdl**
  - Model file containing the parameters of the best model.
- **MODEL_NAME.mdl.checkpoint**
  - A model checkpoint, in case if we need to restart the training.
- **MODEL_NAME.txt**
  - Log file for training.
- **MODEL_NAME.json**
  - The predictions and gold references are dumped during validation.
- **MODEL_NAME_test.txt**
  - Log file for evaluation (greedy).
- **MODEL_NAME_test.json** 
  - The predictions and gold references are dumped during evaluation (greedy).
  


### Acknowledgement
We borrowed and modified code from [NeuralCodeSum](https://github.com/wasiahmad/NeuralCodeSum), [ggnn.pytorch](https://github.com/chingyaoc/ggnn.pytorch). We would like to expresse our gratitdue for the authors of these repositeries.
