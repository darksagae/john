# john
**John the Ripper (John)** is a popular password cracking tool used for performing dictionary attacks, brute-force attacks, and more. It is often utilized in penetration testing and security assessments to test the strength of passwords.

### Installation

If you're using Kali Linux, John is typically installed by default. You can check if it's installed by running:

```bash
john --version
```

### Basic Usage

#### 1. Cracking Password Hashes

**Step 1: Prepare the Hashes**

Create a file named `hashes.txt` containing the password hashes you want to crack. For example, using MD5 hashes:

```
$1$abcdefgh$1234567890abcdefg
$1$ijklmnop$fedcba0987654321
```

**Step 2: Run John the Ripper**

To crack the hashes, use the following command:

```bash
john hashes.txt
```

**Output Example:**

After running, John will display the cracked passwords:

```
$1$abcdefgh$1234567890abcdefg:password1
$1$ijklmnop$fedcba0987654321:password2
```

#### 2. Using a Wordlist

You can also crack passwords using a wordlist. Let's say you have a wordlist file named `wordlist.txt`.

**Step 1: Run John with a Wordlist**

```bash
john --wordlist=wordlist.txt hashes.txt
```

**Output Example:**

If successful, John will display:

```
$1$abcdefgh$1234567890abcdefg:examplepassword
```

#### 3. Cracking Different Hash Types

John supports various hash types. You can specify the hash type using the `--format` option. For example, to crack SHA-256 hashes:

```bash
john --format=raw-sha256 hashes.txt
```

### Additional Options

- **Show Cracked Passwords:**

  To display the cracked passwords from the session, use:

  ```bash
  john --show hashes.txt
  ```

- **Resume Cracking:**

  If you need to stop and resume cracking later, John saves its progress. To resume, simply run:

  ```bash
  john --restore
  ```

### Conclusion

John the Ripper is a powerful tool for password recovery and testing. Always ensure you have permission to test any passwords or systems. Use it responsibly within legal boundaries.




                               ALTERNATIVE
John the Ripper (often referred to as "John") is a popular password cracking tool available on Kali Linux. It is used to identify weak passwords by performing various types of attacks on password hashes.

### Installation
If John is not already installed on your Kali system, you can install it using:

```bash
sudo apt install john
```

### Basic Usage

1. **Prepare a Password Hash File**
   You need a file that contains password hashes. For example, you can create a file named `passwords.txt` with the following content:

   ```
   user1:$6$saltsalt$hashhashhash...
   user2:$6$saltsalt$hashhashhash...
   ```

2. **Run John**
   To crack the hashes in your file, use:

   ```bash
   john passwords.txt
   ```

3. **View Cracked Passwords**
   After running John, you can view the cracked passwords with:

   ```bash
   john --show passwords.txt
   ```

### Example Commands

- **Using a Wordlist**
  If you want to use a wordlist for cracking, you can specify it:

  ```bash
  john --wordlist=/path/to/wordlist.txt passwords.txt
  ```

- **Using Rules**
  You can enhance your attacks by using rules:

  ```bash
  john --wordlist=/path/to/wordlist.txt --rules passwords.txt
  ```

- **Incremental Mode**
  For a brute-force attack, you can use incremental mode:

  ```bash
  john --incremental passwords.txt
  ```

### Output Example

After running John, you might see output similar to this:

```
user1: password123
user2: letmein
```

### Summary of Options

- `--show`: Displays cracked passwords.
- `--wordlist`: Uses a custom wordlist.
- `--rules`: Applies rules to modify words in the wordlist.
- `--incremental`: Attempts all combinations of characters.

### Important Note
Always ensure you have permission to test the security of any system, and only use John the Ripper in ethical and legal contexts.



                             ALTERNATIVE
John the Ripper!

John the Ripper is a popular password cracking tool available on Kali Linux. It's a powerful utility that can be used to crack passwords using various methods, including dictionary attacks, brute-force attacks, and rainbow table attacks.

Here's a brief overview of how to use John the Ripper and some examples:

**Basic Syntax:**
```
john [options] <password_file>
```
**Options:**

* `-form`: specifies the format of the password hash (e.g., MD5, SHA-1, etc.)
* `-wordlist`: specifies the wordlist file to use for dictionary attacks
* `-incremental`: enables incremental mode, which tries all possible combinations of characters
* `-rules`: enables rule-based cracking, which applies transformations to words in the wordlist

**Examples:**

1. **Cracking a single password hash:**
```
john -form=md5 hash.txt
```
Assuming `hash.txt` contains a single MD5 password hash, John will try to crack it using its default settings.

Output:
```
Loaded 1 password hash (MD5 [128/128 SSE2 intrinsics 12x])
Press 'q' or Ctrl-C to abort, almost any other key for status
123456         (password)
```
In this example, John successfully cracks the password hash, revealing the original password as "123456".

2. **Cracking multiple password hashes:**
```
john -form=sha1 hashes.txt
```
Assuming `hashes.txt` contains multiple SHA-1 password hashes, one per line, John will try to crack each hash.

Output:
```
Loaded 5 password hashes (SHA1 [128/128 SSE2 intrinsics 12x])
Press 'q' or Ctrl-C to abort, almost any other key for status
user1:password1
user2:password2
user3:password3
...
```
In this example, John cracks multiple password hashes, revealing the original passwords for each user.

3. **Using a wordlist:**
```
john -wordlist=rockyou.txt -form=md5 hash.txt
```
Assuming `rockyou.txt` is a wordlist file and `hash.txt` contains a single MD5 password hash, John will try to crack the hash using the words in the wordlist.

Output:
```
Loaded 1 password hash (MD5 [128/128 SSE2 intrinsics 12x])
Press 'q' or Ctrl-C to abort, almost any other key for status
iloveyou         (password)
```
In this example, John uses the wordlist to crack the password hash, revealing the original password as "iloveyou".

4. **Using incremental mode:**
```
john -incremental -form=md5 hash.txt
```
Assuming `hash.txt` contains a single MD5 password hash, John will try to crack it using incremental mode, which tries all possible combinations of characters.

Output:
```
Loaded 1 password hash (MD5 [128/128 SSE2 intrinsics 12x])
Press 'q' or Ctrl-C to abort, almost any other key for status
a               (password)
```
In this example, John uses incremental mode to crack the password hash, revealing the original password as "a".

These are just a few examples of how to use John the Ripper. Remember to use this tool responsibly and only for authorized purposes.



                            ALTERNATIVE
John the Ripper is a popular open-source password cracking tool that is commonly used in Kali Linux. It is designed to detect weak passwords by testing various password guesses against a target account or system.

Here are some ways you can use John the Ripper on Kali Linux:

1. Password Cracking:
   - Syntax: `john [options] [password-file]`
   - Example: `john --wordlist=/usr/share/wordlists/rockyou.txt hashes.txt`
   - This will use the rockyou.txt wordlist to crack the passwords in the hashes.txt file.

2. Hash Identification:
   - Syntax: `john --list=formats`
   - This will display a list of supported hash types that John the Ripper can crack.

3. Password Guessing:
   - Syntax: `john --wordlist=[wordlist-file] [password-file]`
   - Example: `john --wordlist=/usr/share/wordlists/rockyou.txt --rules passwords.txt`
   - This will use the rockyou.txt wordlist and apply various rules to generate password guesses for the passwords.txt file.

4. Incremental Mode:
   - Syntax: `john --incremental[=mode] [password-file]`
   - Example: `john --incremental=alpha passwords.txt`
   - This will attempt to crack the passwords in the passwords.txt file using an incremental approach, starting with single-character passwords and gradually increasing the length and complexity.

5. Customizing Rules:
   - Syntax: `john --rules=[rule-file] [password-file]`
   - Example: `john --rules=/usr/share/john/john.conf --wordlist=/usr/share/wordlists/rockyou.txt hashes.txt`
   - This will use the custom rules defined in the john.conf file, along with the rockyou.txt wordlist, to crack the passwords in the hashes.txt file.

John the Ripper is a powerful tool, but it should be used ethically and only with permission on systems you own or have explicit authorization to test. Improper use of password cracking tools can be illegal and unethical.





                       ALTERNATIVE
John the Ripper is a password cracking tool available on Kali Linux. Here's how to use it, along with examples: 

 **1. What John the Ripper Does** 

 *   John the Ripper is an offline password cracking tool. 
 *   It supports a wide variety of password formats. 
 *   It's often pre-installed on penetration testing distributions like Kali Linux. 
 *   It can be used to identify weak passwords. 

 **2. Basic Usage** 

 *   To see the help options: `john -h` 
 *   The simplest way to use it is to provide a password file: `john mypasswd` 

 *   John will automatically try different cracking modes in this order: "single crack", then wordlist with rules, and finally "incremental" mode. 

 **3. Key Concepts & Modes** 

 *   **Wordlist Mode:** John uses a pre-made list of common passwords to try and crack the hashes. 
 *   **Incremental Mode:**  This mode systematically tries all possible combinations of characters. 
 *  **Single Crack Mode:** This mode is the simplest and fastest. It uses variations of login names found in the password file. 

 **4. Example Scenarios** 

 *   **Cracking Linux Passwords:** 

 1.  **Create a password file:** You may need to combine the `/etc/passwd` and `/etc/shadow` files.  Use the `unshadow` utility for this: 
 ```bash 
 unshadow /etc/passwd /etc/shadow > mypasswd 
 ``` 

 2.  **Run John the Ripper:** 
 ```bash 
 john mypasswd 
 ``` 

 *   You can specify the format: `john --format=crypt --wordlist=rockyou lin3.txt` 

 *   **Cracking SSH Keys:** 

 1.  **Extract the Hash:** Use `ssh2john` to export the hashed private key file: 
 ```bash 
 ssh2john /home/kali/.ssh/id_rsa > myHash.txt 
 ``` 

 2.  **Crack with John:** 
 ```bash 
 john --wordlist=rockyou myHash.txt 
 ``` 

 *   **Cracking ZIP Files:** 

 1.  **Extract the Hash:** Use `zip2john`: 
 ```bash 
 zip2john classified.zip > zip.hashes 
 ``` 

 2.  **Crack with John:** 
 ```bash 
 john zip.hashes 
 ``` 

 **5. Important Considerations** 

 *   **Password Files:** John needs the password data in a format it can understand.  For Linux systems, this often involves combining `/etc/passwd` and `/etc/shadow`. 
 *   **Wordlists:**  It's highly recommended to use a larger wordlist than John's default. You can find many wordlists online. 
 *   **john.pot:** Cracked passwords are saved in `$JOHN/john.pot`. This file is not meant to be human-readable. 

 **6. Cracking Windows Passwords** 

 *   You'll need to extract the password hashes from the Windows system first.  Tools like PwDump can help with this. 
 *   Then, you can use John the Ripper to crack the hashes. 

 **7. Ethical and Legal Considerations** 

 *   Always use John the Ripper ethically and legally. 
 *   Obtain proper authorization before attempting to crack passwords. 
 *   Respect privacy and confidentiality. 
 *   Follow all applicable laws and regulations.
