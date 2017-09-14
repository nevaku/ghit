I need to automate some of task of my web application. It contains some boring crud operations with a lot of data to enter. I found <B>Selenium</B> as a good plugin of Mozilla Firefox to do this. Unfortunatelly it was not last for long, when Firefox upgrades its framework and all of my funs just stop working. I decided to use javascript+jquery to do this automations. However things are not work perfectly. Javascript only allow single thread to run for a page. Things get event worst when waiting for certain actions using timeout or other methods, because it worked asynchronously. My test code works but the code was a mess. I have to chain one function to another as a call back of the timeout wait methods.

Later, I have to make this synchronously. There should be a better way. I start to think about stack and execution pointer and so on and here comes the <B>syncjs</B>. It stores the block of statements as execution pointers into an array. An executor will execute this block one by one until it reach the end. It may stop at a block to <B>wait</B> the condition becomes true, for a while. Then it continue to the next block. I also define some <B>if-else-end</B> scenario to skip blocks if the condition was/wasn't met. I will also add loop-end which will move the execution point back at the beginning of the loop, or when the loop finish continue as usual.

So here is the <B>syncjs</B> features:
<ul>
<li> Synchronously run your block of code through javascript async framework
<li> If-elseif-else-end scenario
<li> wait, with progressif delay.
<li> Standard javascript syntax
<ul>
This is a javascript library if you want to automate or test your web application.