# Open questions

### Choose 3 of them to answer via submitting pull requests.

- If you are asked to design a Google Drive like service, which database will you choose and why? 

- How did you decide log level (in your experience) ?

- A API request containing 1323 records need to be executed. Users are complaining about the response time. How do you speed up? What would you do if #617 of the 1323 records goes wrong by the way you are proposing?

    **Answer:** If the execution result is not necessary to return immediately in this response, it could use queue to resolve long response time. A better solution is to redesign it to decrease the amount of the to-be-executed data. Once one of records goes wrong, all operations in this api request should rollback. Partial execution might cause confusion to API client and make it hard to be traced.

- Would you choose to make the above API a micro service? If not, why not ?

    **Answer:** If the API is always in its highest loading status in system, extracting it out as a micro service is a good solution. One point is it may need a more suitable structure. Another one is if it is big enough to isolate, it should serve as a new service to prevent chaos and make it easy to maintain.

- It's 1 am in the midnight. You receive alerts of 99.3% disk usage. What would you do about it?

    **Answer:**
        1. Check what kind of service is provided on this server.
        2. Run monitor tool to check if it is still increasing.
        3. Trace log.
        4. Check if the bigger file is in the right place and if it is supposed to be that big base on server's function.
        5. Check why auto-scaling is not working.
        6. Check who has logged in the server.

- **About learning new stuff**, have you been mining any coin ? AI ? Tensorflow? Kubernetes? or Live streaming? Ever being a YouTuber? Which mobile payment you're using and why? What do you think of these industries? 

- Have you participated in any technical projects (not related to your school) during under graduate? 
 
- You receive system alerts about sudden traffic. After tracing logs you find the requests are coming from a specific version of App. What are the possible reasons and how do you fix it? Can you determine whether this is an APT attack or not ?

- In contrast, system alerts about no traffic at all today. What are the possible reasons and how do you fix it?

- A service depends on library a,b,c and d. Library d has been reported by CVE (like heartbleed or CPU Meltdown CVE-2017-5754) and recommended an update. What steps will you take before doing such update?

- If you have **"unlimited"** funding to start a new business, what kind of projects would you do?

- If you are a Venture Capital (VC), how much would you invest our company ?

# Technical questions

### Choose 3 of them to answer via submitting pull requests.

- In php, what are the result of these? Try php -i
	- $a=""; echo isset($a);
        true

	- $a=0; empty($a);
        true

	- $a=""; is\_null($a); 
        false

	- $a=""; if($a) echo "1"; else echo "0";
        0
        false == "" == 0 == NULL //true

        When converting to boolean, the empty string is false. PHP is a weak typing language. Putting a string in a if statement must be careful that sometimes it might cause confusion, for example, if("false") will turn out te be true.

	- $a="+886"; if(is\_numeric(+886)) echo "is numeric"; else "not numeric";
        is numeric

        The first character is considered as the plus sign and variable $a is a positive number. Minus sign would make it the opposite. Another funny thing about is_numeric is scientific notation, for instance, is_numeric('+0e1') === true.

- In php, what is difference between array $a + array $b to array_merge($a,$b) ? See: http://blog.hsatac.net/2012/11/php-array-plus-array-versus-array-merge/

- What is the year 2038 problem? 

    **Answer:** Like Y2K, 32-bit system would crash when 03:14:07 UTC on 19 January 2038 because of lack of bit for recording datetime. 64-bit system won't have the year 2038 problem.

- Please explain JAX-RS Lifecycle. If you want to log something, which stage would you choose to do it ? filter stage or interceptor stage ?

    **Answer:** JAX-RS Lifecycle starts from client rquest and ends in server response. It clearly defines several stages to handle a client request until it returns a server response. Each part has their own responsibility and will be triggered at a specific timing. You can add your customized one if you need. It also can be settled in good order if you have more than one. This standard makes you easy to do your jobs and could put them in the right place.

    Generally, the things we log are request parameters and response data. In this case, filter is a better choise especially by using name-binding annotation. But if you have a special purpose for logging third party services. You should still log it whenever you need no matter which stage it is in.

- Please write pseudo-code of how to generate a self-signed CA. Keywords are **openssl\_pkey\_new, openssl\_csr\_new, openssl\_csr_sign**.
