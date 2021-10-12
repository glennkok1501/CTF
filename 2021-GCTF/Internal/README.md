# Internal
___Category:___ Web Exploit
## Challenge Details
The aliens have abducted the cow... can you help us find him?
http://c1.2021.gryphonctf.com:9003/
## Hint
🛸 🐄

## Write Up
![Website](images/website.png)
Upon inspecting the website, nothing seems to be of suspicion. However, after downloading the image ```/images/cow.jpg```, it appears that there is an encoded message in the meta data.

![Meta Data](images/exiftool.png)
```Comment : dmVyeXNlY3VyZXBhc3NwaHJhc2U=```

Looking at the comment, it is obvious that the message is encoded in Base64.
Decoded message: ```verysecurepassphrase```

Using the text phrase retrieved earlier as the password, ```secret.txt``` was extracted from ```cow.jpg``` using [Steghide](steghide.sourceforge.net)
![Steghide](images/steghide.png)

secret.txt:
>Meridius:HKw@8j$-cR

When loggining with the credentials ```Username: Meridius``` and ```Password: HKw@8j$-cR``` this is the result
![Login](/images/login.png)

To bypass this, the originating IP Address has to be modified. Using [Burp Suite](https://portswigger.net/burp), I've captured the request and inserted ```X-Forwarded-For: 127.0.0.1``` which would allow me to spoof the request.
![burpsuite](images/burpsuite.png)

![flag](images/flag.png)
```sh
GCTF{4113n_48duc71n9_c0w5}
```