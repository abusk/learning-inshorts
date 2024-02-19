# Encoding/Decoding

Encoding and decoding are fundamental processes in computer science and information technology that involve the transformation of data from one representation to another. These processes are essential for various purposes, including data compression, data transmission, and ensuring compatibility between different systems.

## Encoding

**Encoding** refers to the process of converting data from one format to another, often with the goal of representing the data in a more suitable form for a particular application or system. Encoding can involve converting data from a human-readable format to a machine-readable format or vice versa. 

### Common Types of Encoding:

1. **ASCII Encoding**: ASCII (American Standard Code for Information Interchange) is a character encoding standard that represents text in computers. It uses seven bits to represent each character, allowing for a total of 128 different characters.

```text
Here are the ASCII values for the characters 'a', 'b', and 'c':
'a': 97 (decimal), 01100001 (binary)
'b': 98 (decimal), 01100010 (binary)
'c': 99 (decimal), 01100011 (binary)
```
```python
# ASCII encoding/decoding example
ascii_text = "Hello, ASCII!"
encoded_ascii_text = ascii_text.encode('ascii')  # Encode ASCII text to ASCII byte string
print("Encoded ASCII Text:", encoded_ascii_text)

decoded_ascii_text = encoded_ascii_text.decode('ascii')  # Decode ASCII byte string to ASCII text
print("Decoded ASCII Text:", decoded_ascii_text) # Output: Hello World!
```
2. **Unicode Encoding**: Unicode is a character encoding standard that aims to represent every character from every language in the world. It supports a much larger range of characters compared to ASCII and is commonly used for internationalization and multilingual applications.
```text
'a': U+0061 (hexa), 01100001 (binary)
'b': U+0061 (hexa), 01100010 (binary)
'c': U+0061 (hexa), 01100011 (binary)
```
```python
# Unicode encoding/decoding example
unicode_text = "Hello, नमस्ते"
encoded_unicode_text = unicode_text.encode('utf-8')  # Encode Unicode text to UTF-8 byte string
print("Encoded Unicode Text:", encoded_unicode_text)

decoded_unicode_text = encoded_unicode_text.decode('utf-8')  # Decode UTF-8 byte string to Unicode text
print("Decoded Unicode Text:", decoded_unicode_text)
```
3. **Base64 Encoding**: Base64 encoding is a method of encoding **binary data** into ASCII characters. It is commonly used for encoding binary data in text-based formats, such as email attachments or data transmitted over HTTP.
```html
Base64 encoding of "Hello"  is "SGVsbG8="
How: 
Binary representation of Hello: 01001000 01100101 01101100 01101100 01101111
Base64 group the binary string using 6 bits (2^6 == 64): 010010 000110 010101 101100 011011 000110 1111 
The last group needs two more bits as padding. Base64 encoding uses '=' at the end to identify if it needs padding. Each '=' adds 2 padding bits.
After added padding: 010010 000110 010101 101100 011011 000110 111100

The Base64 character are 
0- 51 -> A-z
52-61 -> 0-9
62-63 -> + /
And Padding is '='
Based on the character list : 
010010 -> S
000110 -> G
010101 -> V
101100 -> s
011011 -> b
000110 -> G
111100 -> 8
and for two bits padding added '='
```
```python
import base64

binary_data = b'Hello'
encoded_data = base64.b64encode(binary_data)
print(encoded_data.decode('utf-8'))  # Output: SGVsbG8="

decoded_data = base64.b64decode(encoded_data)
print(decoded_data.decode('utf-8'))  # Output: Hello
```
4. **URL Encoding**: URL encoding is a method used to encode special characters in URLs (Uniform Resource Locators) into a format that can be transmitted over the internet. It replaces non-alphanumeric characters with a '%' followed by two hexadecimal digits representing the character's ASCII value.

```html
1. Identify Special Characters: URLs may contain special characters such as spaces, punctuation marks, and non-alphanumeric characters like &, =, ?, #, etc.

2. Convert to ASCII: Each character in the URL is converted to its corresponding ASCII value.

3. Encode Special Characters: For each special character, the ASCII value is represented in hexadecimal format and prefixed with a percent sign %. For example:

    Space (ASCII value 32) becomes %20.
    Colon (ASCII value 58) becomes %3A.
    Ampersand (ASCII value 38) becomes %26.
    Equals sign (ASCII value 61) becomes %3D.
    Question mark (ASCII value 63) becomes %3F.
    Hash sign (ASCII value 35) becomes %23, and so on.
Replace Characters: The special characters in the URL are replaced with their percent-encoded representations.

Valid URL Construction: The encoded URL can now be safely transmitted over the internet without being misinterpreted. When a web server receives the URL, it automatically decodes the percent-encoded characters to reconstruct the original URL.
```
```python
import urllib.parse

# URL to encode
url = "https://www.example.com/page with spaces?q=hello world&lang=en"

# Encode the URL
encoded_url = urllib.parse.quote(url)
print("Encoded URL:", encoded_url) # Encoded URL: https%3A%2F%2Fwww.example.com%2Fpage%20with%20spaces%3Fq%3Dhello%20world%26lang%3Den

# Decode the URL
decoded_url = urllib.parse.unquote(encoded_url)
print("Decoded URL:", decoded_url) # Decoded URL: https://www.example.com/page with spaces?q=hello world&lang=en
```
