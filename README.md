# Home_Automation_App
Home Automation App with Bolt IoT
### Things used in this product
Hardware required
The Bolt Wifi module
1 x 330 ohm Resistor
1 x LED

Software and online services:
![Bolt Cloud](cloud.boltiot.com)
![Bolt Cloud Android App](https://play.google.com/store/apps/details?id=com.bolt.com.bolt&hl=en_IN&gl=US)

### Steps for building the product
Connecting the LED to the Bolt
Step 1: Insert the positive leg of the LEDs and BUZZER in digital pin 1,2,3.... of the Bolt.
Step 2: Insert the negative leg of the LEDs and BUZZER into the ground pin of the Bolt.

to control the LEDs and BUZZER using Bolt Cloud
Step 1: Go to cloud.boltiot.com and create a new product. While creating the product, choose product type as Output Device and interface type as GPIO. After creating the product, select the recently created product and then click on configure icon.
Step 2: Move to the code tab and write the following code to control the LED.
//HTML code
<!DOCTYPE html>
<html>
    <head>
        <title>Bolt IoT Platform</title>
        <script type="text/javascript" src="https://cloud.boltiot.com/static/js/boltCommands.js"></script>
        <script>
        setKey('{{ApiKey}}','{{Name}}');
        </script>
    </head>
    <body>
        <center>
        <button onclick="digitalWrite(0, 'HIGH');">ON</button>
        <button onclick="digitalWrite(0, 'LOW');">OFF</button>
        </center>
    </body>
</html>

//Javascript code
singleButton({name:"Led On", action:"digitalWrite", 
              pin:"0", value:"HIGH",bgcolor:"green",
              shape:"rectangle",align:"left","text_color":"white" })
singleButton({name:"Led Off", action:"digitalWrite", 
              pin:"0", value:"LOW", bgcolor:"red",
              shape:"rectangle", align:"left", text_color:"black"})
singleButton({name:"Fan On", action:"analogWrite", 
              pin:"0", value:"230",bgcolor:"#ffa500",
              shape:"circle", align:"right","text_color":"white" })
singleButton({name:"Fan Off", action:"analogWrite", 
              pin:"0", value:"0",bgcolor:"#6a5acd",
              shape:"circle", align:"right", text_color:"white"})
							
Step 3: Once you have written the complete code in the editor, give the file name as ledcontrol and in the drop-down select the file extension as html or js. 
Step 4: Now click on save icon to save the code. Now go back to the dashboard by clicking on 'X' icon.
Step 5: In the products tab, select the product created and then click on the link icon. Select your Bolt device in the popup and then click the 'Done' button.
Step 6: Now click on view this device icon to view the page that you have designed.
