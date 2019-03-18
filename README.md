# iOS Development Guides
Library of useful links, tips and hacks that I use. 
## Guides

### Certificates 

#### Push certificates

##### Create
[Create push certificate guide](https://medium.com/@ankushaggarwal/generate-apns-certificate-for-ios-push-notifications-85e4a917d522)

##### Convert to .pem
<code>openssl pkcs12 -in pushcert.p12 -out pushcert.pem -nodes -clcerts</code>
### Sources

#### Add custom fonts

[Apple guide](Geometria-Bold.otf Geometria-BoldItalic.otf Geometria-ExtaBlack.otf Geometria-ExtraBlackItalic.otf Geometria-ExtraLight.otf Geometria-ExtraLightItalic.otf Geometria-Heavy.otf Geometria-HeavyItalic.otf Geometria-Italic.otf Geometria-Light.otf Geometria-LightItalic.otf Geometria-Medium.otf Geometria-MediumItalic.otf Geometria-Thin.otf Geometria-ThinItalic.otf Geometria.otf)

## Theory

### GCD vs NSOperation

 - __GCD__ is a lightweight way to represent units of work that are going to be executed concurrently. You don’t schedule these units of work; the system takes care of scheduling for you. Adding dependency among blocks can be a headache. Canceling or suspending a block creates extra work for you as a developer!

 - __Operation__  adds a little extra overhead compared to GCD, but you can add dependency among various operations and re-use, cancel or suspend them.
 
##### Stop block execution using GCD
###### Objective-C (iOS 8.0+)
```Objective-C
dispatch_block_t work = dispatch_block_create(0, ^{
  NSLog(@"Hello.");
});
dispatch_after(dispatch_time(DISPATCH_TIME_NOW, (int64_t)(10 * NSEC_PER_SEC)), dispatch_get_main_queue(), work);

dispatch_block_cancel(work)
```
### ARC

```classes``` are involved in __ARC__(Automatic refernce counter).

ARC counts only __strong__ refernces to the object insntances and deallocates it, when count become zero.

By default all references are __strong__
```Swift
var a: A = A()
```
To prevent counting you can use __weak__ or __unowned__ references

### Memory

Class references stay in Run Time Stack (RTS) and their instances stay in Heap area of Memory.



