# AT-Net

Atmospheric turbulence can significantly degrade the quality of images acquired by long-range imaging systems by causing spatially and temporally random fluctuations in the index of refraction of the atmosphere. Variations in the refractive index causes the captured images to be geometrically distorted and blurry. Hence, it is important to compensate for the visual degradation in images caused by atmospheric turbulence. In this paper, we propose a deep learning-based approach for restring a single image degraded by atmospheric turbulence. We make use of the epistemic uncertainty based on Monte Carlo dropouts to capture regions in the image where the network is having hard time restoring. The estimated uncertainty maps are then used to guide the network to obtain the restored image. Extensive experiments are conducted on synthetic and real images to show the significance of the proposed work.

## Installation

1. **Set up a virtual environment:**

    ```bash
    # On Unix/Linux/MacOS
    python3 -m venv ATNET

    # On Windows
    python -m venv ATNET
    ```

2. **Activate the virtual environment:**

    ```bash
    # On Unix/Linux/MacOS
    source ATNET/bin/activate

    # On Windows
    .\ATNET\Scripts\activate
    ```

3. **Install dependencies:**

    Once the virtual environment is activated, you can install the required dependencies using pip.

    ```bash
    pip install -r requirements.txt
    ```

## Usage

## To train AT-Net
1. Clean face images from Helen and CelebA are aligned and used as input to train AT-Net.
2. Specify train directory and validation directory in train.py lines (57-58)
```
    train_data_dir = '/media/labuser/cb8bb1ad-451a-4aa4-870c-2d3eeafe2525/FFHD_data/images512x512/'
    val_data_dir = '/media/labuser/cb8bb1ad-451a-4aa4-870c-2d3eeafe2525/Tubfaces89/300M/tubimages/'
```
Note for training you should mention clean images path, train_data.py will generate pairs of turbulence degraded images (refer lines 78-96 in train_data.py ). turbulence degradation parameters can be modified in config_tdrn.py
3. Run the following command to train At-Net
```
python train.py --learning_rate 2e-4 --crop_size [256,256] --train_batch_size 2 --epoch_start 0 --lambda_loss 2e-3 --exp_name ./results --lambda_GP 0.0015
```

## To test AT-Net
```
python test.py --val_dir ="path_test_images" --checkpoint="path_to_models" --exp_name "./results"
```
pretrained models can downloaded from this link .(https://drive.google.com/drive/folders/1kOgKsrJOd5qwL8LseaIw4OxXPBwluso0?usp=drive_link)


