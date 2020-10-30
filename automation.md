# Automation

![alt text](https://github.com/tuanha2000vn/Home-Assistant-Dashboard/blob/master/images/push_notification_2.png?raw=true)

* Home-Dashboard let you create sophisticated automation without having to code. All condition are pre-selected making Automation easy, bug free and just work!

***

## 1. Setup

To enable Automation feature, please check the following steps:

***

Make sure `automation.yaml` added to `configuration.yaml`

```yaml
automation: !include automations.yaml
```


***

If you already have automation in various file, include both single `automation.yaml` and `automations directory` like this

```yaml
automation: !include automations.yaml
automation mine: !include_dir_merge_list automations/
```
***

If you want to send notification with picture, create a folder name `www` inside `config folder` and add the following line added to `configuration.yaml`

```yaml
homeassistant:
  allowlist_external_dirs:
    - /config/www
```
***

![alt text](https://github.com/tuanha2000vn/Home-Assistant-Dashboard/blob/master/automation/a.push.png?raw=true)

* Go to Setting > Enable Push Notification > Restart Home Assistant

***

## 2. Simple Automation: 
    Turn light on when movement detected

![alt text](https://github.com/tuanha2000vn/Home-Assistant-Dashboard/blob/master/automation/a.1.1.png?raw=true)

* Create new Automation: Go to Automation tab > Top right menu > Create automation > Wait few second > Click the newly created Automation > Edit automation > Change name to "# Turn light on when movement detected"

![alt text](https://github.com/tuanha2000vn/Home-Assistant-Dashboard/blob/master/automation/a.1.2.png?raw=true)

* Create new trigger > Device state changed > Select device > Click To > Set to "On"

***

![alt text](https://github.com/tuanha2000vn/Home-Assistant-Dashboard/blob/master/automation/a.1.3.png?raw=true)

* Create new action > Change device state > Select device > Click Light/Switch > Set To "Turn On"

***

![alt text](https://github.com/tuanha2000vn/Home-Assistant-Dashboard/blob/master/automation/a.1.4.png?raw=true)

* Final result

***

## 3. Intermadiate Automation: 
    Turn light on when I'm coming home but only after 18:00 and before 22:00

![alt text](https://github.com/tuanha2000vn/Home-Assistant-Dashboard/blob/master/automation/a.2.1.png?raw=true)

* Create new triger > Location > Select device > Set Even to "Enter" > Set Zone to Home

* Create new condition > Specific time > Select device > Set After to "18:00:00" > Set Before to "22:00:00"

* Create new action > Change device state > Select device > Click Light/Switch > Set to "Turn On"

***

## 4. Advance Automation: 
    Send notification to my phone with picture of camera 1 if garage door opened for more than 1 minute when I'm at school

![alt text](https://github.com/tuanha2000vn/Home-Assistant-Dashboard/blob/master/automation/a.3.1.png?raw=true)

* Create new triger > Device state changed > Select a door > Click To > Set To "On" > Set For "00:01:00" 

* Create new condition > Location > Select your phone > Set Zone to "School"

* Create new action > Save camera image > Select Camera 1

* Create new action > Push notification > Select device > Change Notify title to "Door Opened for more than 1 minute" > Change Notify message to "Here the camera 1 image" > Camage image: Select camera 1