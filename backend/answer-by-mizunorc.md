# Open questions
#### It's 1 am in the midnight. You receive alerts of 99.3% disk usage. What would you do about it?

> Suppose the alert is from an ubuntu server, I will first remove unnecessary files from the server. For example, running command: sudo apt-get autoremove --purge.

#### A service depends on library a,b,c and d. Library d has been reported by CVE (like heartbleed or CPU Meltdown CVE-2017-5754) and recommended an update. What steps will you take before doing such update?

> 1. Build a test environment for the service.
> 1. Run test cases of the service on test environment and confirm all passed.
> 1. Update library d on test environment.
> 1. Run test cases of the service on test environment and confirm all passed again.
> 1. If all test cases pass, update library d on production server of the service and finish.
> 1. Esle find problem(s) and create new test case(s) for the service.
> 1. Go back to step 4 and continue

#### If you have **"unlimited"** funding to start a new business, what kind of projects would you do?

> Virtual department store.

# Technical questions

#### In php, what are the result of these? Try php -i

> for php 7.0.3 
> $a=""; echo isset($a); Result: 1
> $a=0; empty($a); Result: 1
> $a=""; is_null($a); Result:
> $a=""; if($a) echo "1"; else echo "0"; Result 0
> $a="+886"; if(is_numeric(+886)) echo "is numeric"; else "not numeric"; Result: is numeric

#### In php, what is difference between array $a + array $b to array_merge($a,$b) ?

> ##### array $a + array $b
> if there are same index exist both in $a and $b, element in $a will replace element in $b.
> ##### array_merge($a,$b)
> if there are same manual index exist both in $a and $b, element in $b will replace element in $a.
> Indexes of other elements in $a and $b will be regenerated.


#### What is the year 2038 problem?
> This is a problem that Unix time stored by signed 32-bit integer will encountered on 2038-01-09.
Unix time represents a time point as how many seconds it has been from 1970-01-01 00:00:00 UTC. If we store this value into a signed 32-bit integer, the latest representable time point is 2038-01-09 03:14:07 UTC since the capacity is not enough for the total seconds. Therefore, timepoint after 2038-01-09 03:14:07 UTC is not representable.
