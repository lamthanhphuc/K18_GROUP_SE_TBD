# Paper 2 Summary

## 1. Paper Information

- Title: Automating Code Review Activities by Large-Scale Pre-training
- Authors: Zhiyu Li, Shuai Lu, Daya Guo, Nan Duan, Shailesh Jannu, Grant Jenks, Deep Majumder, Jared Green, Alexey Svyatkovskiy, Shengyu Fu, Neel Sundaresan
- Year: 2022
- Venue/Source: Proceedings of the 30th ACM Joint European Software Engineering Conference and Symposium on the Foundations of Software Engineering (ESEC/FSE 2022)
- Link: https://dl.acm.org/doi/10.1145/3540250.3549081
- PDF Link: https://arxiv.org/pdf/2203.09095.pdf
- DOI: https://doi.org/10.1145/3540250.3549081

## 2. Problem

Code review thá»§ cĂ´ng yĂªu cáº§u reviewer Ä‘á»c diff, hiá»ƒu logic, cháº¡y hoáº·c suy luáº­n chÆ°Æ¡ng trĂ¬nh, kiá»ƒm tra style, performance vĂ  nhiá»u yáº¿u tá»‘ cháº¥t lÆ°á»£ng khĂ¡c. Viá»‡c nĂ y tá»‘n nhiá»u thá»i gian, Ä‘áº·c biá»‡t khi sá»‘ lÆ°á»£ng thay Ä‘á»•i lá»›n. Paper Ä‘áº·t váº¥n Ä‘á» tá»± Ä‘á»™ng hĂ³a má»™t sá»‘ hoáº¡t Ä‘á»™ng trong code review báº±ng mĂ´ hĂ¬nh pre-trained chuyĂªn cho code diff vĂ  review data.

## 3. Method

Paper Ä‘á» xuáº¥t CodeReviewer, má»™t pre-trained model Ä‘Æ°á»£c thiáº¿t káº¿ cho code review. MĂ´ hĂ¬nh há»c tá»« code changes vĂ  review comments, sá»­ dá»¥ng cĂ¡c pre-training tasks chuyĂªn biá»‡t Ä‘á»ƒ hiá»ƒu quan há»‡ giá»¯a file cÅ©, diff, review comment vĂ  code Ä‘Ă£ chá»‰nh sá»­a. CodeReviewer Ä‘Æ°á»£c fine-tune/evaluate trĂªn ba hoáº¡t Ä‘á»™ng: code change quality estimation, review comment generation, vĂ  code refinement.

Trong repo chĂ­nh thá»©c, ba task Ä‘Æ°á»£c mĂ´ táº£ tÆ°Æ¡ng á»©ng lĂ  `cls`, `msg`, vĂ  `ref`: dá»± Ä‘oĂ¡n diff cĂ³ cáº§n comment hay khĂ´ng, sinh review comment tá»« old file + diff hunk, vĂ  chá»‰nh code dá»±a trĂªn old file + diff hunk + review comment.

## 4. Dataset / Input

Dataset gá»“m cĂ¡c code changes vĂ  code reviews thá»±c táº¿ tá»« open-source projects, bao phá»§ chĂ­n ngĂ´n ngá»¯ láº­p trĂ¬nh phá»• biáº¿n. Input Ä‘iá»ƒn hĂ¬nh gá»“m `old_file`, `diff_hunk`, `comment` vĂ  `target` tĂ¹y task. Zenodo Ä‘i kĂ¨m paper cung cáº¥p cĂ¡c gĂ³i dá»¯ liá»‡u cho Diff Quality Estimation, Comment Generation vĂ  Code Refinement.

## 5. Metrics

Paper Ä‘Ă¡nh giĂ¡ theo tá»«ng task. Vá»›i quality estimation, hÆ°á»›ng Ä‘Ă¡nh giĂ¡ lĂ  bĂ i toĂ¡n phĂ¢n loáº¡i nĂªn dĂ¹ng cĂ¡c chá»‰ sá»‘ nhÆ° precision, recall, F1 vĂ  accuracy. Vá»›i comment generation vĂ  code refinement, hÆ°á»›ng Ä‘Ă¡nh giĂ¡ lĂ  sinh chuá»—i/code nĂªn dĂ¹ng cĂ¡c chá»‰ sá»‘ sinh nhÆ° BLEU vĂ  Exact Match. CĂ¡c metric nĂ y phĂ¹ há»£p Ä‘á»ƒ tham kháº£o cho prototype nhÆ°ng váº«n cáº§n human review vĂ¬ metric tá»± Ä‘á»™ng khĂ´ng Ä‘o háº¿t Ä‘á»™ há»¯u Ă­ch cá»§a feedback.

## 6. Results

Káº¿t quáº£ chĂ­nh Ä‘Æ°á»£c bĂ¡o cĂ¡o lĂ  CodeReviewer vÆ°á»£t cĂ¡c pre-trained baselines trÆ°á»›c Ä‘Ă³ trĂªn cáº£ ba task. PhĂ¢n tĂ­ch thĂªm cho tháº¥y pre-training tasks chuyĂªn cho code review vĂ  dá»¯ liá»‡u Ä‘a ngĂ´n ngá»¯ giĂºp mĂ´ hĂ¬nh hiá»ƒu code changes vĂ  review comments tá»‘t hÆ¡n. Äiá»u nĂ y chá»©ng minh LLM/model chuyĂªn biá»‡t cĂ³ thá»ƒ há»— trá»£ cĂ¡c bÆ°á»›c nhÆ° nháº­n diá»‡n thay Ä‘á»•i Ä‘Ă¡ng chĂº Ă½, sinh comment vĂ  Ä‘á» xuáº¥t refinement.

## 7. Limitations

Paper táº­p trung vĂ o dá»¯ liá»‡u code review lá»‹ch sá»­, nĂªn model cĂ³ thá»ƒ há»c bias tá»« comment cÅ© hoáº·c thiáº¿u ngá»¯ cáº£nh business cá»§a tá»«ng dá»± Ă¡n. CĂ¡c metric nhÆ° BLEU/Exact Match cÅ©ng cĂ³ háº¡n cháº¿ vĂ¬ má»™t feedback Ä‘Ăºng cĂ³ thá»ƒ Ä‘Æ°á»£c viáº¿t theo nhiá»u cĂ¡ch khĂ¡c nhau. MĂ´ hĂ¬nh há»— trá»£ review nhÆ°ng khĂ´ng Ä‘áº£m báº£o phĂ¡t hiá»‡n má»i lá»—i logic, báº£o máº­t hoáº·c yĂªu cáº§u sáº£n pháº©m.

## 8. Ideas Learned for Our Prototype

Prototype AI Review hackathon cĂ³ thá»ƒ há»c cĂ¡ch tĂ¡ch output theo nhiá»u nhiá»‡m vá»¥: `review_score` cho Æ°á»›c lÆ°á»£ng cháº¥t lÆ°á»£ng, `issues` cho Ä‘iá»ƒm cáº§n chĂº Ă½, `suggestions` cho gá»£i Ă½ sá»­a, vĂ  `summary` cho nháº­n xĂ©t tá»•ng quĂ¡t. Tuy nhiĂªn, khĂ¡c vá»›i CodeReviewer, prototype nĂªn Æ°u tiĂªn Ä‘á»‹nh dáº¡ng JSON á»•n Ä‘á»‹nh, giáº£i thĂ­ch dá»… hiá»ƒu cho participant/mentor, vĂ  ghi rĂµ AI Review chá»‰ lĂ  feedback tham kháº£o, khĂ´ng tá»± Ä‘á»™ng áº£nh hÆ°á»Ÿng ranking.

VĂ¬ váº­y, paper nĂ y phĂ¹ há»£p vá»›i Ä‘á» tĂ i vĂ¬ nĂ³ cung cáº¥p cÆ¡ sá»Ÿ Ä‘á»ƒ thiáº¿t káº¿ output AI Review gá»“m `review_score`, `summary`, `issues` vĂ  `suggestions`, nhÆ°ng cĂ¡c káº¿t quáº£ nĂ y váº«n chá»‰ nĂªn dĂ¹ng nhÆ° feedback tham kháº£o cho con ngÆ°á»i kiá»ƒm chá»©ng.
