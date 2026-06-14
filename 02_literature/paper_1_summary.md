# Paper 1 Summary

## 1. Paper Information

- Title: Expectations, Outcomes, and Challenges of Modern Code Review
- Authors: Alberto Bacchelli, Christian Bird
- Year: 2013
- Venue/Source: 35th International Conference on Software Engineering (ICSE 2013), IEEE
- Link: https://ieeexplore.ieee.org/document/6606617
- PDF Link: https://zenodo.org/records/1401198/files/paper.pdf
- DOI: https://doi.org/10.1109/ICSE.2013.6606617

## 2. Problem

Paper nghiĂªn cá»©u modern code review trong bá»‘i cáº£nh cĂ´ng nghiá»‡p, khi review khĂ´ng cĂ²n lĂ  inspection náº·ng theo kiá»ƒu há»p dĂ i mĂ  trá»Ÿ thĂ nh quy trĂ¬nh nháº¹, dá»±a trĂªn cĂ´ng cá»¥, diá»…n ra thÆ°á»ng xuyĂªn trong phĂ¡t triá»ƒn pháº§n má»m. Váº¥n Ä‘á» chĂ­nh lĂ  hiá»ƒu developer vĂ  manager ká»³ vá»ng gĂ¬ á»Ÿ code review, review thá»±c táº¿ táº¡o ra káº¿t quáº£ gĂ¬, vĂ  nhá»¯ng khĂ³ khÄƒn nĂ o lĂ m review kĂ©m hiá»‡u quáº£.

ÄĂ¢y lĂ  ná»n táº£ng quan trá»ng cho Ä‘á» tĂ i vĂ¬ prototype AI Review hackathon cÅ©ng khĂ´ng thay tháº¿ reviewer/Judge, mĂ  chá»‰ há»— trá»£ táº¡o feedback tham kháº£o Ä‘á»ƒ giáº£m táº£i bÆ°á»›c Ä‘á»c code ban Ä‘áº§u.

## 3. Method

TĂ¡c giáº£ thá»±c hiá»‡n nghiĂªn cá»©u thá»±c nghiá»‡m táº¡i Microsoft: quan sĂ¡t developer review code, phá»ng váº¥n bĂ¡n cáº¥u trĂºc, phĂ¢n loáº¡i thá»§ cĂ´ng ná»™i dung comment trong cĂ¡c cuá»™c tháº£o luáº­n code review, vĂ  kháº£o sĂ¡t developer/manager. CĂ¡ch tiáº¿p cáº­n lĂ  empirical study, táº­p trung vĂ o hĂ nh vi review tháº­t thay vĂ¬ chá»‰ mĂ´ táº£ quy trĂ¬nh lĂ½ thuyáº¿t.

## 4. Dataset / Input

Input nghiĂªn cá»©u gá»“m dá»¯ liá»‡u Ä‘á»‹nh tĂ­nh vĂ  Ä‘á»‹nh lÆ°á»£ng tá»« cĂ¡c nhĂ³m phĂ¡t triá»ƒn pháº§n má»m táº¡i Microsoft: phiĂªn quan sĂ¡t review, interview, 570 review comments Ä‘Æ°á»£c phĂ¢n loáº¡i thá»§ cĂ´ng, cĂ¹ng kháº£o sĂ¡t trĂªn 165 managers vĂ  873 programmers. Dá»¯ liá»‡u pháº£n Ă¡nh mĂ´i trÆ°á»ng cĂ´ng nghiá»‡p, khĂ´ng pháº£i dá»¯ liá»‡u hackathon hay classroom.

## 5. Metrics

Paper khĂ´ng dĂ¹ng metric ML nhÆ° precision/recall. CĂ¡c tiĂªu chĂ­ phĂ¢n tĂ­ch chĂ­nh lĂ  nhĂ³m Ä‘á»™ng cÆ¡ review, nhĂ³m outcome cá»§a review comment, nhu cáº§u hiá»ƒu code/change cá»§a reviewer, vĂ  táº§n suáº¥t cĂ¡c loáº¡i feedback. Káº¿t quáº£ Ä‘Æ°á»£c tá»•ng há»£p tá»« phĂ¢n loáº¡i comment, kháº£o sĂ¡t vĂ  phá»ng váº¥n.

## 6. Results

Káº¿t quáº£ chĂ­nh cho tháº¥y tĂ¬m defect váº«n lĂ  Ä‘á»™ng cÆ¡ quan trá»ng nháº¥t, nhÆ°ng outcome thá»±c táº¿ cá»§a review khĂ´ng chá»‰ lĂ  tĂ¬m lá»—i. Review cĂ²n táº¡o ra knowledge transfer, tÄƒng team awareness, cáº£i thiá»‡n giáº£i phĂ¡p, vĂ  giĂºp thĂ nh viĂªn hiá»ƒu há»‡ thá»‘ng tá»‘t hÆ¡n. Paper cÅ©ng nháº¥n máº¡nh "code and change understanding" lĂ  thĂ¡ch thá»©c trung tĂ¢m: reviewer cáº§n hiá»ƒu ngá»¯ cáº£nh thay Ä‘á»•i, intent cá»§a ngÆ°á»i viáº¿t code, tĂ¡c Ä‘á»™ng tá»›i há»‡ thá»‘ng, vĂ  nhiá»u nhu cáº§u nĂ y chÆ°a Ä‘Æ°á»£c cĂ´ng cá»¥ review há»— trá»£ tá»‘t.

## 7. Limitations

NghiĂªn cá»©u táº­p trung vĂ o Microsoft nĂªn cĂ³ thá»ƒ khĂ´ng Ä‘áº¡i diá»‡n hoĂ n toĂ n cho open-source, lá»›p há»c, hoáº·c hackathon. Paper cÅ©ng khĂ´ng Ä‘Ă¡nh giĂ¡ má»™t há»‡ thá»‘ng AI tá»± Ä‘á»™ng, vĂ¬ thá»i Ä‘iá»ƒm nghiĂªn cá»©u chá»§ yáº¿u phĂ¢n tĂ­ch quy trĂ¬nh human code review vĂ  tool-based review truyá»n thá»‘ng.

## 8. Ideas Learned for Our Prototype

Prototype nĂªn Ä‘Æ°á»£c Ä‘á»‹nh vá»‹ lĂ  cĂ´ng cá»¥ há»— trá»£ hiá»ƒu code nhanh hÆ¡n, khĂ´ng pháº£i bá»™ cháº¥m Ä‘iá»ƒm tá»± Ä‘á»™ng thay Judge. CĂ¡c trÆ°á»ng `summary`, `repository_structure_notes`, `issues`, vĂ  `suggestions` nĂªn giĂºp mentor/reviewer náº¯m intent, cáº¥u trĂºc repo, rá»§i ro chĂ­nh vĂ  gá»£i Ă½ cáº£i thiá»‡n. VĂ¬ paper chá»‰ ra review thá»§ cĂ´ng cĂ³ thá»ƒ tá»‘n thá»i gian vĂ  cháº¥t lÆ°á»£ng khĂ´ng Ä‘á»“ng Ä‘á»u, AI Review cĂ³ thá»ƒ dĂ¹ng Ä‘á»ƒ táº¡o feedback ban Ä‘áº§u, nhÆ°ng quyáº¿t Ä‘á»‹nh ranking hoáº·c káº¿t quáº£ hackathon váº«n cáº§n con ngÆ°á»i kiá»ƒm chá»©ng.

VĂ¬ váº­y, paper nĂ y phĂ¹ há»£p vá»›i Ä‘á» tĂ i vĂ¬ nĂ³ cung cáº¥p ná»n táº£ng vá» má»¥c tiĂªu vĂ  thĂ¡ch thá»©c cá»§a modern code review, giĂºp Ä‘á»‹nh vá»‹ AI Review nhÆ° cĂ´ng cá»¥ há»— trá»£ hiá»ƒu code vĂ  sinh feedback tham kháº£o, khĂ´ng thay tháº¿ Judge/ranking.
