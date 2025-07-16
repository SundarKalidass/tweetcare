# 🧬 TweetCare-Phi3-LoRA

A fine-tuned **Phi-3 Mini (128k Instruct)** model using **LoRA** on a **Customer Support Twitter** dataset for social media support automation.

---

## 🚀 Project Overview

TweetCare-Phi3-LoRA is a lightweight, instruction-tuned model built for:

* ✅ Customer support query resolution
* ✅ Trained on real Twitter conversations
* ✅ Efficient fine-tuning with LoRA
* ✅ Ready for deployment in RAG, chatbot, or support ticket systems

---

## 📊 Dataset

**📱 Mo Customer Support Tweets**

* 945k+ tweet-reply pairs between customers and support accounts
* Filtered to extract valid, user-facing queries and generic responses
* Transformed into instruction-format prompts for training

**Dataset Link:** [Hugging Face - mo-customer-support-tweets-945k](https://huggingface.co/datasets/MohammadOthman/mo-customer-support-tweets-945k)

---

## 🏗️ Model Architecture

* **Base Model:** [`microsoft/phi-3-mini-128k-instruct`](https://huggingface.co/microsoft/phi-3-mini-128k-instruct)
* **LoRA Strategy:** Applied to `q_proj`, `k_proj`, `v_proj`, `o_proj`, `gate_proj`, `down_proj`, `up_proj`
* **Quantization:** 4-bit using `bitsandbytes`
* **Training Platform:** Google Colab with 1x T4 GPU (or equivalent)

---

## 🧠 Training Workflow

1. Preprocessed 10K tweets into `Instruction → Input → Response` format
2. Tokenized using Phi-3 tokenizer
3. Fine-tuned using LoRA with PEFT and `trl`'s `SFTTrainer`

---

## 🏁 Output Files

* `tweetcare-phi3-mini-lora-v1/` — LoRA adapter model (weights, config, tokenizer)
* `tweetcare_finetune.ipynb` — Colab notebook with training steps
* `README.md` — This documentation

---

## 💬 Sample Prompt

**Prompt:**

```text
### Instruction:
Respond to this customer tweet:
### Input:
I’ve been waiting 5 days and still no response from your team!
### Response:
```

**Model Output:**

```text
We sincerely apologize for the delay. Please DM your ticket number so we can prioritize your request.
```

---

## 🔮 Future Enhancements

* 🔁 Add real support replies for supervised fine-tuning
* 🤖 Integrate into a full-stack customer support assistant (FastAPI + React)
* 🧠 RAG-enabled support using FAQs or policy docs
* 🚀 Deploy to Hugging Face Spaces or AWS Lambda for real-time usage

---

## 🤝 Contributing

Pull requests and issues are welcome! If you build upon this project or use the model, please give credit.

---

## 📜 License

This project is licensed under the MIT License.
