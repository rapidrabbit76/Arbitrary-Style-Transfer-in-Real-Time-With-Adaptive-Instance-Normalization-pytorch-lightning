# Arbitrary Style Transfer in Real-time with Adaptive Instance Normalization

Unofficial pytorch-lightning implementation of a paper, "[Arbitrary Style Transfer in Real-time with Adaptive Instance Normalization](https://arxiv.org/pdf/1703.06868.pdf)" 


# Requirements
Install requirements by pip
``` shell 
pip install -r requirements.txt 
```

- torch==1.10.1
- torchvision==0.11.2
- pytorch-lightning==1.5.7
- tqdm==4.62.3
- wandb==0.12.10
- opencv-python-headless==4.5.5.62
- easydict==1.9
- onnxruntime==1.10.0

# Install by Docker
Install dependency by docker 
```shell
docker-compose up -d 
```

# Pretrained weights / models download

- **Encoder(VGG)** weights download by ["pytorch-AdaIN"](https://github.com/naoto0804/pytorch-AdaIN#download-models) repo 
- **Decoder** weights download by [link]() # TODO
- **Net pl module ** weights download by [link]() # TODO
- **Torchscript** model download by [link]() # TODO
- **Net onnx** model download by [link]() # TODO

# Dataset 
- content : [COCO DATASET](http://images.cocodataset.org/zips/train2017.zip)
- style : [WikiArt](https://drive.google.com/u/0/uc?id=182-pFiKvXPB25DbTfAYjJ6gDE-ZCRXz0&export=download&confirm=t)

# Training

1. download dataset (content, style)
2. download Encoder weights and mv to weights dir 
3. check dataset path 
4. run script 
```bash 
python main.py \
--content_root_dir="{YOUR CONTENT DATASET PATH}" \
--style_root_dir="{YOUR STYLE DATASET PATH}" \
--num_workers=8 \
--batch_size=8 \
--log_every_n_steps=5 \
--gpus=1 \
--max_steps=16000
```


# Training result 


<details>
<summary> result plot, images </summary>

## loss plot
![content_loss](./src/plot/content_loss.png)
![style_loss](./src/plot/style_loss.png)


## sample images 

![video](./src/video/training_sample.gif)
- [video](./src/video/training_sample.mp4)

</details>




# Using APP 

Streamlit app source code referenced "[Neural-Style-Transfer-Streamlit
](https://github.com/kairavkkp/Neural-Style-Transfer-Streamlit)"

![app_01](./src/app/01.png)
![app_02](./src/app/02.png)


<details>
<summary> Menual </summary>

## Requirements
Install requirements by pip
``` shell 
pip install -r requirements.txt 
```

- torch==1.10.1
- torchvision==0.11.2
- pytorch-lightning==1.5.7
- streamlit==1.7.0
- opencv-python-headless==4.5.5.62

## Install by Docker
Install dependency by docker 
```shell
docker-compose up -d 
```

## ENV 
- MODEL_PATH : torchscript file path



</details>


# References
- [Arbitrary Style Transfer in Real-time with Adaptive Instance Normalization](https://arxiv.org/pdf/1703.06868.pdf)
- [pytorch-AdaIN](https://github.com/naoto0804/pytorch-AdaIN#download-models) 
- [Neural-Style-Transfer-Streamlit
](https://github.com/kairavkkp/Neural-Style-Transfer-Streamlit)