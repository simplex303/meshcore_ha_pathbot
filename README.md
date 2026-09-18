# meshcore_homeassistant_pathbot
Home Assistant automation that works with the Meshcore addon to create a automatic path bot message reply.

I have a companion Mescore radio connected to my Home Assistant installation, using the Meshcore HA addon.
I wanted to contribute to the #testing channel, as there was no active pathbots running in my area.

So this automation was created in Home Assistant to act on messages it received.

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

[CHANNEL_ID]\
The channel ID for the #testing channel added to the companion device.

[CODE]  \
Text that the automation will look for in the Meshcore messages it receives, within the setup channel ID.\
Will trigger on any upper or lower case combination.\
When this text is seen the automation is triggered an automated message detailing the message path is sent.

[LOCATON] \
The location of the pathbot, used in message responses.

## USAGE
The automation will only respond to messages in the channel you setup, usually #testing.\
And it will only respond to "!bot" or the "code" you setup within the automation.\

The "code" is a short text string that represents the area your pathbot is operating in.\
Pick a code that is unique across the whole Meshcore network.\
AKL = Auckland\
PNL = New Plymouth\
etc

### !bot
If a message in #testing is received that says "!bot"\
Automation will respond with:
```
@SENDER Use "CODE" for "LOCATION"
```
Allows users to find the pathbots that are reachable from their location.

### code
If a message in #testing is received that says "CODE"

Automation will reply with:
```
@SENDER recv [LOCATON]
Hops: 4
Path: 88D2, A341, E321, 44A2
```
