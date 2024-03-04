# OmnirigBiggerTimeout
OmniRig from VE3NEA fork that enable COM port timeout up to 20000ms instead of 4000ms.<br/>
<br/>
I had problems with OmniRig V1.20 because the timeout we can set on this version is limited to 4000ms.<br/>
In my case, i am using a Magnetic Loop antenna situated 4m away from my TX, <br/>
and i was getting many "Communication error" from WSJT-X program because of the HF fields produced by this nearby antena.<br/>
<br/>
When that araise, i need to click on the "Retry" button in WSJTX error dialog, then reenable transmission by clicking "Enable-TX" button again.<br/>
<br/>
As when clicking "Retry", the communication was etablished again, i suspected that the "Timeout" of 4000ms was too short.<br/>
<br/>
I sent an email to VE3NEA to ask him if he could increase this limited value, but i got no reply.<br/>
So, as this software is a "Freeware", and the sources are published on <a href="https://github.com/VE3NEA/OmniRig">github.com/VE3NEA/OmniRig</a>,<br/>
i forked it, recompiled it using Delphi6 Pascal compiler, then i changed this 4000ms limmit to 20000ms.<br/>
<br/>
I labelled this version <b>V1.21</b><br/>
<br/>
And this solved my problem, as I was able to set the timeout to 8000ms, which is a value that works for me.<br/>
<br/>
The <b>Omnirig.exe</b> file located in this directory is the V1.21 version.<br/>
To use it, you can simply replace the normal V1.20 Omnirig.exe installed by Omnirig legacy setup<br/>
by this one in your <b>C:\Program Files (x86)\Afreet\OmniRig</b> directory<br/>
<br/>
I do it using rename to get a backup of the original V1.20 .exe file.<br/>
While no program using OmniRig is running (i.e: Log4OM closed, WSJT-X closed),<br/>
in a CMD black window, i do:<br/>
    <i>C:</i>
    <i>CD "C:\Program Files (x86)\Afreet\OmniRig"</i>
    <i>REN omnirig.exe omnirig.V120</i>
    <i>COPY C:\users\<username>\Downloads\omnirig.exe .</i>
<br/>
Then you can start Omnirig, and verify in the "About" section that you are running V1.21 version.<br/>
If yes, you can now set the "Timeout" value up to 20s.<br/>
<br/>
Note : A value greater than 4s will loose the begining of the next frame, because your TX will may stay in Transmit mode during the next frame receiving,<br/>
so avoid using too much high values.<br/>
8000 was a good one for me.<br/>
<hr>
