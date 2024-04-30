# home-assistant-automations
Prereqs:
- Home Assistant (installed and running)
- Unifi Protect Integration configured (https://www.home-assistant.io/integrations/unifiprotect/)
- Unifi Protect Viewport device
- Unifi Protect Cameras
- In the Unifi Protect app, create, name and share single camera views for each camera as well as a default multi-view you want the viewport to default to. (To name and share with your local unifi users including your Home Assistant user, you must click on Settings)

To configure dynamic camera switching in Home Assistant you will create a new blank automation and set it up as follows:
Triggers:
- Select your camera device from the device list and then choose the camera triggere for people or vehicles detected (or setup a trigger for both)
- (Optional) configure what days and times you want it to dynamically switch
- From the actions you will choose the Unifi Viewport from the devices list and then choose the option to set the liveview to a particular option and choose the single camera view you created for the particular camera triggereing the detections
- Set a specified delay period (I used around 20 seconds)
- After the delay set another action which checks the State of a device and choose your Viewport device and then have it check to see if it is still on the same camera that you setup above
- Set an additional action if is passes the condition check above to set the viewport back to the default multi-view


![alt text](https://github.com/jtroberts83/[reponame]/blob/[branch]/image.jpg?raw=true)

