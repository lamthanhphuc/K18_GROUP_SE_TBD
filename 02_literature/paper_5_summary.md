# Paper 5 Summary

## 1. Paper Information

- Title: Benchmarking and Studying the LLM-based Code Review
- Authors: Zhengran Zeng, Ruikai Shi, Keke Han, Yixin Li, Kaicheng Sun, Yidong Wang, Zhuohao Yu, Rui Xie, Wei Ye, Shikun Zhang
- Year: 2025
- Venue/Source: arXiv preprint
- Note: Paper nĂ y hiá»‡n lĂ  arXiv preprint, vĂ¬ váº­y káº¿t quáº£ nĂªn Ä‘Æ°á»£c xem lĂ  cÆ¡ sá»Ÿ tham kháº£o ban Ä‘áº§u cho giai Ä‘oáº¡n Ká»³ 5.
- Link: https://arxiv.org/abs/2509.01494
- PDF Link: https://arxiv.org/pdf/2509.01494.pdf
- DOI: https://doi.org/10.48550/arXiv.2509.01494

## 2. Problem

CĂ¡c benchmark automated code review cÅ© thÆ°á»ng táº­p trung vĂ o code snippet hoáº·c má»™t sá»­a Ä‘á»•i nhá», thiáº¿u full project context, vĂ  dĂ¹ng metric nhÆ° text similarity hoáº·c rating Ä‘Æ¡n giáº£n. Nhá»¯ng cĂ¡ch nĂ y khĂ´ng pháº£n Ă¡nh tá»‘t code review thá»±c táº¿ trĂªn pull request. Paper Ä‘áº·t váº¥n Ä‘á» xĂ¢y dá»±ng benchmark vĂ  evaluation method sĂ¡t real-world hÆ¡n cho LLM-based code review.

## 3. Method

Paper giá»›i thiá»‡u SWR-Bench, benchmark gá»“m cĂ¡c pull requests thá»±c táº¿ tá»« GitHub, cĂ³ full project context vĂ  structured ground truth. Thay vĂ¬ chá»‰ so sĂ¡nh text output vá»›i comment gá»‘c, paper dĂ¹ng objective LLM-based evaluation Ä‘á»ƒ kiá»ƒm tra generated review cĂ³ bao phá»§ cĂ¡c issue trong ground truth hay khĂ´ng. Sau khi benchmark cĂ¡c ACR tools vĂ  LLMs, tĂ¡c giáº£ Ä‘á» xuáº¥t Multi-Review: cháº¡y review nhiá»u láº§n hoáº·c tá»« nhiá»u nguá»“n, sau Ä‘Ă³ dĂ¹ng LLM aggregation Ä‘á»ƒ lá»c feedback Ä‘Ăºng vĂ  tá»•ng há»£p report cuá»‘i.

## 4. Dataset / Input

Dataset chĂ­nh lĂ  1,000 manually verified pull requests tá»« GitHub open-source projects. Má»—i instance cung cáº¥p thay Ä‘á»•i trong PR vĂ  snapshot/repository context cáº§n thiáº¿t Ä‘á»ƒ reviewer hiá»ƒu tĂ¡c Ä‘á»™ng cá»§a thay Ä‘á»•i. Input Ä‘Ă¡nh giĂ¡ lĂ  review report do ACR tool hoáº·c LLM sinh ra so vá»›i structured ground truth.

## 5. Metrics

Metrics trá»ng tĂ¢m gá»“m issue coverage so vá»›i ground truth, Precision, Recall, F1, false positives/incorrect feedback, vĂ  human agreement vá»›i objective LLM-based evaluation. Paper bĂ¡o cĂ¡o phÆ°Æ¡ng phĂ¡p Ä‘Ă¡nh giĂ¡ Ä‘áº¡t khoáº£ng 90% agreement vá»›i human judgment. ÄĂ¢y lĂ  hÆ°á»›ng metric phĂ¹ há»£p hÆ¡n text similarity khi Ä‘Ă¡nh giĂ¡ feedback code review.

## 6. Results

Káº¿t quáº£ cho tháº¥y cĂ¡c ACR tools vĂ  LLM hiá»‡n táº¡i váº«n underperform trĂªn bá»‘i cáº£nh PR tháº­t, dĂ¹ chĂºng phĂ¡t hiá»‡n functional errors tá»‘t hÆ¡n non-functional issues nhÆ° documentation hoáº·c maintainability. Multi-Review cáº£i thiá»‡n Ä‘Ă¡ng ká»ƒ hiá»‡u nÄƒng: paper bĂ¡o cĂ¡o F1 tÄƒng tá»‘i Ä‘a 43.67%. Vá»›i má»™t cáº¥u hĂ¬nh Gemini-2.5-Flash Self-Agg, F1 Ä‘áº¡t 21.91% vĂ  Recall Ä‘áº¡t 30.44%, cho tháº¥y aggregation giĂºp tĂ¬m thĂªm true issues nhÆ°ng váº«n cáº§n giáº£m false positives Ä‘á»ƒ tÄƒng precision.

## 7. Limitations

Paper lĂ  arXiv preprint á»Ÿ nguá»“n Ä‘Ă£ kiá»ƒm tra. Benchmark váº«n chá»‰ Ä‘áº¡i diá»‡n cho táº­p PR vĂ  project Ä‘Æ°á»£c chá»n; káº¿t quáº£ cĂ³ thá»ƒ thay Ä‘á»•i vá»›i domain, ngĂ´n ngá»¯ láº­p trĂ¬nh hoáº·c quy mĂ´ repo khĂ¡c. Objective LLM-based evaluation Ä‘Ă£ Ä‘Æ°á»£c human validation nhÆ°ng váº«n phá»¥ thuá»™c vĂ o LLM evaluator vĂ  structured ground truth.

## 8. Ideas Learned for Our Prototype

Prototype nĂªn Ä‘Ă¡nh giĂ¡ káº¿t quáº£ AI Review báº±ng nhiá»u metric thá»±c táº¿ hÆ¡n BLEU/text similarity. Vá»›i `04_result/initial_result.md`, cĂ³ thá»ƒ dĂ¹ng: sá»‘ issue trung bĂ¬nh tĂ¬m Ä‘Æ°á»£c, useful feedback rate, expert rating 1-5, false positive/incorrect feedback, review time, JSON format validity, vĂ  human agreement giá»¯a mentor/Judge vá»›i AI feedback. Paper cÅ©ng cá»§ng cá»‘ nguyĂªn táº¯c: AI Review chá»‰ há»— trá»£ phĂ¡t hiá»‡n vĂ  diá»…n giáº£i issue, khĂ´ng tá»± Ä‘á»™ng thay Judge hoáº·c ranking.

VĂ¬ váº­y, paper nĂ y phĂ¹ há»£p vá»›i Ä‘á» tĂ i vĂ¬ nĂ³ cung cáº¥p bá»™ metric thá»±c táº¿ Ä‘á»ƒ Ä‘Ă¡nh giĂ¡ prototype AI Review, Ä‘áº·c biá»‡t lĂ  useful feedback rate, false positive rate, expert rating, review time vĂ  format validity.
