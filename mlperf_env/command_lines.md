Test run mgx batch
```
python txt2img_batch.py     --prompt "Astronaut in a jungle, cold color palette, muted colors, detailed, 8k",              "Sunset over a mountain range, warm colors, realistic, high resolution",              "Portrait of an old sailor, black and white, detailed wrinkles, 4k"     --negative-prompt "low quality, blurry", "overexposed", "grainy, underexposed"     --seed 42     --output batch_output     --pipeline-type sdxl     --fp16 all     --batch 3 --exhaustive-tune --force-compile > compile_out.txt
```
