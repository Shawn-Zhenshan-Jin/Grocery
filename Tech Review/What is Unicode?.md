## 1. What is Unicode:  
Unicode: `Universal Coded Character Set`, represented as `code point`;  
Fact: unitl 2012, there 1.1 millioin characters exist in the word and 10% of them have been assigned in Unicode  

## 2. what is Bytes:
The format that Unicode is stored inside computer; 

## 3. what is `ASCII`, `UTF-8`, `UTF-16`:  
Transformation format that computer used to encoding/decoding Unicode into Bytes
Fact: UFT-8 have the capacity to represent all the existing characters(4 bytes is enough: 256 ^ 4 > 1.1 M) and compatible with 
ASCII, but not UTF-16

## 4. What is the matter concerning Python?  
### 4.1 Python2  
**`str`**:  
Representation: `Bytes`  
Fact: 1. len(my_string) return bytes number; 2. require encoding/decoding  
  
**`u"my_characters"`**:  
Representation: `Unicode`  
Fact: len(u"my_characters") return code point number

**`Feature`**:  
implicit convert `str` into unicode through default encoding/decoding method, usually `ASCII`(sys.getdefaultencoding())

**`Pain`**:  
Won't work if the requirement for en/decoding method require more than default method.

### 4.2 Python3
**`str`**:  
Represnetation: `Unicode`  
  
**`b"my_chracters"`**:  
Representation: `Bytes`  

**`Feature`**:  
1. no implicit conversion, have to make it consistent by programmer  
2. read & write:  
`open(file = "my_text.txt", mode = "r", encoding = default_encoding)`  
Explain:  
`mode`: mode to read the file, `"rb"` to read the file directly as `Bytes`  
`encoding`: method to use when encoding and decoding the file. `default encoding` depend on platform, for Ubuntu 16.04 is `UTF-8`(locale.getpreferredencoding())  

## 5. How to go away from the pains?  
1. all the documents are stored in `Bytes`, make sure: Bytes(documents) -->(input) Unicode(python processing) -->(output) Bytes(documents)  
2. know what is the type of data I have: `Unicode` or `Bytes`, if Bytes, what is the encoding/decoding method

## 6. Relationship with other text representation language:  
`XML`: way to store & transpose Unicode   
`HTML`: way to represent Unicode   

## 7. Conclusion:  
For importing PDF text into Python, need to know how the PDF is encoded and then to make it consistent during the processing procudure

## 8. Resources:  
Great video from `Ned Batchelder`: [Pragmatic Unicode, or, How do I stop the pain?](https://www.youtube.com/watch?v=sgHbC6udIqc&t=1515s)  
What is `encoding` inside python `open`: [python 3.0 open() default encoding](https://stackoverflow.com/questions/36303919/python-3-0-open-default-encoding)
