# Paper 3 Summary

## 1. Paper Information

- Title: Combining Large Language Models with Static Analyzers for Code Review Generation
- Authors: Imen Jaoua, Oussama Ben Sghaier, Houari Sahraoui
- Year: 2025
- Venue/Source: Mining Software Repositories (MSR 2025); arXiv preprint
- Link: https://2025.msrconf.org/details/msr-2025-technical-papers/27/Combining-Large-Language-Models-with-Static-Analyzers-for-Code-Review-Generation
- PDF Link: https://arxiv.org/pdf/2502.06633.pdf
- DOI: https://doi.org/10.1109/MSR66628.2025.00038

## 2. Problem

Static analyzers nhÆ° PMD hoáº·c Checkstyle cĂ³ Ä‘á»™ chĂ­nh xĂ¡c tá»‘t vá»›i rule rĂµ rĂ ng, nhÆ°ng pháº¡m vi háº¹p vĂ  khĂ³ hiá»ƒu cĂ¡c váº¥n Ä‘á» phá»¥ thuá»™c ngá»¯ cáº£nh. NgÆ°á»£c láº¡i, LLM cĂ³ thá»ƒ sinh review comment tá»± nhiĂªn vĂ  bao phá»§ nhiá»u loáº¡i issue hÆ¡n, nhÆ°ng dá»… thiáº¿u precision hoáº·c sinh feedback khĂ´ng Ä‘Ăºng. Paper giáº£i quyáº¿t trade-off giá»¯a coverage cá»§a LLM vĂ  precision cá»§a static analysis trong code review generation.

## 3. Method

Paper Ä‘á» xuáº¥t pipeline hybrid káº¿t há»£p Knowledge-Based Systems (KBS) vĂ  Learning-Based Systems (LBS). LBS lĂ  CodeLlama-7B Ä‘Æ°á»£c fine-tune cho review comment generation. KBS lĂ  cĂ¡c static analyzers cho Java, cá»¥ thá»ƒ PMD vĂ  Checkstyle. Ba chiáº¿n lÆ°á»£c káº¿t há»£p Ä‘Æ°á»£c Ä‘Ă¡nh giĂ¡:

- Data-Augmented Training (DAT): sinh vĂ  lá»c dá»¯ liá»‡u review tá»« cáº£ LBS vĂ  KBS rá»“i fine-tune láº¡i model.
- Retrieval-Augmented Generation (RAG): Ä‘Æ°a káº¿t quáº£ static analyzer vĂ o prompt á»Ÿ inference time.
- Naive Concatenation of Outputs (NCO): ghĂ©p output tá»« static analyzer vĂ  LLM sau khi sinh.

## 4. Dataset / Input

Paper dĂ¹ng real-world code review dataset, sau Ä‘Ă³ lá»c vá» cĂ¡c Java samples Ä‘á»ƒ cháº¡y trá»±c tiáº¿p PMD vĂ  Checkstyle trĂªn source code. Input gá»“m code change/diff cho LLM vĂ  source file cho static analyzer. Data vĂ  replication package Ä‘Æ°á»£c cĂ´ng bá»‘ qua GitHub/Zenodo; sá»‘ lÆ°á»£ng sample chĂ­nh xĂ¡c trong báº£n HTML Ä‘Ă£ xem khĂ´ng hiá»ƒn thá»‹ rĂµ nĂªn khĂ´ng tá»± Ă½ ghi sá»‘.

## 5. Metrics

ÄĂ¡nh giĂ¡ gá»“m manual accuracy assessment, LLM-as-a-judge, Cohen's kappa Ä‘á»ƒ Ä‘o agreement giá»¯a LLM vĂ  human judgment, coverage ranking, vĂ  win-tie-loss analysis. Review Ä‘Æ°á»£c phĂ¢n loáº¡i thĂ nh accurate, partially accurate hoáº·c not accurate. Coverage Ä‘Æ°á»£c xem nhÆ° kháº£ nÄƒng bao phá»§ nhiá»u issue quan trá»ng trong cĂ¹ng code change.

## 6. Results

Káº¿t quáº£ cho tháº¥y RAG cáº£i thiá»‡n accuracy rĂµ nháº¥t so vá»›i LLM Ä‘á»™c láº­p, dĂ¹ static analyzer váº«n cĂ³ accuracy cao hÆ¡n á»Ÿ cĂ¡c lá»—i theo rule. Llama3-70B Ä‘áº¡t Cohen's kappa 0.72 so vá»›i human assessment, nĂªn Ä‘Æ°á»£c dĂ¹ng Ä‘á»ƒ má»Ÿ rá»™ng Ä‘Ă¡nh giĂ¡ toĂ n bá»™ test set. Vá» coverage, DAT cĂ³ nhiá»u review Rank 1, RAG cĂ³ pháº§n lá»›n review á»Ÿ Rank 1 hoáº·c Rank 2, cĂ²n NCO chá»§ yáº¿u á»Ÿ má»©c trung bĂ¬nh. NhĂ¬n chung, hybrid strategy giĂºp káº¿t há»£p báº±ng chá»©ng tá»« static analyzer vá»›i kháº£ nÄƒng diá»…n giáº£i cá»§a LLM.

## 7. Limitations

NghiĂªn cá»©u chá»§ yáº¿u thá»­ trĂªn Java vĂ  hai static analyzers, nĂªn kháº£ nÄƒng Ă¡p dá»¥ng cho nhiá»u ngĂ´n ngá»¯ hoáº·c framework khĂ¡c cáº§n kiá»ƒm chá»©ng thĂªm. ÄĂ¡nh giĂ¡ dá»±a má»™t pháº§n vĂ o LLM-as-a-judge nĂªn váº«n cĂ³ rá»§i ro bias. DAT vĂ  NCO khĂ´ng luĂ´n cáº£i thiá»‡n accuracy, cĂ²n RAG phá»¥ thuá»™c cháº¥t lÆ°á»£ng static analyzer output.

## 8. Ideas Learned for Our Prototype

Paper nĂ y ráº¥t sĂ¡t prototype AI Review hackathon. Pipeline nĂªn cháº¡y source scanner vĂ  static checks trÆ°á»›c, sau Ä‘Ă³ Ä‘Æ°a káº¿t quáº£ cĂ³ báº±ng chá»©ng vĂ o LLM Ä‘á»ƒ sinh `issues` vĂ  `suggestions`. CĂ¡ch nĂ y giĂºp giáº£m hallucination vĂ¬ LLM khĂ´ng chá»‰ Ä‘oĂ¡n tá»« prompt mĂ  cĂ²n dá»±a trĂªn rule/static signal. Output JSON nĂªn tĂ¡ch rĂµ issue do static check phĂ¡t hiá»‡n vĂ  lá»i giáº£i thĂ­ch/gá»£i Ă½ do LLM diá»…n giáº£i. Prototype váº«n pháº£i ghi rĂµ feedback lĂ  tham kháº£o, khĂ´ng thay tháº¿ Judge.

VĂ¬ váº­y, paper nĂ y phĂ¹ há»£p vá»›i Ä‘á» tĂ i vĂ¬ nĂ³ cá»§ng cá»‘ hÆ°á»›ng thiáº¿t káº¿ hybrid: cháº¡y static checks trÆ°á»›c, sau Ä‘Ă³ dĂ¹ng LLM diá»…n giáº£i vĂ  sinh gá»£i Ă½, giĂºp giáº£m hallucination trong AI Review.
