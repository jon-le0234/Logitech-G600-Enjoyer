# Logitech-G600-Enjoyer
A collection of resources for fans of the tragically discontinued Logitech G600 MMO gaming mouse.

# Love for the G600
1. https://www.fictiv.com/teardowns/teardown-showdown-logitech-gaming-mouse-edition-g600-mmo-vs-g502-proteus-spectrum
`
# Buy
It's not coming back any time soon, so buy a few and store them in a safe place. Learn how to repair them by resoldering new switches.

Searched used listings on eBay, Craigslist, Kijiji, etc.

Also look for Logicool G600 sold in Japan.

# Repair

## Testing
XbitLabs has a few tests for your mouse.

https://www.xbitlabs.com/mouse-speed-acceleration-test/

## Skate pads
To open up the mouse, there's a good chance you'll destroy the original skate pads, so order replacements before you get started.

[Corepad Skatez 07919 - PRO 76](https://www.corepad.de/en/Corepad-Skatez-Logitech-Teflon-Mousefeet-Mouse-Feet-Hyperglides-Hyperglide/Corepad-Skatez-PRO-76-Mouse-Feet-Logitech-G600.html
)

[Feetglide FG-077](https://feetglide.com/shop/glides/feetglide-skates-for-logitech-g600-fg-077/)

## Mouse button switches
1. Original: OMRON D2FC-F-7N(20M)
    * [Octopart](https://octopart.com/d2fc-f-7n%2820m%29-omron-131296229)
    * [Datasheet](https://components.omron.com/us-en/sites/components.omron.com.us/files/datasheet_pdf/B152-E1.pdf)
1. Definitive Omron Switch Guide for Mice
    * https://geekhack.org/index.php?topic=81743.0
1. [Micro-switch replacements](https://www.reddit.com/r/MouseReview/comments/jpz3mc/comment/gbk6j9n/)
    1. Omron D2F-01F (w/ plunger mod)
    1. Kailh GM 8.0, 2.0 or 4.0
    1. Zippy DF3
    1. Huano Blue-shell Blue-point
    1. TTC Gold Dustproof (newer revision)
    1. Honeywell UX10C
    1. Cherry ZF DGBE-FL60

## Tactile Switches
1. Original: Omron B3F-1000
    * [Octopart](https://octopart.com/b3f-1000-omron-3117)
    * [Datasheet](https://omronfs.omron.com/en_US/ecb/products/pdf/en-b3f.pdf)

## Scroll wheel
3D printed replacement

[Logitech G600 Scroll Wheel](https://www.printables.com/model/454993-logitech-g600-scroll-wheel)

## Keypad
[Fix intermittent keypad](https://www.ifixit.com/Guide/How+to+fix+Logitech+G600+intermittent+keypad+buttons/155289)

## USB Cable
[Zerk Gaming Mods](https://zerkgamingmods.co.uk/product-category/mouse-cables/)

Plenty available across Aliexpress, eBay, [Amazon](https://www.amazon.ca/SZYDD-Original-Replacement-Braided-1-7-2M/dp/B0DHL3X5ZH), Walmart, etc.

## Weight
Unscrew the [metal weight](https://www.youtube.com/watch?v=PIg7q7rOKc8) inside of the housing.

## Top cover
3D printed replacement

[Top piece replacement for Logitech g600 Mouse](https://www.thingiverse.com/thing:2747969)

# Programming Keys
## Hardware Programming
### Logitech G Hub

Newer, fancier software with wider support for newer devices. Rather bloated piece of software for what it does, and it can have problems running properly, e.g., Windows 11, M1 Mac, Linux.

Graphical. 
Supports macros. 
Switches games and programs automagically.
Settings can be backed up manually.

Strikes an important convention:
View 1 -> Top of themouse
View 2 -> Keypad on the side

### Logitech Gaming Software

The original software that worked with the G600 when it was released. Works on Windows 11. Handy to have as a backup or even a main software.

### g600prog

Cross-platform scrip to program the G600 using Python: https://github.com/tulth/g600prog

Install Python: https://www.python.org/downloads/

Install prerequisite.
```
pip install pyusb
```

Clone the repository.
```
git clone https://github.com/tulth/g600prog
cd g600prog
```

On macOS, use the following command to download the current config from the mouse to your Mac:
```
sudo python3 g600prog.py MOUSE current_mouse_cfg.json
```

After you've created a new config using the provided template, to upload a new config from your Mac to the mouse, use:
```
sudo python3 g600prog.py new_mouse_cfg.json MOUSE
```
## Software Programming
Since the keypad is recognized as a keyboard under the Human Interface Device (HID) class within the OS, we can use any keyboard remapping software.

### keymapper
The one I like most so far is [keymapper](https://github.com/houmain/keymapper). It's a powerful cross platform, context-aware keyboard remapper with a text-based configuration system. 

Most importantly, it can automatically switch behaviours based on attributes like the OS, the window title, device name/ID, etc. Though the hardware programming enables an expansion of functions that can be called from the mouse, the software programming can expand that number even more. This customizability and density sits at the core of the G600's power and beauty. Such a tragedy that it was discontinued.

## Sharing Configurations
If the G600 is programmed with a hardware configuration that has better default keycodes, then software configurations can be more easily shared. G HUB already does this with updates to the hardware profiles for different games, but they stopped short of productivity apps and additional software profiles.

Each workflow maps a little differently based on the user's brain because of things like training, muscle memory, games/applications, etc. But surely there are enough similarities out there that all G600 and MMO mouse users can benefit.

The main limitation of this approach is that the number of "unused" keycodes is limited and dependent on your specific workflows. Also, if you use multiple modes, then there aren't enough unused keycodes that can be used across all 127(?) possible keys.

My bias is that I dont really cycle between the 3 modes at all. I stick with the 1 mode and just G-Shift because that's usually enough for my usage. However, if G600 users stick their heads together, perhaps we can come up with a better way.

## Proposed Default: F13-F24, NumPad, g600prog, keymapper
If people programmed their hardware buttons to the following keycodes, then keymapper configs could be shared more easily.

1. Program the keypad with new default config using g600prog
    1. [F13 through F24](https://old.reddit.com/r/LogitechG/comments/11a49es/g600_mouse_button_beyond_4_and_5/) for View 2
    1. Numpad for some of View 1 and G-Shift for View 2.
    1. G Hub and LGS can be used to program mice this way as well, but it's more work.
1. Customize profile with keymapper
    1. For those that use Numpad on keyboards, keymapper can restrict  remapping to just the G600 using `[device="Gaming Mouse G600"]`.

### View 1
1. #G1 = LeftMouse
1. #G2 = RightMouse
1. #G3 = MiddleMouse
1. G4 = NumpadMultiply
1. G5 = NumpadDivide
1. #G6 = GShift
1. G7 = NumpadAdd
1. G8 = NumpadSubtract

### G-Shift + View 1
I honestly don't find it comfortable using G-Shift with any of the View 1 keys, so I don't have anything to list here.

1. #SG1 = 
1. #SG2 = 
1. #SG3 = 
1. #SG4 = 
1. #SG5 = 
1. #SG6 = # You can't use G-Shift with itself, silly
1. #SG7 = 
1. #SG8 = 

### View 2
1. G9 = F13
1. G10 = F14
1. G11 = F15
1. G12 = F16
1. G13 = F17
1. G14 = F18
1. G15 = F19
1. G16 = F20
1. G17 = F21
1. G18 = F22
1. G19 = F23
1. G20 = F24

### G-Shift + View 2
1. SG9 = Numpad7
1. SG10 = Numpad8
1. SG11 = Numpad9
1. SG12 = Numpad4
1. SG13 = Numpad5
1. SG14 = Numpad6
1. SG15 = Numpad1
1. SG16 = Numpad2
1. SG17 = Numpad3
1. SG18 = Numpad0
1. SG19 = NumpadDecimal
1. SG20 = NumpadEnter

# Further Reading
* [Mouse Guide 2.0: A list of mice with superior sensors and more.](https://geekhack.org/index.php?PHPSESSID=bcc2m478o7flnakttvcctp6qhse82q54&topic=56240.0)