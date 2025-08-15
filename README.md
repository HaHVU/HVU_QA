# HVU_QA

**HVU_QA** is an open-source Vietnamese Question–Context–Answer (QCA) corpus and supporting tools for building FAQ-style question generation systems in low-resource languages. The dataset was created using a fully automated pipeline that combines web crawling from trustworthy sources, semantic tag-based extraction, and AI-assisted filtering to ensure high factual accuracy.

## Dataset Description

- **Language:** Vietnamese
- **Format:** SQuAD-style JSON
- **Total samples:** 30,000 QCA triples (full corpus released)
- **Domains covered:** Social services, labor law, administrative processes, and other public service topics.
- **Structure of each sample:**
  - **Question:** Generated or extracted question
  - **Context:** Supporting text passage from which the answer is derived
  - **Answer:** Answer span within the context

## Creation Pipeline

The dataset was built using a 4-stage automated process:
1. **Selecting relevant QA websites** from trusted sources.
2. **Automated data crawling** to collect raw QA webpages.
3. **Extraction via semantic tags** to obtain clean Question–Context–Answer triples.
4. **AI-assisted filtering** to remove noisy or factually inconsistent samples.

## Quality Evaluation

A fine-tuned `VietAI/vit5-base` model trained on HVU_QA achieved:
- **BLEU:** 90.61
- **Semantic similarity:** 97.0% (cosine similarity ≥ 0.8)
- **Human evaluation scores:**
  - Grammaticality: 4.58 / 5
  - Usefulness: 4.29 / 5

These results confirm that HVU_QA is a high-quality resource for developing robust FAQ-style question generation models.

## Citation
If you use **HVU_QA** in your research, please cite our paper:
@inproceedings{nguyen2025hvuqa,
  title={A Method to Build QA Corpora for Low-Resource Languages},
  author={Ha Nguyen-Tien and Phuc Le-Hong and Dang Do-Cao and Cuong Nguyen-Hung and Chung Mai-Van},
  booktitle={Proceedings of KSE 2025},
  year={2025}
}
