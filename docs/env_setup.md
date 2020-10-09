Installing environment with conda

* Load conda
  ```
  module load python/anaconda3
  ```
* Add conda to ~/.bashrc
  ```
  conda init bash
  source ~/.bashrc
  ``` 
* Create environment
  ```
  conda env create --prefix ~/.conda/envs/asr -f asr_speedup/Automatic-Speech-Recognition/environment-gpu.yml python=3.7.5
  ```
* Install additional ipykernel
  ```
  conda install -n asr ipykernel
  ```
* Install libsndfile
  ```
  conda install -n asr -c conda-forge libsndfile
  ```
* Reset environment variables
  ```
  module unload python/anaconda3
  ```
* Activate environment
  ```
  conda activate asr
  ```
* Install the kernelspec
  ```
  python -m ipykernel install --user --name asr
  ```
* Modify kernelspec to contain additional paths
  ```
  vi ~/.local/share/jupyter/kernels/asr/kernel.json
  ```
  Add the following entry into json file. 
  Replace "/gpfs/data/home/r.schutski/.conda/envs/asr" 
  with the actual path to your environment
  ```
  ...,
  "env": {
  "PATH": "/gpfs/data/home/r.schutski/.conda/envs/asr/bin:/sbin:/bin:/usr/sbin:/usr/bin:/trinity/shared/opt/singularity-3.1.0/bin:/usr/local/sbin:/opt/ibutils/bin:/trinity/home/r.schutski/.local/bin:/trinity/home/r.schutski/bin",
  "PYTHONHOME": "",
  "PYTHONPATH": "",
  "LD_LIBRARY_PATH": "/trinity/home/r.schutski/.conda/envs/asr/lib:/trinity/home/r.schutski/.conda/envs/asr/lib/python3.7:/gpfs/data/opt/cuda-10.1/lib64:/gpfs/data/opt/MPI/openmpi-3.1.2/lib"},
  ...
  ```
	
