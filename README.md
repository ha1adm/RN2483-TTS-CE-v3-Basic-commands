# RN2483-TTS-CE-v3-Basic-commands
RN2483-TTS-CE (v3) Basic commands (OTAA and ABP) 

To resets the module firmware to default values, plus clears the EEPROM
> sys factoryRESET

To get the DevEUI for the RN2483 module:
> mac get deveui

When an Over-the-Air Activation (OTAA) device is registered we are provided with:

    AppEUI
    AppKey

On start-up the module will need to be configured with these before it can request to join the network and following which, if successful, it will then be allocated a network address and session encryption keys will be configured.

Auto reply is setted up here for confirmed Downlinks. If the application needs otherwise make manual replys. Also If your node is stationary, ADR could help to optimise DataRate. (And higly suggested)

> mac set appeui AAAAAAAAAAAAAAAA             
> mac set appkey KKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKK   
> mac set adr on        
> mac set ar on             
> mac save                
> mac join otaa             

Activation By Personalisation (ABP) device is registered we are provided with:

#Note: For some reason I can't get the device to automatically adjust the RX1 window form the factory default 1s to 5s.
(As requested by the Network server. So I added this line manually. After This ADR and Downlink is working correctly)

Auto reply is setted up here for confirmed Downlinks. If the application needs otherwise make manual replys. Also If your node is stationary, ADR could help to optimise DataRate. (And higly suggested)


    Devaddr
    Nwkskey
    Appskey

> mac set devaddr AAAAAAAA                           
> mac set nwkskey KKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKK   
> mac set appskey KKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKK                  
> mac set rxdelay1 5000     
> mac set adr on        
> mac set ar on         
> mac save                                           
> mac join abp                                       
