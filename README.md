# RN2483-TTS-CE-v3-Basic-commands
RN2483-TTS-CE (v3) Basic commands (OTAA and ABP) 

To get the DevEUI for the RN2483 module:
mac get deveui

When an Over-the-Air Activation (OTAA) device is registered we are provided with:

    AppEUI
    AppKey

On start-up the module will need to be configured with these before it can request to join the network and following which, if successful, it will then be allocated a network address and session encryption keys will be configured.

> mac set appeui AAAAAAAAAAAAAAAA             
> mac set appkey KKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKK               
> mac save                
> mac join otaa             

Activation By Personalisation (ABP) device is registered we are provided with:

    Devaddr
    Nwkskey
    Appskey

> mac set devaddr AAAAAAAA                           
> mac set nwkskey KKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKK   
> mac set appskey KKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKK   
> mac save                                           
> mac join abp                                       
