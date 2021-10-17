# Static
___Category:___ Misc
## Challenge Details
swish swoosh  
![hidden.png](images/hidden.png)

## Write Up
Initially, the given image looks like static and nothing can be deciphered. However, using a tool such as [StegSolve](https://github.com/eugenekolo/sec-tools/tree/master/stego/stegsolve/stegsolve), I noticed that a manipulated QR Code can be seen at ```red plane 2```.  
![](images/1.png)

The image is then cropped and can easily be "unswirled" using [Gimp](https://www.gimp.org/).
After opening the image, navigate to ```Filters > Distorts > Whirl and Pinch...``` and adjust until the QR Code is fairly visible.  
![](images/2.png)

Obviously the QR Code is not readable yet. Using an online tool like [Qrazybox](https://merricx.github.io/qrazybox/), I was able piece out and restore the image.  
![](images/3.png)

When finished, Qrzazy box is also able to decode the QR Code which revealed the flag.  
![](images/4.png)

## Flag:
```
GCTF{h1dd3n_5w1213d_1m4935}
```
