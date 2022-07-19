# Copy / Paste Nodes

Copying and Pasting nodes can be a quick and convenient way to duplicate nodes within your current flow graph, copy selected nodes between different node editor flows or to share node configuration with others online without having to send an entire flow file.

When cutting/copying selected nodes the node editor is actually querying the node state for each selected node and building a JSON object with all the relevant node information and connections as well as relative node placement to each other. Similar to the .flow file format used by the node editor to load and save flows.

You can paste the clipboard from a copied node graph into a text editor and it will look like this:
```json
{
    "connections": [
        {
            "from_id": 2001,
            "from_idx": 0,
            "to_id": 3001,
            "to_idx": 0
        }
    ],
    "editor": [
        {
            "id": 2001,
            "location": {
                "x": 742.0,
                "y": 8.0
            }
        },
        {
            "id": 3001,
            "location": {
                "x": 940.0,
                "y": 33.0
            }
        }
    ],
    "nodes": [
        {
            "id": 2001,
            "name": "Video_Capture",
            "params": {
                "camera_settings": {
                    "Auto Exposure": -1.0,
                    "Backlight": -1.0,
                    "Brightness": -1.0,
                    "Contrast": -1.0,
                    "Exposure": -1.0,
                    "Focus": -1.0,
                    "Gain": -1.0,
                    "Gamma": -1.0,
                    "Hue": -1.0,
                    "ISO Speed": -1.0,
                    "Iris": -1.0,
                    "Saturation": -1.0,
                    "Sharpness": -1.0,
                    "Zoom": -1.0
                },
                "force_index": false,
                "fps": 30,
                "fps_index": 7,
                "list_index": 0,
                "set_load_man": false,
                "src_index": 0,
                "src_mode": 4,
                "src_name": "System Default"
            }
        },
        {
            "id": 3001,
            "name": "Transform",
            "params": {
                "aspect_mode": 0,
                "flip_mode": 0,
                "interp_mode": 0,
                "rotate_amt": 0.0,
                "rotate_mode": 0,
                "scale": {
                    "x": 100.0,
                    "y": 100.0
                },
                "scale_mode": 0,
                "translate": {
                    "x": 0,
                    "y": 0
                }
            }
        }
    ]
}
```

You can edit the information to make changes if needed or paste the buffer to someone on Slack or Discord and they can then paste that buffer into their node editor and get your same nodes, settings and relative layout to start working with.



