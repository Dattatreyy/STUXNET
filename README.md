#                                                                      STUXNET

Stuxnet is a computer worm that was originally aimed at Iran's nuclear facilities and has since mutated and spread to other industrial and energy-producing facilities. The original Stuxnet malware attack targeted the programmable logic controllers (PLCs) used to automate machine processes.

Read More : https://www.trellix.com/en-us/security-awareness/ransomware/what-is-stuxnet.html

Here we will extract payload from the payload, that means double unpacking

File name : WTR4132.TMP

We can see Pretty high entropy here

<img width="360" alt="nrl3" src="https://user-images.githubusercontent.com/107531426/205477428-f79ff54f-cb23-4657-8ac2-461d3ea3dc75.PNG">

.stub section contains main stuxnet payload.

This Section (".stub") includes also the configuration data of stuxnet which is so important on the spreading mechanism, updating mechanism and many other things.

<img width="760" alt="nrl3" src="https://user-images.githubusercontent.com/107531426/205477609-a26c0a64-adaf-4ef5-864f-6708fbb94e5c.PNG">

Using VirtualProtect Payload is unpacking itself in the memory

<img width="760" alt="nrl3" src="https://user-images.githubusercontent.com/107531426/205477615-e8a91803-612f-402c-b344-69eeebac7691.PNG">

Loading the DLL after enabling "DLL Load" and "DLL Entry" in debugger. 

Going to the entrypoint of the sample

<img width="760" alt="nrl3" src="https://user-images.githubusercontent.com/107531426/205477809-15a51b1c-8c5c-427f-ab9c-d043ad2efa48.PNG">

Applying breakpoint at the end of VirtualProtect. 

Then will go to the entrypoint execute the sample untill we hit our breakpoint and then one step over will take you to the payload where the malware is unpacking itself

<img width="760" alt="nrl3" src="https://user-images.githubusercontent.com/107531426/205477823-dd7c551d-a982-4d6e-bdc0-167568766da7.PNG">

We know that .stub is the section where the malware is residing. In IDA we can the starting offset of .stub "1000600"

<img width="760" alt="nrl3" src="https://user-images.githubusercontent.com/107531426/205477838-ec1d5b85-4374-4b52-892f-6eb5f68f5f60.PNG">

Dump the ESI register with the same offset to find the payload

<img width="760" alt="nrl3" src="https://user-images.githubusercontent.com/107531426/205477845-96ae2d37-f883-4941-a1b9-729986d6a388.PNG">



