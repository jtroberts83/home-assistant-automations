# Dynamic Unifi Camera Switching With ViewPort

## Prereqs:
- Home Assistant (installed and running)
- Unifi Protect Integration configured (https://www.home-assistant.io/integrations/unifiprotect/)
- Unifi Protect Viewport device
- Unifi Protect Cameras
- In the Unifi Protect app, create, name and share single camera views for each camera as well as a default multi-view you want the viewport to default to. (To name and share with your local unifi users including your Home Assistant user, you must click on Settings)

## To configure dynamic camera switching in Home Assistant you will create a new blank automation and set it up as follows: (Screenshot below and YAML config attached)
Triggers:
- Select your camera device from the device list and then choose the camera triggere for people or vehicles detected (or setup a trigger for both)
- (Optional) configure what days and times you want it to dynamically switch
- From the actions you will choose the Unifi Viewport from the devices list and then choose the option to set the liveview to a particular option and choose the single camera view you created for the particular camera triggereing the detections
- Set a specified delay period (I used around 20 seconds)
- After the delay set another action which checks the State of a device and choose your Viewport device and then have it check to see if it is still on the same camera that you setup above
- Set an additional action if is passes the condition check above to set the viewport back to the default multi-view


![alt text](https://github.com/jtroberts83/home-assistant-automations/blob/main/ViewportAutomation.jpg?raw=true)

## To setup the YoLink Remote:
- Purchase a YoLink 4 button Fob and Hub if you don't already have one (Hub is required) - [Amazon Link](https://www.amazon.com/FlexFob-4-Button-Functions-Routines-Included/dp/B0BJK75MDL/ref=sr_1_6?crid=3HT9EZE150YZC&dib=eyJ2IjoiMSJ9.SIuw_uwFMoL-Fj_slVStEQZRrvXm_pJ7e8n71q5aJ3EgbOlzMnUncmh-PbtAeXCPc7_ZOKmKHo8G5yCLUhLjO2KWqma7b7rgN8nQVBLcfgHO2dVnGGO6TA6kjs8_q4ICZNcFSGko7nag8bFttz7OPJEkCyMf_D9TRHvExgQc0P5-N4KF_npCLqXofhMXV1M86G65q18HhoLPHq_CA9v33ynfym_HcbcScZRnSQP2giig1-DVsiu5KwjCI0eIRxBR--xkUnGnSIUkdj243Who7LFfZppH1_IkIA4l_vzHzLI.A8iRPfAZkw3zO35ijTlxPgOG4b4pdWkYu-z1_v0_31U&dib_tag=se&keywords=yolink+fob&qid=1714493897&sprefix=yolink+fob%2Caps%2C125&sr=8-6)
- Add the YoLink Home Assistant integration - [YoLink Integration](https://www.home-assistant.io/integrations/yolink/)  
- Duplicate the above dynamic camera automations and change the triggers from Camera AI events to the YoLink remote button pushes
- Save and done. Enjoy!

