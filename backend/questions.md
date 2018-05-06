# Open questions

### Choose 3 of them to answer via submitting pull requests.

- If you are asked to design a Google Drive like service, which database will you choose and why? 

- How did you decide log level (in your experience) ?

- A API request containing 1323 records need to be executed. Users are complaining about the response time. How do you speed up? What would you do if #617 of the 1323 records goes wrong by the way you are proposing?

- Would you choose to make the above API a micro service? If not, why not ?

- It's 1 am in the midnight. You receive alerts of 99.3% disk usage. What would you do about it?

- **About learning new stuff**, have you been mining any coin ? AI ? Tensorflow? Kubernetes? or Live streaming? Ever being a YouTuber? Which mobile payment you're using and why? What do you think of these industries? 
- A: 1.我有在使用coinpot挖彼特幣和領取水龍頭硬幣。2.有在學深度學習並且會使用tensorflow。3.行動支付的話有在使用街口支付，指定店家的話有不錯的回饋。討論我本身有參與的技術：1.我覺得虛擬貨幣本身還在法律無法管控的階段，有太多不確定性和炒作在其中，本身是以沾一下的態度參與，等穩定的時候再以傳統金融商品的角度去看待。2.AI產業的話必定是個趨勢，本身也是在退伍後持續開始學習，希望可以用AI做許多有想過的事情。3.行動支付必定是個趨勢，小時候就看過那種對未來的刻化的故事書，減少貨幣使用的科技會使生活越便利，不過像知名的paypal目前尚存在洗錢的問題。
- Have you participated in any technical projects (not related to your school) during under graduate? 
 
- You receive system alerts about sudden traffic. After tracing logs you find the requests are coming from a specific version of App. What are the possible reasons and how do you fix it? Can you determine whether this is an APT attack or not ?

- In contrast, system alerts about no traffic at all today. What are the possible reasons and how do you fix it?

- A service depends on library a,b,c and d. Library d has been reported by CVE (like heartbleed or CPU Meltdown CVE-2017-5754) and recommended an update. What steps will you take before doing such update?

- If you have **"unlimited"** funding to start a new business, what kind of projects would you do?
A: 目前比較想從事的是將AI應用在體育上面，之前有看過國外將籃球員的場上動作用電腦記錄下來，分析其在什麼位置、什麼動作上的效率比較高，戰術上的好壞也能被分析出來，甚至可以在比賽中應用，勇士隊在2014-2015奪冠的賽季就有使用這項系統。台灣目前還處於人工記錄的階段，開發這項系統在任何運動上都有大大增加指導效率的好處。
- If you are a Venture Capital (VC), how much would you invest our company ?

# Technical questions

### Choose 3 of them to answer via submitting pull requests.

- In php, what are the result of these? Try php -i
- 參考線上編譯器http://www.writephponline.com/ :
	- $a=""; echo isset($a);
	- A: 1
	- $a=0; empty($a);
	- A: nothing to show
	- $a=""; is\_null($a);
	- A: nothing to show
	- $a=""; if($a) echo "1"; else echo "0";
	- A: 0
	- $a="+886"; if(is\_numeric(+886)) echo "is numeric"; else "not numeric";
	

- In php, what is difference between array $a + array $b to array_merge($a,$b) ? See: http://blog.hsatac.net/2012/11/php-array-plus-array-versus-array-merge/
- A: 參考連結得到結論: 1.merege(a,b)的行為是先以append把b放在後面，若有key相同的element則以b來取代a，沒有key的element則在後面重新給定index。
2.array a+b的行為也是先以append把b放在後面，有相同key和index的element的b直接砍掉，且不會重新排序。

- What is the year 2038 problem? 
- A:參考維基百科，舊的程式資料是以32BIT儲存的，以時間來說會以2^32-1秒為一個循環，當約2038年的時候一些軟體會在時間上回到起始的1901年

- Please explain JAX-RS Lifecycle. If you want to log something, which stage would you choose to do it ? filter stage or interceptor stage ?

- Please write pseudo-code of how to generate a self-signed CA. Keywords are **openssl\_pkey\_new, openssl\_csr\_new, openssl\_csr_sign**.
