#  M2SE: A Multistage Multitask Instruction Tuning Strategy for Unified Sentiment and Emotion Analysis

Our paper: [arXiv](https://arxiv.org/abs/2412.08049).

## Emotion Multitask Dataset
In the **"data"** folder, you'll find training JSON files for each stage. These files are generated by randomly sampling tasks from the original EMT file. The original EMT dataset is still being organized.

### Stage Breakdown:
- **First Stage**: The files are based on randomly sampled tasks from the **MOSEI** dataset.
- **Second Stage**: The files are based on mixed sampling from three different datasets and various tasks.

### Dataset Sources:
- For the **MOSEI** dataset, download the video from [here](https://github.com/thuiar/MMSA).
- For the **MELD** dataset, download the video from [here](https://github.com/declare-lab/MELD).
- For the **ECF2.0** dataset, download the dataset from [here](https://github.com/NUSTM/SemEval-2024_ECAC/tree/main/data).

## Environment
The fine-tuning framework for EmoVerse based on ms-swift: https://github.com/modelscope/ms-swift.
```
conda create -n emoverse python=3.9
conda activate emoverse
pip install 'ms-swift[all]' -U
```

## Checkpoint
EmoVerse is fine-tuned based on Internvl2, download Internvl2 weights at https://github.com/OpenGVLab/InternVL.
Once the checkpoint is downloaded, place it in your own directory and make sure to update the model path in the corresponding .sh file accordingly. 

## First stage
```
bash first_stage.sh
```

## Second stage
```
bash second_stage.sh
```

## Evaluation
Once inference is completed using ms-swift, the corresponding inference files will be generated. You can then calculate the accuracy by using the functions in compute_result.py.
```
bash test.sh
python compute_result.py
```

## Cite us
```
@article{li2024m2se,
  title={M2SE: A Multistage Multitask Instruction Tuning Strategy for Unified Sentiment and Emotion Analysis},
  author={Li, Ao and Xu, Longwei and Ling, Chen and Zhang, Jinghui and Wang, Pengwei},
  journal={arXiv preprint arXiv:2412.08049},
  year={2024}
}
```
