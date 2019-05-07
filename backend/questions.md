# Open questions

### Choose 3 of them to answer via submitting pull requests.

- Design a one-time-download link for Dropbox.

- If you are asked to design a Google Drive like service, which database will you choose and why? 

- How did you decide log level (in your experience) ?
	- **Ans:** In production must keep raw request, raw response and unexpected errors. Other than that, known errors are INFO level. Out going traffic to 3rd party services like AWS asynchronous read/write, payment, login with 3rd-party ID like facebook should be INFO level. Other details all in debug level.

- A API request containing 1323 records need to be executed. Users are complaining about the response time. How do you speed up? What would you do if #617 of the 1323 records goes wrong by the way you are proposing?

- Would you choose to make the above API a micro service? If not, why not ?

- It's 1 am in the midnight. You receive alerts of 99.3% disk usage. What would you do about it?

- **About learning new stuff**, have you been mining any coin ? AI ? Tensorflow? Kubernetes? or Live streaming? Ever being a YouTuber? Which mobile payment you're using and why? What do you think of these industries? 
	- **Ans:** I watched every Google I/O events and tried Bitcoin since 2014. Noticed the rising of ethereum since 2017. I think the live streaming industry is a hype but will last for a very long time. Content of 3G (Girls, gambling, gaming) will never change, only the underlying technology and business model will change.

- Have you participated in any technical projects (not related to your school) during under graduate? 
 
- You receive system alerts about sudden traffic. After tracing logs you find the requests are coming from a specific version of App. What are the possible reasons and how do you fix it? Can you determine whether this is an APT attack or not ?

- In contrast, system alerts about no traffic at all today. What are the possible reasons and how do you fix it?

- A service depends on library a,b,c and d. Library d has been reported by CVE (like heartbleed or CPU Meltdown CVE-2017-5754) and recommended an update. What steps will you take before doing such update?
	- **Ans:** First i will read through the CVE report and check if patching library d affect the service. Did other company report issue after patching. Then, try patching the library in dev environment or beta environment.

- If you have **"unlimited"** funding to start a new business, what kind of projects would you do?

- If you are a Venture Capital (VC), how much would you invest our company ?

# Technical questions

### Choose 3 of them to answer via submitting pull requests.

- In php, what are the result of these? Try php -i
	- $a=""; echo isset($a);
	- $a=0; empty($a);
	- $a=""; is\_null($a); 
	- $a=""; if($a) echo "1"; else echo "0";
	- $a="+886"; if(is\_numeric(+886)) echo "is numeric"; else "not numeric";
	- **Ans**: 

- In php, what is difference between array $a + array $b to array_merge($a,$b) ? See: http://blog.hsatac.net/2012/11/php-array-plus-array-versus-array-merge/

- What is the year 2038 problem? 
	- **Ans**: Like Y2K, 2038 issue is an overflow issue on 32-bit machine. Resolved after upgrading to 64-bit machine.

- Please explain JAX-RS Lifecycle. If you want to log something, which stage would you choose to do it ? filter stage or interceptor stage ?
	- **Ans**: 

- Please write pseudo-code of how to generate a self-signed CA. Keywords are **openssl\_pkey\_new, openssl\_csr\_new, openssl\_csr_sign**.
