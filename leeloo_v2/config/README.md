# Clickety Split | Leeloo v2

![Leeloo](https://cdn.shopify.com/s/files/1/0599/3460/5491/files/Leeloo-rev1.0-w.jpg?v=1646798726)

Keyboard Designer: [clicketysplit.ca](https://clicketysplit.ca)
GitHub: [ClicketySplit](https://github.com/ClicketySplit)
Hardware Supported: Pro Micro, Elite-C, nice!nano v2

Albeit, there is no doubt where Leeloo's heritage is derived from—Lily58, and Corne.  It is not a copy-paste-modify implementation.

Leeloo has been designed from scratch; everything from the schematic to its PCB footprints, and column stagger. There are some subtle differences that may not be apparent; however, its subtle changes enable an interesting future.

Features:
* 4x6x5m Split Keyboard
* Support for MX/Box or Low Profile Choc switches.
* 90% of the switches are socketed; with the exception to the rotary encoder positions—6 positions require soldering.
* Support for 128x32 OLED Displays.
* The option to select one of three positions for an EC11 rotary encoder on each half.
* Support for Alps Alpine Micro Switch
* Support for 3.7v 301230 LiPo Battery

# Building Your Firmware
ZMK Firmware: [Introduction to ZMK](https://zmk.dev/docs/)
Installation: [Installing ZMK](https://zmk.dev/docs/user-setup)
Customization: [Customizing ZMK](https://zmk.dev/docs/customization)
Development Environment: [Basic Setup](https://zmk.dev/docs/development/setup)

Note: With Zephyr 4.1, the board name is `nice_nano` (formerly `nice_nano_v2`).

Build command for the default keymap of Leeloo:

    west build -d build/left -p -b nice_nano -- -DSHIELD=leeloo_left
    west build -d build/right -p -b nice_nano -- -DSHIELD=leeloo_right

Build command for your custom keymap of Leeloo:

    west build -d build/right -p -b nice_nano -- -DSHIELD=leeloo_right -DZMK_CONFIG="C:/zmk/[alias]/leeloo/config"
    west build -d build/left -p -b nice_nano -- -DSHIELD=leeloo_left -DZMK_CONFIG="C:/zmk/[alias]/leeloo/config"

Build command with nice!view:
    west build -d build/left -p -b nice_nano -- -DSHIELD="leeloo_left nice_view_adapter nice_view" -DZMK_CONFIG="/workspaces/zmk-config/[alias]/leeloo/config"
    west build -d build/right -p -b nice_nano -- -DSHIELD="leeloo_right nice_view_adapter nice_view" -DZMK_CONFIG="/workspaces/zmk-config/[alias]/leeloo/config"

    # spencer config
    west build -d build/left -p -b nice_nano -- -DSHIELD="leeloo_rev2_left nice_view_adapter nice_view" -DZMK_CONFIG="/workspaces/zmk-config/leeloo_v2/config"
    west build -d build/right -p -b nice_nano -- -DSHIELD="leeloo_rev2_right nice_view_adapter nice_view" -DZMK_CONFIG="/workspaces/zmk-config/leeloo_v2/config"

    For Corne Keyboards:
    // Overwrite the display cs pin
    &nice_view_spi {
        cs-gpios = <&pro_micro 4 GPIO_ACTIVE_HIGH>;
    };

    NOTE: 4 equates to D4, or P0.22 on the nice!nano MCU.

    Compile with:
    west build -d build/left -p -b nice_nano -- -DSHIELD="leeloo_left nice_view_adapter nice_view" -DZMK_CONFIG="/workspaces/zmk-config/[alias]/leeloo/config"
    west build -d build/right -p -b nice_nano -- -DSHIELD="leeloo_right nice_view_adapter nice_view" -DZMK_CONFIG="/workspaces/zmk-config/[alias]/leeloo/config"


    For Corne Keyboards:
    // Overwrite the display cs pin
    &nice_view_spi {
        cs-gpios = <&pro_micro 0 GPIO_ACTIVE_HIGH>;
    };

    NOTE: 0 equates to D0, or P0.08 on the nice!nano MCU.

    Compile with:
    west build -d build/left -p -b nice_nano -- -DSHIELD="corne_left nice_view_adapter nice_view" -DZMK_CONFIG="/workspaces/zmk-config/[alias]/corne/config"
    west build -d build/right -p -b nice_nano -- -DSHIELD="corne_right nice_view_adapter nice_view" -DZMK_CONFIG="/workspaces/zmk-config/[alias]/corne/config"


# Support
If you have any questions with regards to Leeloo, please [Contact Us](https://clicketysplit.ca/pages/contact-us).

Clickety Split
For the love of split keyboards.
