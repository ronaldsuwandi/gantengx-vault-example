Disable annoying shortcut to send link in Safari (cmd+i or cmd+shift+i) using Karabiner-Elements

```json
{
    "description": "Disable mail shortcut on Safari",
    "manipulators": [
        {
            "conditions": [
                {
                    "bundle_identifiers": [
                        "^com.apple.Safari"
                    ],
                    "type": "frontmost_application_if"
                }
            ],
            "from": {
                "key_code": "i",
                "modifiers": {
                    "mandatory": ["left_command"],
                    "optional": ["left_shift", "right_shift"]
                }
            },
            "type": "basic"
        },
        {
            "conditions": [
                {
                    "bundle_identifiers": [
                        "^com.apple.Safari"
                    ],
                    "type": "frontmost_application_if"
                }
            ],
            "from": {
                "key_code": "i",
                "modifiers": {
                    "mandatory": ["right_command"],
                    "optional": ["left_shift", "right_shift"]
                }
            },
            "type": "basic"
        }
    ]
}
```

This one to disable print (cmd+p) in Finder
```json
{
    "description": "Disable print shortcut on Finder",
    "manipulators": [
        {
            "conditions": [
                {
                    "bundle_identifiers": [
                        "^com.apple.finder"
                    ],
                    "type": "frontmost_application_if"
                }
            ],
            "from": {
                "key_code": "p",
                "modifiers": {
                    "mandatory": ["left_command"],
                    "optional": []
                }
            },
            "type": "basic"
        },
        {
            "conditions": [
                {
                    "bundle_identifiers": [
                        "^com.apple.finder"
                    ],
                    "type": "frontmost_application_if"
                }
            ],
            "from": {
                "key_code": "p",
                "modifiers": {
                    "mandatory": ["right_command"],
                    "optional": []
                }
            },
            "type": "basic"
        }
    ]
}
```
