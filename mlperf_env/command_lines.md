Test run mgx batch
```
python txt2img_batch.py     --prompt "Astronaut in a jungle, cold color palette, muted colors, detailed, 8k",              "Sunset over a mountain range, warm colors, realistic, high resolution",              "Portrait of an old sailor, black and white, detailed wrinkles, 4k"     --negative-prompt "low quality, blurry", "overexposed", "grainy, underexposed"     --seed 42     --output batch_output     --pipeline-type sdxl     --fp16 all     --batch 3 --exhaustive-tune --force-compile > compile_out.txt
```

multi-node
```
server_sut:
python sut_over_network_demo.py --dataset "coco-1024" --dataset-path coco2014 --profile stable-diffusion-xl-pytorch --dtype fp16 --device cuda --scenario Offline --max-batchsize 4

network_server:
python py_demo_server_lon.py --sut-server http://t007-001:8888 http://t006-001:8888 --dataset=coco-1024 --dataset-path=/work1/zixian/ziw081/inference/text_to_image/coco2014 --profile=stable-diffusion-xl-pytorch --dtype=fp16 --device=cuda --time=30 --scenario=Offline --max-batchsize=4

python main.py --sut-server http://t007-001:8888 http://t006-001:8888 --dataset=coco-1024 --dataset-path=/work1/zixian/ziw081/inference/text_to_image/coco2014 --profile=stable-diffusion-xl-pytorch --dtype=fp16 --device=cuda --time=30 --scenario=Offline --max-batchsize=4
```
