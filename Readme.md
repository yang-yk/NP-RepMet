### Introduction  
This is the codebase for the NeurIPS 2020 paper "**Restoring Negative Information in Few-Shot Object Detection**". 
The code will be continuously improved. For any questions/issues, please open an issue in this repository or email me at <yyk17@mails.tsinghua.edu.cn>.
### Requirements  
The codebase is modified on the basis of RepMet (<https://github.com/jshtok/RepMet>). It is built based on Python 2.7, MXNet 1.5.1, and CUDA 10.0.130. Other packages include matplotlib, opencv-python, PyYAML, etc. You may need to change some file paths to run the code.
### Preparing Data   
#### Dataset   
wget -c http://image-net.org/image/ILSVRC2017/ILSVRC2017_CLS-LOC.tar.gz
#### Data and Pre-trained Model
Please download the data and pre-trained model from <https://cloud.tsinghua.edu.cn/f/461fd3c8ca4f46fbbc80/?dl=1> and put it in the root directory.  
### Code execution
#### NP-RepMet Evaluation:
To reconstruct the 1-shot, 5-way experiment with the NP-RepMet from the NeurIPS paper, run  
`python fpn/few_shot_benchmark_1_shot.py --test_name=RepMet_inloc  --Nshot=1 --Nway=5 --Nquery_cat=10 --Nepisodes=500` 
 
To reconstruct the 5-shot, 5-way experiment with the NP-RepMet from the NeurIPS paper, run  
`python fpn/few_shot_benchmark_5_shot.py --test_name=RepMet_inloc  --Nshot=5 --Nway=5 --Nquery_cat=10 --Nepisodes=500`
#### NP-RepMet Traning:  
To train the model from scratch, run  
`python ./experiments/fpn_end2end_train_test.py --cfg=./experiments/cfgs/resnet_v1_101_voc0712_trainval_fpn_dcn_oneshot_end2end_ohem_8.yaml`
#### Citation
@ARTICLE{2020arXiv201011714Y,
       author = {{Yang}, Yukuan and {Wei}, Fangyun and {Shi}, Miaojing and {Li}, Guoqi},
        title = "{Restoring Negative Information in Few-Shot Object Detection}",
      journal = {arXiv e-prints},
     keywords = {Computer Science - Computer Vision and Pattern Recognition, Computer Science - Artificial Intelligence},
         year = 2020,
        month = oct,
          eid = {arXiv:2010.11714},
        pages = {arXiv:2010.11714},
archivePrefix = {arXiv},
       eprint = {2010.11714},
 primaryClass = {cs.CV},
       adsurl = {https://ui.adsabs.harvard.edu/abs/2020arXiv201011714Y},
      adsnote = {Provided by the SAO/NASA Astrophysics Data System}
}