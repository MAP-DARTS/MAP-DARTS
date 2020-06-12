# MAP-DARTS

## Requirements
```
python==3.7.4
torch==1.5.0
torchvision==0.6.0
numpy==1.16.4
```

## Usage


#### Searching on CIFAR10

```
python train_search.py --prior_path <path_to_priors>
```
#### Searching on ImageNet

Data preparation: 10% and 2.5% images need to be random sampled prior from earch class of trainingset as train and val, respectively. The sampled data is saved into `./imagenet_search`.
Note that not to use torch.utils.data.sampler.SubsetRandomSampler for data sampling as imagenet is too large.
```
python train_search_imagenet.py \\
       --tmp_data_dir /path/to/your/sampled/data \\
       --save log_path \\
       --prior_path <path_to_priors>
```
#### Evaluation on CIFAR10

```
python train.py \\
       --auxiliary \\
       --cutout \\
```

#### Evaluation on ImageNet
```
python train_imagenet.py \\
       --tmp_data_dir /path/to/your/data \\
       --save log_path \\
       --auxiliary \\
       --note note_of_this_run
```