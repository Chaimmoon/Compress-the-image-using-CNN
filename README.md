# Compress-the-image-using-CNN

## How to use

The changes are in `train.py`. I change the loss function and make it possible to improve the `PSNR` and `MS-SSIM` at the same time. During the process of training and testing, the `bpp`, `ms-ssim`, `psnr` and `mse` are shown , which is quite convenient to observe. 
If you want to train on the ImageNet dataset, try this,
    
    python train.py ae_configs/cvpr/AE_CONFIG pc_configs/cvpr/PC_CONFIG \
            --dataset_train TRAIN_DATASET \
            --dataset_test TEST_DATASET \
            --log_dir_root LOG_DIR_ROOT
    
Where `AE_CONFIG` and `PC_CONFIG` are one of the configs in the respective folders.

What's more, we can observe the result in `Tensorboard`:

    tensorboard --logdir LOG_DIR_ROOT/id
    
Where `id` is the filename of your training results.

## Reference

I make this program mainly under the inspiration from the following:

    @inproceedings{mentzer2018conditional1,
        Author = {Mentzer, Fabian and Agustsson, Eirikur and Tschannen, Michael and Timofte, Radu and Van Gool, Luc},
        Booktitle = {Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
        Title = {Conditional Probability Models for Deep Image Compression},
        Year = {2018}}
