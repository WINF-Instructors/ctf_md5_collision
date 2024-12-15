# ctf_md5_collision

CTF bases on collision in MD5: Flag (in ./flag.txt on server) is revealed if we can go into the path of the program where we login as a user, but the username does not match the one in the list of users.
The idea is that for the check, the program just compares the MD5 hash and checks the password. So, if we register a user and then try to login with a user whose username differs from the registered user, but has the same MD5 hash, the flag is revealed.
It works with 

{"option": "register"}

{"username":"TEXTCOLLBYfGiJUETHQ4hAcKSMd5zYpgqf1YRDhkmxHkhPWptrkoyz28wnI9V0aHeAuaKnak", "password":"1234"}

{"option":"login"}

{"username":"TEXTCOLLBYfGiJUETHQ4hEcKSMd5zYpgqf1YRDhkmxHkhPWptrkoyz28wnI9V0aHeAuaKnak", "password": "1234"}

This is because both usernames have the same MD5 hash, but they are different.
For possible collisions, just google MD5 collisions or use tools like hashclash (https://marc-stevens.nl/p/hashclash/).
