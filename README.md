# Project-Code
import time

import random

myConfig = {

"identity":{

    "orgId":"e6dgwr",

    "typeId":"iotdevice",

    "deviceId":"1234"

 },

 "auth":{

     "token":"UK!ox2syaH2ExIhTo1"

}
}

def myCommandCallback(cmd):

print("Message received from IBM IoT Platform: %s" % cmd.data['command'])

m=cmd.data['command']
client = wiotp.sdk.device.DeviceClient(config=myConfig, logHandlers=None)

client.connect()

def pub(data):

client.publishEvent(eventId="status", msgFormat="json", data=myData, qos=0, onPublish=None)

print("Published data Successfully: %s", myData)
while True:

myData={'name':'Train1','lat': 8.0883,'lon': 77.5385}

pub(myData)

time.sleep(3)

myData={'name':'Train1','lat': 13.0827,'lon': 80.2707}

pub(myData)

time.sleep(3)

myData={'name':'Train1','lat': 12.9716,'lon': 77.5946}

pub(myData)

time.sleep(3)

myData={'name':'Train1','lat': 17.3850,'lon': 78.4867}

pub(myData)

time.sleep(3)

myData={'name':'Train1','lat': 23.2599,'lon': 77.4126}

pub(myData)

time.sleep(3)

myData={'name':'Train1','lat': 28.7041,'lon': 77.1025}

pub(myData)

time.sleep(3)

myData={'name':'Train1','lat': 33.2778,'lon': 75.3412}

pub(myData)

time.sleep(3)

client.commandCallback = myCommandCallback
client.disconnect()
