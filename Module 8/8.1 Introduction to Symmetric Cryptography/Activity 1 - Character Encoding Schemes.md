## Activity Objectives

By the end of this activity, students will be able to identify, understand, and apply common character encoding schemes such as Base64, UTF-8, ASCII, and Decimal to Hex. Through the completion of a quiz, students will demonstrate their ability to convert between these encoding formats, recognize their applications and limitations, and explain their significance in data representation and communication.

## Activity Instruction
Complete the knowledge check.

## Knowledge Check
1. What is the primary purpose of Base64 encoding?
   1. To compress data prior to being efficiently transmitted
   2. To encrypt data prior to being transmitted
   3. To represent binary data in ASCII text format
   4. To format data for web pages
<details closed>
<summary>Answer</summary>
The primary purpose of Base64 encoding is to represent binary data in an ASCII string format so it can be safely transmitted or stored in systems that only support text data.</details>

2. Given the string "hello" in ASCII, what is the Base64 encoded version?
   1. aGVsbG8=
   2. agVsbG8=
   3. aGVsbG8
   4. aGVsbG8g
<details closed>
<summary>Answer</summary>
aGVsbG8=</details>

3. Decode the following Base64 string: SGVsbG8gd29ybGQh
   1. Hello World!
   2. Hello world!
   3. Hello world
   4. Hello World
<details closed>
<summary>Answer</summary>
Hello World!</details>

4. What is the purpose of padding when encoding?
<details closed>
<summary>Answer</summary>
Padding ensures that the encoded output has the correct length and structure, especially when the input data doesn't divide evenly into the required block sizes.</details>

5. What is UTF-8 primarily used for?
   1. Compression of binary data into text day
   2. To represent text in a universal, efficient, and web-safe format 
   3. To represent binary data in ASCII text format
   4. Formatting text data prior to being sent over the internet
<details closed>
<summary>Answer</summary>
UTF-8 is primarily used to encode text in a universal, efficient, and web-safe format that supports all Unicode characters.</details>

6. Which of the following is/are a key feature of UTF-8 encoding? (Select all that Apply)
   1. Variable-Length Encoding
   2. Backward Compatible with ASCII
   3. Byte-Order Independence
   4. Self-Synchronizing & Error Handling
   5. Supports All Unicode Characters
<details closed>
<summary>Answer</summary>
UTF-8 is a variable-length encoding that uses 1 to 4 bytes per character, allowing it to efficiently represent both simple ASCII characters and complex Unicode symbols. It is byte-order independent, meaning it stores data in a consistent sequence of bytes without needing a Byte Order Mark (BOM). UTF-8 is also self-synchronizing, where the beginning of each character is clearly marked, making it easier to detect and recover from errors. This structure allows for reliable error handling, since a corrupted byte won't break the entire string—only the affected character is impacted.</details>

7. Which of the following is/are a key feature of base64 encoding? (Select all that Apply)
   1. Fixed Output Length
   2. Padding with "="
   3. Includes uppercase letters (A-Z), lowercase letters (a-z), digits (0-9), and the characters + and /
   4. Variations use different characters (e.g., URL-safe Base64 uses - and _ instead of + and /)
<details closed>
<summary>Answer</summary>
Base64 is an encoding scheme that produces a fixed output length, converting every 3 bytes of binary input into 4 ASCII characters, which ensures consistent and predictable encoded data size. When the input isn't a multiple of 3 bytes, Base64 uses padding with = to complete the final 4-character block and maintain proper alignment. The encoded output includes uppercase letters (A–Z), lowercase letters (a–z), digits (0–9), and the symbols + and /, making it safe for most text-based systems. There are also variations, such as URL-safe Base64, which replaces + and / with - and _ to avoid conflicts with URL or filename restrictions.</details>

8. What is the maximum number of bytes used to encode a single character in UTF-8?
   1. 1 byte
   2. 2 bytes
   3. 3 bytes
   4. 4 bytes
<details closed>
<summary>Answer</summary>
The maximum number of bytes used to encode a single character in UTF-8 is 4 bytes.</details>

9. Which of the following is true about UTF-8 encoding?
   1. It requires all characters to be encoded with exactly 4 bytes.
   2. It uses only 1 byte for characters outside the Basic Latin block.
   3. It can represent all possible characters in Unicode while minimizing space usage for common characters.
   4. It is only used for encoding English text.
<details closed>
<summary>Answer</summary>
UTF-8 is universal, supporting all Unicode characters. It also is efficient because it uses fewer bytes when encoding characters that appear more often.</details>

10. Which of the following is true about UTF-8 encoding? (Select all that Apply)
   1. To encode special characters in URLs to ensure that they are transmitted correctly over the internet
   2. Ensure URLs are valid and properly interpreted by the browser and web server
   3. To avoid conflicts with URL syntax.
   4. Converts binary data to ASCII
   5. To maintain the integrity of query strings and parameters
<details closed>
<summary>Answer</summary>
The purpose of a URL encoding scheme is to ensure that all characters within a URL are transmitted safely and interpreted correctly by web browsers and servers. URLs can only contain a limited set of ASCII characters, so characters that have special meanings (like spaces, &, ?, #) or are not allowed (such as non-English letters or symbols) must be encoded using a percent (%) followed by two hexadecimal digits—for example, a space becomes %20. This prevents confusion between data and URL structure, especially in query strings and form submissions. URL encoding also ensures that the integrity of parameters is preserved and that no illegal or unsafe characters cause errors during transmission. It is important to note that URL encoding is not a form of encryption; it is simply a way to safely represent text in URLs.</details>

11. Decode the following: Security%20through%20obscurity%2C%20is%20not%20security%3B%20so%20remember%20to%20check%20your%20code%21%20-%20Myles%5FJWW
<details closed>
<summary>Answer</summary>
Security through obscurity, is not security; so remember to check your code! - Myles_JWW

The original string uses URL encoding, where certain characters are replaced with % followed by two hexadecimal digits to make them safe for URLs.</details>
