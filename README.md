#                                                                      STUXNET

Stuxnet is a computer worm that was originally aimed at Iran's nuclear facilities and has since mutated and spread to other industrial and energy-producing facilities. The original Stuxnet malware attack targeted the programmable logic controllers (PLCs) used to automate machine processes.

Read More : https://www.trellix.com/en-us/security-awareness/ransomware/what-is-stuxnet.html

Here we will extract payload from the payload, that means double unpacking

File name : WTR4132.TMP

We can see Pretty high entropy here

<img width="760" alt="nrl3" src="https://user-images.githubusercontent.com/107531426/205477428-f79ff54f-cb23-4657-8ac2-461d3ea3dc75.PNG)

.stub section contains main stuxnet payload.

This Section (".stub") includes also the configuration data of stuxnet which is so important on the spreading mechanism, updating mechanism and many other things.

<img width="760" alt="nrl3" src="https://user-images.githubusercontent.com/107531426/205477609-a26c0a64-adaf-4ef5-864f-6708fbb94e5c.PNG">

Using VirtualProtect Payload is unpacking itself in the memory

![stux3](https://user-images.githubusercontent.com/107531426/205477615-e8a91803-612f-402c-b344-69eeebac7691.PNG)

<img width="760" alt="nrl3" src="https://user-images.githubusercontent.com/107531426/205477809-15a51b1c-8c5c-427f-ab9c-d043ad2efa48.PNG">
<img width="760" alt="nrl3" src="https://user-images.githubusercontent.com/107531426/205477823-dd7c551d-a982-4d6e-bdc0-167568766da7.PNG">
<img width="760" alt="nrl3" src="https://user-images.githubusercontent.com/107531426/205477838-ec1d5b85-4374-4b52-892f-6eb5f68f5f60.PNG">
<img width="760" alt="nrl3" src="https://user-images.githubusercontent.com/107531426/205477845-96ae2d37-f883-4941-a1b9-729986d6a388.PNG">



