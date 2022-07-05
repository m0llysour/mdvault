_exploit_ modules are defined as modules that use payloads.
_Auxiliary_ modules include port scanners, fuzzers, sniffers, and more.
_Payloads_ consist of code that runs remotely, while _encoders_ ensure that payloads make it to their destination intact. _Nops_ keep the payload sizes consistent across exploit attempts.

 you can switch modules from within other modules
 variables will only carry over if they are set globally.

Active exploits will exploit a specific host, run until completion, and then exit.
Passive exploits wait for incoming hosts and exploit them as they connect.

payload in Metasploit refers to an exploit module. There are three different types of payload modules in the Metasploit Framework: **Singles**, **Stagers**, and **Stages**.

Singles are payloads that are self-contained and completely standalone. A Single payload can be something as simple as adding a user to the target system or running calc.exe.
These kinds of payloads are self-contained, so they can be caught with non-metasploit handlers such as netcat.

Stagers setup a network connection between the attacker and victim and are designed to be small and reliable.

Stages are payload components that are downloaded by Stagers modules.

A single payload containing the exploit and full shell code for the selected task. Inline payloads are by design more stable than their counterparts because they contain everything all in one.

Stager payloads work in conjunction with stage payloads in order to perform a specific task. A stager establishes a communication channel between the attacker and the victim and reads in a stage payload to execute on the remote host.

Meterpreter, the short form of Meta-Interpreter is an advanced, multi-faceted payload that operates via dll injection.

When confronted with  a Windows target, identifying which patches have been applied is an easy way of knowing if regular updates happen. It may also provide information on other possible vulnerabilities present on the system.

An auxiliary module was specifically created for just this task called **enum_patches**. Like any post exploitation module, it is loaded using the **use** command.

-   There is always a _Payload Information Block_. An Exploit without a Payload is simply an Auxiliary Module.