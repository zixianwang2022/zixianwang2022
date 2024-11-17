```
pip3 install --pre torch torchvision torchaudio --index-url https://download.pytorch.org/whl/nightly/rocm6.2

export PYTHONPATH=/opt/rocm/lib:PYTHONPATH  
or   
export PYTHONPATH=/AMDMIGraphX/build/lib:PYTHONPATH  

pip install pybind11
cd inference/loadgen

conda install -c conda-forge libstdcxx-ng
CFLAGS="-std=c++14" python setup.py install

pip install opencv-python-headless
pip install pandas
pip install open_clip_torch
pip install scipy
pip install tabulate
pip install cmind
pip install flask
pip install diffusers
pip install transformers

cd ../text_to_image/
python3 main.py --dataset "coco-1024" --dataset-path coco2014 --profile stable-diffusion-xl-pytorch --model-path /work1/zixian/ziw081/CM/models/SDXL/official_pytorch/fp16/stable_diffusion_fp16/ --dtype fp16 --device cuda --time 30 --scenario Offline --max-batchsize 4 


python3 main.py --dataset "coco-1024" --dataset-path coco2014 --profile stable-diffusion-xl-pytorch --model-path /home/ziw081/CM/models/SDXL/official_pytorch/fp16/stable_diffusion_fp16/ --dtype fp16 --device cuda --time 30 --scenario Offline --max-batchsize 4 
```
