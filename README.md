# MMBERT

## MMBERT: Multimodal BERT Pretraining for Improved Medical VQA
Yash Khare*, Viraj Bagal*, Minesh Mathew, Adithi Devi, U Deva Priyakumar, CV Jawahar

![alt text](https://github.com/VirajBagal/MMBERT/blob/main/qualitative.png?raw=true)

The application of Visual Question Answering (VQA) in the medical field has sgnificantly impacted the traditional medical research methods.
A mature medical visual question answering system can greatly help the patients diagnose. The  Visual Question Answering Model in the generic
domain is not effect enough for the feature alignment in medical image and text semantics because of the complex diversity of clinical 
problems and the difficulties in multi-modal reasoning. To solve these, we propose a model called FGCVQA. It is important to consider 
the semantic alignment of both the medical images and the language features. Specifially, We use the Cross-Modality Encoder to learn the 
semantic representation of medical images and texts. It effectively improves the reasoning ability of different modals by considering 
fine-grained property.  The experimental results show that FGCVQA outperforms all previous methods on dataset VQA-RAD, for radiology images.
FGCVQA is effective in answering medical visual questions and can help doctors to make better clinical analysis and diagnosis.

## Train on VQARAD

```
python train_vqarad.py  --mixed_precision --use_pretrained --lr set_lr  --epochs set_epochs
```


## Evaluate 

```
python eval.py  --mixed_precision --category cat_name --hidden_size hidden_dim_size --use_pretrained
```

## VQARAD Results

FGCVQA, which is a single model for both the question types
in the dataset, outperforms the existing approaches including
the ones which have a dedicated model for each question
type.

| Method                | Dedicated Models | Open Acc. | Closed Acc. | Overall Acc. |
|-----------------------| --- |-----------|-------------| -- | 
| MEVF + SAN            | - | 40.7      | 74.1        | 60.8 |
| MEVF + BAN            | - | 43.9      | 75.1        | 62.7 |
| Conditional Reasoning | :heavy_check_mark: | 60.0   | 79.3     | 71.6 |
| MMBERT                | :x: | 63.1      | 77.9        | 72.0 | 
| FITS                  | :x: | 68.2      | 82.0        | 76.5 | 
| FGCVQA                | :x: | 66.5      | 84.6        | 77.4 | 



