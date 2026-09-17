# meshcore_homeassistant_pathbot
Home Assistant automation that works with the Meshcore addon to create a automatic path bot message reply.

I had a companion Mescore radio connected to my Home Assistant installation, using the Meshcore HA addon.
I wanted to contribute to the #testing channel, as there was no active pathbot running in my area.

So this simple automation was created for Home Assistant.

## Prerequisites
- Home Assistant operating system
- Meshcore HA addon installed [Meshcore Home Assistant Addon](https://github.com/meshcore-dev/meshcore-ha)
- Meshcore companion device connected to Home Assistant via USB
- #testing channel added to the Meshcore companion device
- A good reliable connection to your local Meshcore network.

## References
This Home Assistant automation takes inspiration and is influenced by these two projects.

**Pathbot YAML**\
[Pathbot YAML](https://gist.github.com/andyshinn/73a4f978a82c10d2aa24b03edcb4fcac)\
A Home Assistant automation written in YAML

**Meshcore Bot**\
[meshcore-bot](https://github.com/agessaman/meshcore-bot)\
A Python bot with a full set of tools and features. Does way more than my simple automation.

I've looked at the path response behaviour of the MeshCore-Bot and further added to the Pathbot YAML automation.

## YAML Edit
Within the YAML file there are some parts that need to be edited to customise this automation to your needs.

[CHANNEL_ID]
The channel ID for the #testing channel added to the companion device.\
[CODE]  
Text that the automation will look for in the Meshcore messages it recieves. This will trigger a automated message detailing the message path.\
[LOCATON] 
The location of the pathbot, used in message responses.

## USAGE
The automation will only respond to messages in the channel you setup, usually #testing.\
And it will only respond to "!bot" or the "code" you setup within the automation.

If a message in #testing is received that says "!bot"\
Automation will respond with:
```
@SENDER Use "CODE" for "LOCATION"
```
If a message in #testing is received that says "CODE"\
Automation will reply with:
```
@SENDER recv [LOCATON]
Hops: 4
Path: 88D2, A341, E321, 44A2
```
