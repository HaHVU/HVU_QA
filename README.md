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

## 📁 Vietnamese Question Generation Tool

## 📂 Project Structure

```
.HVU_QA
├── t5-viet-qg-finetuned/
├── fine_tune_qg.py
├── generate_question.py
├── 30ktrain.json
└── README.md
```
> All data files are UTF-8 encoded and ready for use in NLP pipelines.

---

## 🛠️ Requirements

* Python 3.8+
* PyTorch >= 1.9
* Transformers >= 4.30
* scikit-learn
* Fine-tuned model (download at: [link](https://huggingface.co/datasets/DANGDOCAO/GeneratingQuestions/tree/main))

---

## 🚀 Setup

### Step 1: Download and Extract

1. Download `HVU_QA.zip`
2. Extract into a folder, e.g.:

   ```
   D:\your\HVU_QA
   ```

### Step 2: Add to Environment Path (if needed)

1. Open **System Properties → Environment Variables**
2. Select `Path` → **Edit** → **New**
3. Add the path, e.g.:

   ```
   D:\your\HVU_QA
   ```

### Step 3: Open in Visual Studio Code

```
File > Open Folder > D:\HVU_QA
```

### Step 4: Install Required Libraries

Open **Terminal** and run:

#### 📦 Windows (PowerShell)

**Required only**

```powershell
python -m pip install --upgrade pip
pip install torch transformers datasets scikit-learn sentencepiece safetensors
```

**Required + Optional**

```powershell
python -m pip install --upgrade pip
pip install torch transformers datasets scikit-learn sentencepiece safetensors accelerate tensorboard evaluate sacrebleu rouge-score nltk
```

#### 📦 Linux / macOS (bash/zsh)

**Required only**

```bash
python3 -m pip install --upgrade pip
pip install torch transformers datasets scikit-learn sentencepiece safetensors
```

**Required + Optional**

```bash
python3 -m pip install --upgrade pip
pip install torch transformers datasets scikit-learn sentencepiece safetensors accelerate tensorboard evaluate sacrebleu rouge-score nltk
```

✅ Verify installation:

* Windows (PowerShell)

```powershell
python -c "import torch, transformers, datasets, sklearn, sentencepiece, safetensors, accelerate, tensorboard, evaluate, sacrebleu, rouge_score, nltk; print('✅ All dependencies installed correctly!')"
```

* Linux/macOS

```bash
python3 -c "import torch, transformers, datasets, sklearn, sentencepiece, safetensors, accelerate, tensorboard, evaluate, sacrebleu, rouge_score, nltk; print('✅ All dependencies installed correctly!')"
```

---

## 📚 Usage

* Train and evaluate a question generation model.
* Develop Vietnamese NLP tools.
* Conduct linguistic research.

### 🔹 Training (Fine-tuning)

When you run `fine_tune_qg.py`, the script will:

1. Load the dataset from **`30ktrain.json`**
2. Fine-tune the `VietAI/vit5-base` model
3. Save the trained model into a new folder named **`t5-viet-qg-finetuned/`**

Run:

```bash
python fine_tune_qg.py
```

### 🔹 Generating Questions

```bash
python generate_question.py
```

**Example:**

```
Input passage:
Iced milk coffee (Cà phê sữa đá) is a famous drink in Vietnam.

Number of questions: 5
```

✅ Output:

1. What type of coffee is famous in Vietnam?
2. Why is iced milk coffee popular?
3. What ingredients are included in iced milk coffee?
4. Where does iced milk coffee originate from?
5. How is Vietnamese iced milk coffee prepared?

---

## ⚙️ Generation Settings

In `generate_question.py`, you can adjust:

* `top_k`, `top_p`, `temperature`, `no_repeat_ngram_size`, `repetition_penalty`

---

## 🤝 Contribution

We welcome contributions:

* Open issues
* Submit pull requests
* Suggest improvements or add datasets

## Citation

If you use **HVU_QA** in your research, please cite our paper:

```bibtex
@inproceedings{nguyen2025hvuqa,
  title={A Method to Build QA Corpora for Low-Resource Languages},
  author={Ha Nguyen-Tien and Phuc Le-Hong and Dang Do-Cao and Cuong Nguyen-Hung and Chung Mai-Van},
  booktitle={Proceedings of KSE 2025},
  year={2025}
}

