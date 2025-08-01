# OverTheWire Bandit Wargame: My Learning Journey 🚀

[cite_start]This repository documents my progress through the [OverTheWire Bandit Wargame](https://overthewire.org/wargames/bandit/)[cite: 1, 5]. [cite_start]This game is an excellent resource for learning basic Linux commands and security concepts[cite: 5]. [cite_start]The goal of each level is to find a password to unlock the next one[cite: 5]. [cite_start]If a password is lost, you'll need to restart from a previous level[cite: 5].

[cite_start]Let's dive into the levels! [cite: 5]

---

## Level 0 → Level 1

[cite_start]**Level Goal:** Log into the game using SSH[cite: 6, 7].

**Connection Details:**
* [cite_start]**Host:** `bandit.labs.overthewire.org` [cite: 8]
* [cite_start]**Port:** `2220` [cite: 8]
* [cite_start]**Username:** `bandit0` [cite: 8]
* [cite_start]**Password:** `bandit0` [cite: 8]

**Commands Used:**
* [cite_start]`ssh` [cite: 10]

**Solution:**
1.  [cite_start]Open your terminal (e.g., Kali Linux)[cite: 13].
2.  Type the SSH command with the provided details:
    ```bash
    ssh bandit0@bandit.labs.overthewire.org -p 2220
    ```
3.  [cite_start]When prompted, enter the password `bandit0`[cite: 14].

[cite_start]**Password for Level 1:** `ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5lf` [cite: 58]

---

## Level 1 → Level 2

[cite_start]**Level Goal:** The password for the next level is stored in a file called `readme` located in the home directory[cite: 17]. [cite_start]Use this password to log into `bandit1` using SSH on port 2220[cite: 18].

**Commands Used:**
* [cite_start]`ls` [cite: 20]
* [cite_start]`cat` [cite: 20]

**Solution:**
1.  [cite_start]After logging in as `bandit0`[cite: 25, 26], you are in the home directory.
2.  [cite_start]Use `ls` [cite: 27] [cite_start]or `ls -alps` [cite: 27] to list the files in the current directory.
3.  [cite_start]You will see a file named `readme`[cite: 28].
4.  [cite_start]Use the `cat` command to display its contents[cite: 28, 29]:
    ```bash
    cat readme
    ```
    [cite_start]The `cat` command stands for "concatenate" and is mainly used to display the contents of a file[cite: 28, 29, 32, 33].

[cite_start]**Password for Level 2:** `263JGJPfgU6LtdEvgfWU1XP5yac29mFx` [cite: 96]

[cite_start]**Important Tip:** Create a file for notes and passwords on your local machine, as passwords are not saved automatically and may occasionally change[cite: 21, 22, 23]. [cite_start]Detailed notes are useful for solving challenges, referencing later, or helping others[cite: 24].

---

## Level 2 → Level 3

[cite_start]**Level Goal:** The password for the next level is stored in a file called `-spaces in this filename-` located in the home directory[cite: 100].

**Commands Used:**
* [cite_start]`ls` [cite: 101]
* [cite_start]`cat` [cite: 101]

**Solution:**
1.  Log into `bandit1` using the previous password.
2.  [cite_start]Use `ls -alps` [cite: 67] to list files. [cite_start]You'll observe a file with a leading dash, which can be problematic for `cat`[cite: 108].
3.  To correctly read a file with special characters or leading dashes, you must use `./` to specify the current directory or use quotes or escape characters. [cite_start]The provided solution snippet in the document for `bandit1@bandit:~$ cat ./-` seems to imply a file named just `-` or similar, which resulted in the password[cite: 95, 96].
    ```bash
    cat ./-
    ```
    *(Note: The level goal mentions a file named `-spaces in this filename-`, which would typically require `cat -- -spaces\ in\ this\ filename-` or `cat ./-spaces\ in\ this\ filename-`. The document shows `cat ./-` as the command that retrieved the password.)*

[cite_start]**Password for Level 3:** `MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx` [cite: 116]

---

## Level 3 → Level 4

[cite_start]**Level Goal:** The password for the next level is stored in a hidden file in the `inhere` directory[cite: 119].

**Commands Used:**
* [cite_start]`ls` [cite: 121]
* [cite_start]`cd` [cite: 121]
* [cite_start]`cat` [cite: 121]

**Solution:**
1.  Log into `bandit2` using the previous password.
2.  [cite_start]Use `ls -alps` [cite: 122] to list files and directories. [cite_start]You'll see a directory named `inhere/`[cite: 132].
3.  Change into the `inhere` directory:
    ```bash
    [cite_start]cd inhere [cite: 135]
    ```
4.  [cite_start]Once inside `inhere`, use `ls -al` [cite: 138] [cite_start]to reveal hidden files (files starting with a dot `.` [cite: 146]). [cite_start]You will see a hidden file named `... Hiding-From-You`[cite: 146].
5.  Read the content of the hidden file. Remember to escape the leading dots and spaces:
    ```bash
    [cite_start]cat \.\.\.Hiding-From-You [cite: 163]
    ```

[cite_start]**Password for Level 4:** `2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ` [cite: 164]

---

## Level 4 → Level 5

[cite_start]**Level Goal:** The password for the next level is stored in the only human-readable file in the `inhere` directory[cite: 170].

**Commands Used:**
* [cite_start]`ls` [cite: 172]
* [cite_start]`cd` [cite: 172]
* [cite_start]`file` [cite: 172]
* [cite_start]`cat` [cite: 172]

**Solution:**
1.  Log into `bandit3` using the previous password.
2.  [cite_start]Change into the `inhere` directory[cite: 135].
3.  Use the `file` command with a wildcard to check the file type of all files in the current directory:
    ```bash
    [cite_start]file ./* [cite: 174]
    ```
4.  Examine the output. [cite_start]You are looking for a file that is "ASCII text" (human-readable)[cite: 170]. [cite_start]In this case, `file07` is identified as `ASCII text`[cite: 182].
5.  Read the content of that file using `cat`:
    ```bash
    [cite_start]cat ./-file07 [cite: 187]
    ```

[cite_start]**Password for Level 5:** `40QYVPkXZO0E005pTW81FB8j8lxXGUQw` [cite: 187]

---

## Level 5 → Level 6

**Level Goal:** The password for the next level is stored in a file somewhere under the `inhere` directory and has all of the following properties:
* [cite_start]human-readable [cite: 191]
* [cite_start]1033 bytes in size [cite: 192]
* [cite_start]not executable [cite: 193]

**Commands Used:**
* [cite_start]`find` [cite: 195]
* [cite_start]`cat` [cite: 195]

**Solution:**
1.  Log into `bandit4` using the previous password.
2.  [cite_start]Use the `find` command to search for files with specific properties from the current directory (`.`)[cite: 219].
    * [cite_start]`-type f`: Look for files[cite: 219].
    * [cite_start]`-size 1033c`: Find files exactly 1033 bytes in size[cite: 219].
    * [cite_start]`!-executable`: Files that are NOT executable[cite: 219].
    ```bash
    find . -type f -size 1033c !-executable
    ```
3.  [cite_start]The command will output the path to the file (e.g., `/maybehere07/.file2` [cite: 226]).
4.  Read the content of that file using `cat`:
    ```bash
    [cite_start]cat /maybehere07/.file2 [cite: 227]
    ```

[cite_start]**Password for Level 6:** `HWasnphtq9AVKe0dmk45nxy20cvUa6EG` [cite: 227]

---

## Level 6 → Level 7

**Level Goal:** The password for the next level is stored somewhere on the server and has all of the following properties:
* [cite_start]owned by user `bandit7` [cite: 244]
* [cite_start]owned by group `bandit6` [cite: 245]
* [cite_start]33 bytes in size [cite: 246]

**Commands Used:**
* [cite_start]`find` [cite: 248]
* [cite_start]`cat` [cite: 248]

**Solution:**
1.  Log into `bandit5` using the previous password.
2.  [cite_start]Use `find` to search the entire file system (starting from `/`) for a file with the specified properties[cite: 265].
    * [cite_start]`-type f`: Look for files[cite: 265].
    * [cite_start]`-user bandit7`: Owned by user `bandit7`[cite: 265].
    * [cite_start]`-group bandit6`: Owned by group `bandit6`[cite: 265].
    * [cite_start]`-size 33c`: Exactly 33 bytes in size[cite: 265].
    ```bash
    find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
    ```
    [cite_start]*(Note: `2>/dev/null` is added to suppress "Permission denied" errors for a cleaner output, though the document does not show it. The document does show `find: /sys/kernel/tracing': Permission denied`[cite: 265].)*
3.  [cite_start]The command will find the file: `/var/lib/dpkg/info/bandit7.password`[cite: 266].
4.  Use `cat` to read the content of this file:
    ```bash
    [cite_start]cat /var/lib/dpkg/info/bandit7.password [cite: 266]
    ```

[cite_start]**Password for Level 7:** `morbNTDkSW6jIlUc0ym0dMaLn0lFVAaj` [cite: 266]

---

## Level 7 → Level 8

[cite_start]**Level Goal:** The password for the next level is stored in the file `data.txt` next to the word `millionth`[cite: 270].

**Commands Used:**
* [cite_start]`ls` [cite: 271]
* [cite_start]`cat` [cite: 271]
* [cite_start]`strings` [cite: 271]
* [cite_start]`grep` [cite: 271]

**Solution:**
1.  Log into `bandit6` using the previous password.
2.  [cite_start]Use `ls` [cite: 273] [cite_start]to confirm `data.txt` is present[cite: 274].
3.  [cite_start]The file `data.txt` contains many lines [cite: 294-308]. [cite_start]To find the password efficiently, pipe the output of `strings` (to extract printable characters) to `grep` (to search for "millionth")[cite: 309, 310].
    ```bash
    [cite_start]strings data.txt | grep "millionth" [cite: 310]
    ```
4.  [cite_start]The output will show the word "millionth" followed by the password[cite: 311, 312].

[cite_start]**Password for Level 8:** `dfwvzFQi4mU0wfNbF0e9RoWskMLg7eEc` [cite: 312]

---

## Level 8 → Level 9

[cite_start]**Level Goal:** The password for the next level is stored in the file `data.txt` and is the only line of text that occurs only once[cite: 316].

**Commands Used:**
* [cite_start]`cat` [cite: 317]
* [cite_start]`sort` [cite: 317]
* [cite_start]`uniq` [cite: 317]

**Solution:**
1.  Log into `bandit7` using the previous password.
2.  The goal requires finding a unique line in `data.txt`. [cite_start]This can be achieved by combining `cat`, `sort`, and `uniq` using piping[cite: 320, 321, 322, 323, 324].
    * [cite_start]`cat data.txt`: Displays the file's content[cite: 321].
    * [cite_start]`sort`: Sorts the lines alphabetically[cite: 322].
    * [cite_start]`uniq -c`: Counts the occurrences of each unique line[cite: 323].
3.  Pipe these commands together:
    ```bash
    [cite_start]cat data.txt | sort | uniq -c [cite: 323, 324]
    ```
4.  [cite_start]Look for the line that has a count of `1` at the beginning[cite: 325, 326].

[cite_start]**Password for Level 9:** `4CKMh1JI91bUIZZPXDqGanal4xvAg0JM` [cite: 326]

---

## Level 9 → Level 10

[cite_start]**Level Goal:** The password for the next level is stored in the file `data.txt` in one of the few human-readable strings, preceded by several `=` characters[cite: 331].

**Commands Used:**
* [cite_start]`strings` [cite: 333]
* [cite_start]`grep` [cite: 333]

**Solution:**
1.  Log into `bandit8` using the previous password.
2.  [cite_start]Use `strings` to extract printable strings from `data.txt`[cite: 334].
3.  [cite_start]Pipe the output to `grep` and search for lines that are preceded by several `=` characters[cite: 331, 334]. A pattern like `^=+` would match lines starting with one or more `=`.
    ```bash
    [cite_start]strings data.txt | grep "^=*" # The document uses this pattern, which matches lines starting with 0 or more '=' [cite: 334]
    # A more specific approach could be:
    # strings data.txt | grep "^=.*"
    # Or, if you know the password starts after a specific number of '=':
    # strings data.txt | grep "===="
    ```
    [cite_start]The password is provided as `FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey`[cite: 356].

[cite_start]**Password for Level 10:** `FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey` [cite: 356]

---

## Level 10 → Level 11

[cite_start]**Level Goal:** The password for the next level is stored in the file `data.txt`, which contains base64 encoded data[cite: 361].

**Commands Used:**
* [cite_start]`cat` [cite: 362]
* [cite_start]`base64` [cite: 362]

**Solution:**
1.  Log into `bandit9` using the previous password.
2.  [cite_start]Use `cat data.txt` [cite: 367] [cite_start]to view the base64 encoded string[cite: 368].
3.  [cite_start]Use the `base64 -d` command to decode the content[cite: 376].
    ```bash
    [cite_start]cat data.txt | base64 -d [cite: 376]
    ```
    The `base64 -d` command decodes base64-encoded data.

[cite_start]**Password for Level 11:** `dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr` [cite: 377]

---

## Level 11 → Level 12

[cite_start]**Level Goal:** The password for the next level is stored in the file `data.txt`, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions[cite: 380].

**Commands Used:**
* [cite_start]`cat` [cite: 381]
* [cite_start]`tr` [cite: 381]

**Solution:**
1.  Log into `bandit10` using the previous password.
2.  [cite_start]Use `cat data.txt` [cite: 389] [cite_start]to see the ROT13 encoded text[cite: 390].
3.  Use the `tr` (translate) command to decode the ROT13. ROT13 is symmetric, meaning applying it twice decodes the text.
    ```bash
    cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
    ```
    [cite_start]The password derived from the document is `7x16WNeHli5YklhWsfFlqoognUTyj9Q4`[cite: 698].

[cite_start]**Password for Level 12:** `7x16WNeHli5YklhWsfFlqoognUTyj9Q4` [cite: 698]

---

## Level 12 → Level 13

[cite_start]**Level Goal:** The password for the next level is stored in the file `data.txt`, which is a hexdump of a file that has been repeatedly compressed[cite: 403]. [cite_start]For this level, it may be useful to create a directory under `/tmp` in which you can work[cite: 404].

**Commands Used:**
* [cite_start]`xxd` [cite: 408]
* [cite_start]`file` [cite: 408]
* [cite_start]`mkdir` [cite: 408]
* [cite_start]`cp` [cite: 408]
* [cite_start]`mv` [cite: 408]
* [cite_start]`tar`, `gzip`, `bzip2` (for decompression) [cite: 408]

**Solution:**
1.  Log into `bandit11` using the previous password.
2.  Create a temporary working directory and navigate into it:
    ```bash
    [cite_start]mkdir /tmp/alexis [cite: 416] # or use `mktemp -d` for a unique name
    [cite_start]cd /tmp/alexis [cite: 418]
    ```
3.  Copy `data.txt` to your temporary directory:
    ```bash
    [cite_start]cp ~/data.txt . [cite: 417]
    ```
4.  The `data.txt` is a hexdump. Convert it back to binary. *(The `xxd -r` command is used for this, though not explicitly shown in the document's solution steps, it's implied by subsequent file operations).*
    ```bash
    xxd -r data.txt > data.bin
    ```
5.  Repeatedly use `file` to identify the compression type and then decompress it, renaming the file at each step for clarity.
    * [cite_start]`file data.bin` (assuming `data.bin` is the first unpacked file) [cite: 420]
    * [cite_start]**Step 1:** `data5.bin: POSIX tar archive (GNU)` [cite: 421]
        * [cite_start]`mv data5.bin data.tar` [cite: 422]
        * [cite_start]`tar xf data.tar` [cite: 423] [cite_start](extracts `data6.bin` [cite: 425, 427])
    * [cite_start]**Step 2:** `file data6.bin` -> `bzip2 compressed data` [cite: 431, 432]
        * [cite_start]`mv data6.bin data.bz2` [cite: 433]
        * [cite_start]`bzip2 -d data.bz2` [cite: 434] [cite_start](extracts `data` [cite: 436, 438])
    * [cite_start]**Step 3:** `file data` -> `POSIX tar archive (GNU)` [cite: 439, 440]
        * [cite_start]`mv data data.tar` [cite: 441]
        * [cite_start]`tar xf data.tar` [cite: 444] [cite_start](extracts `data8.bin` [cite: 445])
    * [cite_start]**Step 4:** `file data8.bin` -> `gzip compressed data` [cite: 446, 447]
        * [cite_start]`mv data8.bin data.gz` [cite: 448]
        * [cite_start]`gzip -d data.gz` [cite: 449] [cite_start](extracts `data` [cite: 451])
    * [cite_start]**Step 5:** `file data` -> `ASCII text` [cite: 452, 453]
6.  Finally, `cat` the resulting ASCII text file to get the password:
    ```bash
    [cite_start]cat data [cite: 454]
    ```

[cite_start]**Password for Level 13:** `F05dwFsccbaIiH0h8J2eUks2vdTDwAn` [cite: 454]

---

## Level 13 → Level 14

[cite_start]**Level Goal:** The password for the next level is stored in `/etc/bandit_pass/bandit14` and can only be read by user `bandit14`[cite: 457]. [cite_start]For this level, you don't get the next password directly, but you get a private SSH key that can be used to log into the next level[cite: 458].

**Commands Used:**
* [cite_start]`ssh` [cite: 460]
* [cite_start]`ls` [cite: 460]
* [cite_start]`cat` [cite: 460]
* `chmod` (to set key permissions)

**Solution:**
1.  Log into `bandit12` using the previous password.
2.  [cite_start]List files in the current directory: `ls`[cite: 464]. [cite_start]You'll find `sshkey.private`[cite: 465].
3.  Change the permissions of the private key to be readable only by you, as required for SSH keys:
    ```bash
    [cite_start]chmod 600 sshkey.private [cite: 558]
    ```
4.  [cite_start]Use the SSH key to log into `bandit14` on `localhost` (the same machine) on port `2220`[cite: 459, 466].
    ```bash
    [cite_start]ssh -i sshkey.private -p 2220 bandit14@localhost [cite: 466]
    ```
    [cite_start]You might be asked to confirm the authenticity of the host; type `yes`[cite: 469]. [cite_start]You may also see a "Permission denied" error for `.ssh` directory if it's the first time[cite: 469, 470].
5.  Once logged in as `bandit14`, read the password file:
    ```bash
    [cite_start]cat /etc/bandit_pass/bandit14 [cite: 473]
    ```

[cite_start]**Password for Level 14:** `MU4VWeTyJk8R0of1qqmcBPaLh7LDCPvS` [cite: 474]

---

## Level 14 → Level 15

[cite_start]**Level Goal:** The password for the next level can be retrieved by submitting the password of the current level to port `30000` on `localhost`[cite: 478].

**Commands Used:**
* [cite_start]`nc` (netcat) [cite: 480]
* `cat`

**Solution:**
1.  Log into `bandit13` using the previous SSH key.
2.  [cite_start]Get the current password: `cat /etc/bandit_pass/bandit14` (which is `MU4VWeTyJk8R0of1qqmcBPaLh7LDCPvS` [cite: 474]).
3.  [cite_start]Use `nc` to connect to `localhost` on port `30000`[cite: 489].
    ```bash
    [cite_start]nc localhost 30000 [cite: 489]
    ```
4.  [cite_start]Once connected, paste or type the password (`MU4VWeTyJk8R0of1qqmcBPaLh7lDCPvS` [cite: 490]) and press Enter. [cite_start]The server will respond with `Correct!` and the next password[cite: 490, 491].

[cite_start]**Password for Level 15:** `8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo` [cite: 491]

---

## Level 15 → Level 16

[cite_start]**Level Goal:** The password for the next level can be retrieved by submitting the password of the current level to port `30001` on `localhost` using SSL/TLS encryption[cite: 494].

**Commands Used:**
* [cite_start]`ncat` [cite: 497] [cite_start](or `openssl s_client` [cite: 497])
* `cat`

**Solution:**
1.  Log into `bandit14` using the previous password.
2.  [cite_start]Get the current password: `cat /etc/bandit_pass/bandit15` (which is `8xCjnmgoKbGLhHFAZLGE5Tmu4M2tKJQo` [cite: 501]).
3.  [cite_start]Use `ncat` with the `-ssl` flag to establish an SSL/TLS encrypted connection to `localhost` on port `30001`[cite: 502].
    ```bash
    [cite_start]ncat -ssl localhost 30001 [cite: 502]
    ```
4.  [cite_start]Once connected, paste or type the password (`8xCjnmgoKbGLhHFAZLGE5Tmu4M2tKJQo` [cite: 503]) and press Enter. [cite_start]The server will respond with `Correct!` and the next password[cite: 503, 504].

[cite_start]**Password for Level 16:** `kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx` [cite: 504]

---

## Level 16 → Level 17

[cite_start]**Level Goal:** The credentials for the next level can be retrieved by submitting the password of the current level to a port on `localhost` in the range `31000` to `32000`[cite: 507]. [cite_start]First, find out which of these ports have a server listening on them[cite: 507]. [cite_start]Then find out which of those speak SSL/TLS and which don't[cite: 508]. [cite_start]There is only 1 server that will give the next credentials[cite: 509].

**Commands Used:**
* [cite_start]`nmap` [cite: 512]
* [cite_start]`ncat` (with and without `-ssl`) [cite: 512]
* `cat`

**Solution:**
1.  Log into `bandit15` using the previous password.
2.  [cite_start]Get the current password: `cat /etc/bandit_pass/bandit16` (which is `kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx` [cite: 531]).
3.  [cite_start]Use `nmap` to scan the specified port range (`31000-32000`) on `localhost` to find open ports[cite: 515].
    ```bash
    [cite_start]nmap localhost -p 31000-32000 [cite: 515]
    ```
4.  [cite_start]Nmap will list several open ports, such as `31046`, `31518`, `31691`, `31790`, and `31960` [cite: 522-529].
5.  For each open port, try connecting with `ncat` without SSL and with SSL (`ncat -ssl`) to identify which one responds correctly. [cite_start]The document shows `ncat -ssl localhost 31790` was the successful command[cite: 532].
    ```bash
    [cite_start]ncat -ssl localhost 31790 [cite: 532]
    ```
6.  [cite_start]Paste or type the password (`kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx` [cite: 532]) and press Enter. [cite_start]The server will respond with `Correct!` and the next credentials, which is an RSA private key [cite: 532, 533-540].

[cite_start]**Password for Level 17:** This level provides an RSA private key which is the credential for the next level [cite: 533-540].

---

## Level 17 → Level 18

**Level Goal:** There are 2 files in the home directory: `passwords.old` and `passwords.new`. [cite_start]The password for the next level is in `passwords.new` and is the only line that has been changed between `passwords.old` and `passwords.new`[cite: 563, 564].

**Commands Used:**
* [cite_start]`diff` [cite: 568]

**Solution:**
1.  Log into `bandit17` using the provided SSH private key. First, save the private key obtained from Level 16 into a file (e.g., `key`) and set its permissions:
    ```bash
    [cite_start]vim key # paste the RSA private key here, then save and exit (:wq) [cite: 541, 542, 547]
    [cite_start]chmod 600 key [cite: 558]
    [cite_start]ssh -i key bandit17@bandit.labs.overthewire.org -p 2220 [cite: 560]
    ```
2.  [cite_start]Once logged in, use the `diff` command to find the differences between the two files[cite: 569, 571].
    ```bash
    [cite_start]diff passwords.old passwords.new [cite: 571]
    ```
3.  The output will show lines that are different. [cite_start]The line starting with `>` is the new line in `passwords.new`, which contains the password[cite: 573, 574].

[cite_start]**Password for Level 18:** `x2gLTTjFwMOhQ8oWNbMN362QKxfRqG10` [cite: 573]

---

## Level 18 → Level 19

[cite_start]**Level Goal:** The password for the next level is stored in a file `readme` in the home directory[cite: 577]. [cite_start]Unfortunately, someone has modified `.bashrc` to log you out when you log in with SSH[cite: 578].

**Commands Used:**
* [cite_start]`ssh` [cite: 579]
* [cite_start]`ls` [cite: 579]
* [cite_start]`cat` [cite: 579]

**Solution:**
1.  [cite_start]When you try to log into `bandit18` normally, you are immediately logged out due to the `.bashrc` modification[cite: 578].
2.  To bypass `.bashrc` and get a shell, you can specify a command to execute directly with SSH. [cite_start]The `/bin/sh` shell can be used with the `-t` option to force pseudo-terminal allocation[cite: 582].
    ```bash
    [cite_start]ssh -t bandit18@bandit.labs.overthewire.org -p 2220 /bin/sh [cite: 582]
    ```
3.  [cite_start]Once the shell is active, list the files (`ls`) [cite: 587] [cite_start]to confirm `readme` is present[cite: 588].
4.  [cite_start]Then `cat readme` [cite: 589] [cite_start]to retrieve the password[cite: 590].

[cite_start]**Password for Level 19:** `CGWpMaKXVWDUNgPAVJbWYuGHVn9zl3j8` [cite: 590]

---

## Level 19 → Level 20

[cite_start]**Level Goal:** To gain access to the next level, you should use the `setuid` binary in the home directory[cite: 593]. [cite_start]Execute it without arguments to find out how to use it[cite: 594]. [cite_start]The password for this level can be found in the usual place (`/etc/bandit_pass`), after you have used the `setuid` binary[cite: 595].

**Commands Used:**
* [cite_start]`ls` [cite: 598]
* [cite_start]`./bandit20-do` (execution of a binary) [cite: 600]
* [cite_start]`cat` [cite: 606]

**Solution:**
1.  Log into `bandit19` using the previous password.
2.  [cite_start]List files (`ls`)[cite: 598]. [cite_start]You'll see an executable named `bandit20-do`[cite: 599].
3.  Run the executable without arguments to understand its usage:
    ```bash
    [cite_start]./bandit20-do [cite: 600]
    ```
    It will output: `Run a command as another user. [cite_start]Example: ./bandit20-do id`[cite: 601, 602].
4.  The goal states the password is in `/etc/bandit_pass/bandit20` but readable by `bandit20`. [cite_start]Since `bandit20-do` runs commands as `bandit20` (confirmed by `euid=11020(bandit20)` in `id` command output [cite: 604]), use it to `cat` the password file:
    ```bash
    [cite_start]./bandit20-do cat /etc/bandit_pass/bandit20 [cite: 606]
    ```

[cite_start]**Password for Level 20:** `0qXahG8ZjOVMN9Ghs7i0WsCfZyX0UbYO` [cite: 607]

---

## Level 20 → Level 21

[cite_start]**Level Goal:** There is a `setuid` binary in the home directory that makes a connection to `localhost` on a specified port[cite: 611]. [cite_start]It reads a line of text from the connection and compares it to the password in the previous level (`bandit20`)[cite: 612]. [cite_start]If the password is correct, it will transmit the password for the next level (`bandit21`)[cite: 613].

**Commands Used:**
* [cite_start]`ls` [cite: 615]
* [cite_start]`./suconnect` (execution of a binary) [cite: 619]
* [cite_start]`cat` [cite: 615]
* [cite_start]`nc` (netcat for listening) [cite: 615]

**Solution:**
1.  Log into `bandit20` using the previous password.
2.  [cite_start]List files (`ls`)[cite: 617]. [cite_start]You'll find `suconnect`[cite: 618].
3.  [cite_start]Run `suconnect` without arguments to see its usage: `./suconnect <portnumber>`[cite: 619, 620].
4.  The program expects a port number. To receive the password, you need to set up a listener on a port on `localhost` that `suconnect` will connect to.
5.  [cite_start]Get the password for `bandit20`: `cat /etc/bandit_pass/bandit20` (which is `0qXahG8ZjOVMN9Ghs7i0WsCfZyX0UbYO` [cite: 623, 624]).
6.  Open a new terminal session or use job control (e.g., `Ctrl+Z`, `bg`) if your current terminal supports it for multitasking. Set up a netcat listener on an arbitrary unused port (e.g., `4444`) on your local machine:
    ```bash
    [cite_start]nc -lvp 4444 [cite: 638]
    ```
7.  Go back to your SSH session as `bandit20` and execute `suconnect`, pointing it to your listener port:
    ```bash
    [cite_start]./suconnect 4444 [cite: 646]
    ```
8.  [cite_start]Immediately after `suconnect` connects (you'll see `Connection received on localhost 37646` in your listener terminal [cite: 640][cite_start]), type the `bandit20` password (`0qXahG8ZjOVMN9Ghs7i0WsCfZyX0UbYO` [cite: 641]) into the listening `nc` session and press Enter. [cite_start]The `suconnect` program will verify it and then send the `bandit21` password back to your listener[cite: 646].

[cite_start]**Password for Level 21:** `EeoULMCra2q0dSkYj561DX7s1CpBu0Bt` [cite: 642]

---

## Level 21 → Level 22

[cite_start]**Level Goal:** A program is running automatically at regular intervals from `cron`, the time-based job scheduler[cite: 649]. [cite_start]Look in `/etc/cron.d/` for the configuration and see what command is being executed[cite: 650].

**Commands Used:**
* [cite_start]`ls` [cite: 651]
* [cite_start]`cat` [cite: 651]

**Solution:**
1.  Log into `bandit21` using the previous password.
2.  [cite_start]List the contents of the `/etc/cron.d/` directory to see the cron job configurations[cite: 656].
    ```bash
    [cite_start]ls /etc/cron.d/ [cite: 656]
    ```
3.  [cite_start]You'll see a file named `cronjob_bandit22`[cite: 657]. View its contents:
    ```bash
    [cite_start]cat /etc/cron.d/cronjob_bandit22 [cite: 660]
    ```
4.  [cite_start]The script indicates that `bandit22` runs `/usr/bin/cronjob_bandit22.sh`[cite: 663, 664].
5.  Examine the script:
    ```bash
    [cite_start]cat /usr/bin/cronjob_bandit22.sh [cite: 665]
    ```
    [cite_start]The script shows that it changes permissions of a temporary file and then `cat`s the `bandit22` password into that file[cite: 667, 668]:
    ```bash
    chmod 644 /tmp/t706lds9S0RqQh9aMcz6ShpAoZKF7fgv
    cat /etc/bandit_pass/bandit22 > /tmp/t706lds9S0RqQh9aMcz6ShpAoZKF7fgv
    ```
6.  The password will be in the specified temporary file. Read it:
    ```bash
    [cite_start]cat /tmp/t706lds9S0RqQh9aMcz6ShpAoZKF7fgv [cite: 668]
    ```

[cite_start]**Password for Level 22:** `tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q` [cite: 668]

---

## Level 22 → Level 23

[cite_start]**Level Goal:** A program is running automatically at regular intervals from `cron`, the time-based job scheduler[cite: 672]. [cite_start]Look in `/etc/cron.d/` for the configuration and see what command is being executed[cite: 673]. [cite_start]This script is intentionally made easy to read[cite: 675].

**Commands Used:**
* [cite_start]`cat` [cite: 677]
* [cite_start]`whoami` [cite: 682]
* [cite_start]`md5sum` [cite: 683]
* [cite_start]`cut` [cite: 683]

**Solution:**
1.  Log into `bandit21` using the previous password.
2.  Examine the cron job for `bandit23`:
    ```bash
    [cite_start]cat /etc/cron.d/cronjob_bandit23 [cite: 679]
    ```
    [cite_start]It shows `bandit23` running `/usr/bin/cronjob_bandit23.sh`[cite: 680].
3.  View the script's content:
    ```bash
    [cite_start]cat /usr/bin/cronjob_bandit23.sh [cite: 681]
    ```
    The script contains:
    ```bash
    #!/bin/bash
    myname=$(whoami)
    mytarget=$(echo I am user $myname | md5sum  cut -d-f 1)
    echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"
    cat /etc/bandit_pass/$myname > /tmp/$mytarget
    ```
4.  [cite_start]The script copies the password for `bandit23` to a file in `/tmp/` whose name is generated by an MD5 hash of "I am user bandit23"[cite: 683, 684, 685].
5.  To find the `mytarget` filename, simulate the script's logic:
    * [cite_start]`whoami` as `bandit22` [cite: 686, 687] (but the script runs as `bandit23`)
    * Therefore, `myname` will be `bandit23`.
    * Calculate the MD5 hash:
    ```bash
    [cite_start]echo I am user bandit23 | md5sum | cut -d-f 1 [cite: 693]
    ```
    [cite_start]This will output the hash, which is `8ca319486bfbbc3663ea0fbe81326349`[cite: 693].
6.  Now, `cat` the content of the file in `/tmp/` with this hash:
    ```bash
    [cite_start]cat /tmp/8ca319486bfbbc3663ea0fbe81326349 [cite: 694]
    ```

[cite_start]**Password for Level 23:** `0Zf11ioIjMVN551jX3CmStKLYqjk54Ga` [cite: 695]

---

## All Passwords Logged So Far:

* [cite_start]**level-0:** `bandit0` [cite: 697]
* [cite_start]**level 0-1:** `ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5lf` [cite: 698]
* [cite_start]**level 1 - 2:** `263JGJPfgU6LtdEvgfWU1XP5yac29mFx` [cite: 698]
* [cite_start]**level 2 - 3:** `MNk8KNH3Usiio41PRUEoDFPqfxLPISmx` [cite: 698]
* [cite_start]**level 3 - 4:** `2WmrDFRmJlq3lPxneAaMGhap0pFhF3NJ` [cite: 698]
* [cite_start]**level 4-5:** `40QYVPkxZOOEOO5pTW81FB8j8lxXGUQw` [cite: 698]
* [cite_start]**level 5-6:** `HWasnPhtq9AVKe0dmk45nxy20cvUa6EG` [cite: 698]
* [cite_start]**level 6-7:** `morbNTDkSW6jllUc0ymOdMaLnOIFVAaj` [cite: 698]
* [cite_start]**level 7 - 8:** `dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc` [cite: 698]
* [cite_start]**level 8-9:** `4CKMh1JI91bUIZZPXDqGanal4xvAg0JM` [cite: 698]
* [cite_start]**level 9-10:** `FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey` [cite: 698]
* [cite_start]**level10-11:** `dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr` [cite: 698]
* [cite_start]**level11-12:** `7x16WNeHli5YklhWsfFlqoognUTyj9Q4` [cite: 698]
* [cite_start]**level12-13:** `F05dwFsc0cbaliH0h8J2eUks2vdTDwAn` [cite: 698]
* [cite_start]**level13-14:** `MU4VWeTyJk8ROof1qqmcBPaLh7IDCPvS` [cite: 698]
* [cite_start]**level14-15:** `8xCjnmgoKbGLhHFAZIGE5Tmu4M2tKJQo` [cite: 698]
* [cite_start]**level15-16:** `kSkvUpMQ7IBYyCM4GBPvCvT1BfWRy0Dx` [cite: 699]
* [cite_start]**level16-17:** (RSA Private Key - save this in a file and use `chmod 600` for SSH) [cite: 700-711]
    ```
    -----BEGIN RSA PRIVATE KEY-----
    MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
    imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMIOJf7+BrJObArnxd9Y7YT2bRPQ
    Ja6Lzb558YW3FZI87ORIO+rW4LCDCNd2IUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
    DSt2mcNn4rhAL+JFr5604T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
    JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
    x0YVztz/zblkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
    KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RILwD1NhPx3iBl
    J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
    d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
    YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
    vLY9r60wYSvmZhNqBUrj7lyCtXMlu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
    +TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dElkza8ky5molwUqYdsx0NxHgRRhORT
    8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
    SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
    HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
    SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enClvGCSx+X315SiWg0A
    R57hJglezliVjv3aGwHwvlZvtszK6zV60XFAu0ECgYAbjo46T4hyP5tJi93V5HDi
    Ttiek7xRVxUI+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
    R8VdwSk8r9FGLS+9aKcV5PI/WEKIwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
    L8ktHMPvodBwNsSBULpG0QKBgBApITfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
    blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
    YOdjHdSOoKvDQNWu6ucyLRAWFulSeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
    77pBAoGAMmjmlJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
    dxviW8+TFVEBI1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
    vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6lgeuZ/ujbjY=
    -----END RSA PRIVATE KEY-----
    ```
* [cite_start]**level17-18:** `x2gLTTjFwMOhQ80WNbMN362QKxfRqGIO` [cite: 712]
* [cite_start]**level18-19:** `cGWpMaKXVwDUNGPAVJbWYuGHVn9zl3j8` [cite: 712]
* [cite_start]**level19-20:** `0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO` [cite: 712]
* [cite_start]**level20-21:** `EeoULMCra2q0dSkYj561DX7s1CpBuOBt` [cite: 712]
* [cite_start]**level21 - 22:** `tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q` [cite: 712]
* [cite_start]**level22 - 23:** `0Zf11ioIjMVN551JX3CmStKLYqjk54Ga` [cite: 712]

---

[cite_start]I will update this post as I continue my journey through the Bandit Wargame! [cite: 713]
