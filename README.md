# ReproducibleProject_housegan_Group41


This is reproducible project of group 41.

For the course Deep Learning (CS4240), we do reproducible project by tuning the architectures of the original model. We have four variant models.


The original model is from the paper: House-GAN: Relational Generative Adversarial Networks for Graph-constrained House Layout Generation, ECCV 2020 (Link: https://github.com/ennauata/housegan).





# Training these variant models:

Step 1 : Download the complete codes from original source through the following command. 
* git clone https://github.com/ennauata/housegan.git

Step 2: Replace the orginal models.py with one of the model files. Rember to rename it into models.py again.

Step 3: Download the training data from original source through the following command. 
* wget https://www.dropbox.com/sh/p707nojabzf0nhi/AACYH3oLZS-mKrt7EJwrOAJca/housegan_clean_data.npy?dl=0

Step 4: Rename the name of training data from housegan_clean_data.npy?dl=0 to train_data.npy.

Step 5: Change the path in main.py to the path of the folder containing train_data.npy. 

Step 6: Run the following command
* python main.py --n_epochs 20

# Testing trained model:

Step 1 : Download the complete codes from original source through the following command. 
* git clone https://github.com/ennauata/housegan.git

Step 2: Replace the orginal models.py with one of the model files. Rember to rename it into models.py again.

Step 3: Download the training data from original source through the following command. 
* wget https://www.dropbox.com/sh/p707nojabzf0nhi/AAAKXxezFoBF89u0SsC1FYoha/dataset_paper/train_data.npy?dl=0

Step 4: Rename the name of training data from train_data.npy?dl=0 to train_data.npy.

Step 5: Change the room_path in variation_bbs_with_target_graph_segments_suppl.py to the path of the folder containing train_data.npy and to the trained model.

Step 6: In the smae py file as step 5, add the file name of tranid model into the following variable.
* checkpoint = './checkpoints/{}_{}_{}.pth'.format(exp_name, target_set, numb_iters).

Step 7: In the smae py file as step 5, replace the orignal code
* generator.load_state_dict(torch.load(checkpoint)) 
with 
* generator.load_state_dict(torch.load(checkpoint)['model_state_dict'])

Step 8: Run * python variation_bbs_with_target_graph_segments_suppl.py








# Citation

@inproceedings{nauata2020house,
  title={House-gan: Relational generative adversarial networks for graph-constrained house layout generation},
  author={Nauata, Nelson and Chang, Kai-Hung and Cheng, Chin-Yi and Mori, Greg and Furukawa, Yasutaka},
  booktitle={European Conference on Computer Vision},
  pages={162--177},
  year={2020},
  organization={Springer}
}

# Link (Original Paper)

 https://github.com/ennauata/housegan
