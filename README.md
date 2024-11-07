This tutorial is inspired by this [video](https://www.youtube.com/watch?v=_8lJ5lp8P0U&list=WL&index=150&t=1326s)

It's just very fast crash course to get hands dirty and work with redis-cli

# Redis-CLI (command line interface) commands:</br>

## 1] Normal Storing & Retrieving:
- set <key> <value>
set specific value for specific key</br>
e.g: set username maamoun_haj_najeeb</br>
- get <key>
get the value of that key</br>
e.g: get username</br>
the previous command will return maamoun_haj_najeeb</br>
- keys *:
show all the keys in the redis storage</br>

## 2] Storing & Retrieving With HSet Data Structure:
- hset <father_key> <child_key_1> <value> <child_key_2> <value>
 <child_key_3> <value></br>
explain: hset command use the redis HSet data structure to store one/multiple key-value pairs related to one key.</br>
e.g: hset users user_1 token_1 user_2 token_2 user_3 token_3</br>
this command will store them like this:</br>
```json
{
"users": 
	{
		"user_1": "token_1",
		"user_2": "token_2",
		"user_3": "token_3"
	}
}
```
- hget <father_key> <child_key>
e.g: hget users user_1</br>
this command witll return token_1</br>
- hgetall <father_key>:
explain: we can get all the father_key info with this command</br>
e.g: hgetall users</br>
previous command will return:</br>
* 1) "user_1"</br>
* 2) "token_1"</br>
* 3) "user_2"</br>
* 4) "token_2"</br>
* 5) "user_3"</br>
* 6) "token_3"</br>

## Delete command:
- del <key_name>
e.g: del username</br>

## Expire command:
- expire <key_name> <time_in_seconds>
e.g: expire users 10</br>
explain: the previous command will make users key with it's ascoiated value deleted within 10 seconds. So, if I query on users key after 10 seconds redis will not find it.</br>



