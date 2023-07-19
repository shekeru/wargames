# Bandit

## Level 0 -> 1

The goal of this level is for you to log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. Once logged in, go to the Level 1 page to find out how to beat Level 1. The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

```sh
cat readme
```

- Link: <https://overthewire.org/wargames/bandit/bandit1.html>
- Connect: `ssh bandit0@bandit.labs.overthewire.org -p 2220`
- Password: `bandit0`


## Level 1 -> 2

The password for the next level is stored in a file called - located in the home directory

```sh
cat ./-
```

- Link: <https://overthewire.org/wargames/bandit/bandit2.html>
- Connect: `ssh bandit1@bandit.labs.overthewire.org -p 2220`
- Password: `NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL`

## Level 2 -> 3

The password for the next level is stored in a file called spaces in this filename located in the home directory

```sh
cat "spaces in this filename"
```

- Link: <https://overthewire.org/wargames/bandit/bandit3.html>
- Connect: `ssh bandit2@bandit.labs.overthewire.org -p 2220`
- Password: `rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi`


## Level 3 -> 4

The password for the next level is stored in a hidden file in the inhere directory.

```sh
cat "cat -u inhere/.* 2>/dev/null"
```

- Link: <https://overthewire.org/wargames/bandit/bandit4.html>
- Connect: `ssh bandit3@bandit.labs.overthewire.org -p 2220`
- Password: `aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG`

## Level 4 -> 5

The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

```sh
grep -h "^[[:alnum:]]*$" -r inhere
```

- Link: <https://overthewire.org/wargames/bandit/bandit5.html>
- Connect: `ssh bandit4@bandit.labs.overthewire.org -p 2220`
- Password: `2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe`

## Level 5 -> 6

The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not executable

```sh
cat $(find . -size 1033c ! -executable) | head -n 1
```

- Link: <https://overthewire.org/wargames/bandit/bandit6.html>
- Connect: `ssh bandit5@bandit.labs.overthewire.org -p 2220`
- Password: `lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR`

## Level 6 -> 7

The password for the next level is stored somewhere on the server and has all of the following properties:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size

```sh
cat $(find / -size 33c -group bandit6 -user bandit7 2>&-)
```

- Link: <https://overthewire.org/wargames/bandit/bandit7.html>
- Connect: `ssh bandit6@bandit.labs.overthewire.org -p 2220`
- Password: `P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU`

## Level 7 -> 8

The password for the next level is stored in the file data.txt next to the word millionth

```sh
sed -n 's/millionth\t//p' data.txt
```

- Link: <https://overthewire.org/wargames/bandit/bandit8.html>
- Connect: `ssh bandit7@bandit.labs.overthewire.org -p 2220`
- Password: `z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S`

## Level 8 -> 9

```sh

```

- Link: <https://overthewire.org/wargames/bandit/bandit9.html>
- Connect: `ssh bandit8@bandit.labs.overthewire.org -p 2220`
- Password: `TESKZC0XvTetK0S9xNwm25STk5iWrBvP`

<!-- 

ssh bandit7@bandit.labs.overthewire.org -p 2220
HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs

  Level 8
Challenge: sort data.txt | uniq -u

ssh bandit8@bandit.labs.overthewire.org -p 2220
cvX2JJa4CFALtqS87jk27qwqGhBM9plV

  Level 9
Challenge: strings data.txt | sed -n 's/^==.*\s//p' | tail -n 1

ssh bandit9@bandit.labs.overthewire.org -p 2220
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

  Level 10
Challenge: cat data.txt | base64 -d | sed -n 's/^.*\s//p'

ssh bandit10@bandit.labs.overthewire.org -p 2220
truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk

  Level 11
Challenge: cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m' | sed -n 's/^.*\s//p'

ssh bandit11@bandit.labs.overthewire.org -p 2220
IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR

  Level 12
Challenge: xxd -r ~/data.txt | gzip -d | bzip2 -d | gzip -d | tar -xO | tar -xO | tar -xjO | gzip -d

ssh bandit12@bandit.labs.overthewire.org -p 2220
5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu


  Level 13
Challenge: ssh -i sshkey.private -o StrictHostKeyChecking=no bandit14@localhost cat /etc/bandit_pass/bandit14

ssh bandit13@bandit.labs.overthewire.org -p 2220
8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL

  Level 14
Challenge: netcat localhost 30000 < /etc/bandit_pass/bandit14

ssh bandit14@bandit.labs.overthewire.org -p 2220
4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e

  Level 15
Challenge: openssl s_client -connect localhost:30001 -ign_eof < /etc/bandit_pass/bandit15

ssh bandit15@bandit.labs.overthewire.org -p 2220
BfMYroe26WYalil77FoDi9qh59eK5xNr

  Level 16
Challenge: nmap -p 31000-32000 localhost | sed -e 's/\/tcp.*$//p' -n | while read line; do
  openssl s_client -connect localhost:$line -quiet < /etc/bandit_pass/bandit16;
  done 2>/dev/null | tail -n +2
Note: Save Key Locally

ssh bandit16@bandit.labs.overthewire.org -p 2220
cluFn7wTiGryunymYOu4RcffSxQluehd

Level 17
Challenge: diff passwords.* | sed -n '2s/..//p'

ssh bandit17@bandit.labs.overthewire.org -p 2220
xLYVMN9WE5zQ5vHacb0sZEVqbrp7nBTn

Level 18
Challenge: diff passwords.* | sed -n '2s/..//p'

ssh bandit18@bandit.labs.overthewire.org -p 2220
kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd

http://overthewire.org/wargames/bandit/ -->
