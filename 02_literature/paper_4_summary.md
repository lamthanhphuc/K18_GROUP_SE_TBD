# Paper 4 Summary

## 1. Paper Information

- Title: Large Language Models (GPT) for Automating Feedback on Programming Assignments
- Authors: Maciej Pankiewicz, Ryan S. Baker
- Year: 2023
- Venue/Source: ICCE 2023 - The 31st International Conference on Computers in Education; arXiv preprint
- Link: https://library.apsce.net/index.php/ICCE/article/view/950
- PDF Link: https://library.apsce.net/index.php/ICCE/article/download/950/4676
- DOI: https://doi.org/10.58459/icce.2023.950

## 2. Problem

Sinh feedback cĂ¡ nhĂ¢n hĂ³a cho bĂ i láº­p trĂ¬nh cá»§a sinh viĂªn lĂ  khĂ³ vĂ¬ code cĂ³ cĂº phĂ¡p phá»©c táº¡p, cĂ³ nhiá»u cĂ¡ch giáº£i Ä‘Ăºng, vĂ  lá»—i thÆ°á»ng phá»¥ thuá»™c vĂ o tráº¡ng thĂ¡i bĂ i lĂ m hiá»‡n táº¡i. Paper nghiĂªn cá»©u liá»‡u GPT-3.5 cĂ³ thá»ƒ tá»± Ä‘á»™ng táº¡o hint há»¯u Ă­ch cho sinh viĂªn trong má»™t automated assessment platform hay khĂ´ng.

## 3. Method

TĂ¡c giáº£ tĂ­ch há»£p GPT-3.5 vĂ o ná»n táº£ng cháº¥m bĂ i láº­p trĂ¬nh Ä‘á»ƒ sinh personalized hints cho sinh viĂªn. Thiáº¿t káº¿ lĂ  experimental study: nhĂ³m experimental Ä‘Æ°á»£c báº­t GPT hints á»Ÿ má»™t sá»‘ bĂ i, sau Ä‘Ă³ so sĂ¡nh hĂ nh vi vĂ  káº¿t quáº£ vá»›i feedback thÆ°á»ng cá»§a platform. Paper khĂ´ng chá»‰ xem GPT tráº£ lá»i Ä‘Ăºng hay khĂ´ng, mĂ  cĂ²n xem sinh viĂªn dĂ¹ng feedback nhÆ° tháº¿ nĂ o vĂ  cĂ³ dáº¥u hiá»‡u phá»¥ thuá»™c vĂ o GPT hay khĂ´ng.

## 4. Dataset / Input

Input lĂ  submissions cá»§a sinh viĂªn trĂªn cĂ¡c programming assignments trong automated assessment platform. Nguá»“n Ä‘Ă£ xem khĂ´ng nĂªu Ä‘áº§y Ä‘á»§ sá»‘ lÆ°á»£ng sinh viĂªn/submission trong abstract; vĂ¬ váº­y khĂ´ng ghi sá»‘ cá»¥ thá»ƒ. Dá»¯ liá»‡u quan trá»ng gá»“m tráº¡ng thĂ¡i bĂ i lĂ m, hint do GPT sinh, feedback thÆ°á»ng cá»§a platform, sá»‘ láº§n submit, thá»i gian giáº£i vĂ  pháº£n há»“i/rating cá»§a sinh viĂªn.

## 5. Metrics

Metrics gá»“m Ä‘Ă¡nh giĂ¡ usefulness cá»§a GPT-generated hints tá»« sinh viĂªn, má»©c Ä‘á»™ sá»­ dá»¥ng regular feedback, tá»· lá»‡ successful submissions qua cĂ¡c attempt, thá»i gian giáº£i bĂ i, kháº£ nÄƒng giáº£i Ä‘Ăºng khi GPT hints khĂ´ng cĂ²n Ä‘Æ°á»£c báº­t, vĂ  affective state cá»§a sinh viĂªn.

## 6. Results

Sinh viĂªn Ä‘Ă¡nh giĂ¡ GPT hints lĂ  há»¯u Ă­ch. NhĂ³m experimental dĂ¹ng Ă­t regular feedback hÆ¡n vĂ  cĂ³ káº¿t quáº£ tá»‘t hÆ¡n vá» tá»· lá»‡ successful submissions á»Ÿ cĂ¡c task cĂ³ GPT hints. Khi GPT feedback bá»‹ táº¯t á»Ÿ má»™t sá»‘ task, nhĂ³m tá»«ng dĂ¹ng GPT cáº§n Ă­t thá»i gian hÆ¡n Ä‘á»ƒ giáº£i bĂ i, nhÆ°ng ban Ä‘áº§u cĂ³ kháº£ nÄƒng giáº£i Ä‘Ăºng tháº¥p hÆ¡n, cho tháº¥y nguy cÆ¡ over-reliance. Sau nhiá»u attempt, nhĂ³m nĂ y váº«n báº¯t ká»‹p tá»· lá»‡ Ä‘Ăºng. Paper cÅ©ng bĂ¡o cĂ¡o GPT hints khĂ´ng táº¡o áº£nh hÆ°á»Ÿng Ä‘Ă¡ng ká»ƒ tá»›i affective state.

## 7. Limitations

Feedback do LLM sinh cĂ³ thá»ƒ sai, chung chung hoáº·c khiáº¿n sinh viĂªn phá»¥ thuá»™c náº¿u khĂ´ng Ä‘Æ°á»£c thiáº¿t káº¿ cáº©n tháº­n. Bá»‘i cáº£nh lĂ  programming assignments trong giĂ¡o dá»¥c, khĂ´ng pháº£i hackathon full repository. Paper cÅ©ng khĂ´ng chá»©ng minh GPT cĂ³ thá»ƒ thay tháº¿ giáº£ng viĂªn/mentor trong Ä‘Ă¡nh giĂ¡ cuá»‘i cĂ¹ng.

## 8. Ideas Learned for Our Prototype

Vá»›i hackathon, AI Review nĂªn viáº¿t feedback theo hÆ°á»›ng dá»… hiá»ƒu, cĂ³ tĂ­nh hÆ°á»›ng dáº«n vĂ  giĂºp participant cáº£i thiá»‡n bĂ i ná»™p. CĂ¡c trÆ°á»ng `summary`, `issues` vĂ  `suggestions` nĂªn trĂ¡nh ngĂ´n ngá»¯ nhÆ° káº¿t luáº­n cháº¥m Ä‘iá»ƒm tuyá»‡t Ä‘á»‘i. `review_score` náº¿u cĂ³ chá»‰ nĂªn lĂ  tĂ­n hiá»‡u tham kháº£o cho mentor/Judge, khĂ´ng tá»± Ä‘á»™ng quyáº¿t Ä‘á»‹nh ranking. Prototype cÅ©ng nĂªn cáº£nh bĂ¡o ráº±ng feedback AI cĂ³ thá»ƒ sai vĂ  cáº§n Ä‘Æ°á»£c con ngÆ°á»i kiá»ƒm tra.

VĂ¬ váº­y, paper nĂ y phĂ¹ há»£p vá»›i Ä‘á» tĂ i vĂ¬ nĂ³ giĂºp Ä‘á»‹nh hÆ°á»›ng cĂ¡ch viáº¿t feedback dá»… hiá»ƒu cho Participant vĂ  Mentor trong hackathon, Ä‘á»“ng thá»i nháº¥n máº¡nh ráº±ng AI feedback cáº§n human oversight.
