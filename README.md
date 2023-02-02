# GMS2_Controller_Boilerplate
GMS2 Controller Boilerplate setup. Use in your projects. 

I made this because:
* [Yoyo's docs barely get you started, and are often incomplete, and missing examples](https://manual.yoyogames.com/GameMaker_Language/GML_Reference/Game_Input/GamePad_Input/Gamepad_Input.htm)
* [Google search has incomplete and promoted content](https://www.google.com/search?q=gms2+gamepad+boilerplate)

So, here's a no-frills full-mapping of a whole Xbox controller that functions well. While I still have patience for Yoyo, I'll do things like this, but I'm close to jumping ship after I found my app with no network functionality was phoning-home to Yoyo.

### Set your analog tolerance
```analog_tolerance = 0.6``` 

### Analog Left
// Analog Left Check for 8 different positions (including diagonal)
```
al_right_up = (l_horizontal_axis > analog_tolerance && l_vertical_axis < -analog_tolerance) 
al_right_down = (l_horizontal_axis > analog_tolerance && l_vertical_axis > analog_tolerance)
al_left_up = (l_horizontal_axis < -analog_tolerance && l_vertical_axis < -analog_tolerance) 
al_left_down = (l_horizontal_axis < -analog_tolerance && l_vertical_axis > analog_tolerance) 
al_right = (l_horizontal_axis > analog_tolerance)
al_left = (l_horizontal_axis < -analog_tolerance) 
al_up = (l_vertical_axis < -analog_tolerance)
al_down = (l_vertical_axis > analog_tolerance) 
al_push = gamepad_button_check_pressed(0,gp_stickl) // L3
```

### Analog Right
```
ar_right_up = (r_horizontal_axis > analog_tolerance && r_vertical_axis < -analog_tolerance) 
ar_right_down = (r_horizontal_axis > analog_tolerance && r_vertical_axis > analog_tolerance)
ar_left_up = (r_horizontal_axis < -analog_tolerance && r_vertical_axis < -analog_tolerance) 
ar_left_down = (r_horizontal_axis < -analog_tolerance && r_vertical_axis > analog_tolerance) 
ar_right = (r_horizontal_axis > analog_tolerance)
ar_left = (r_horizontal_axis < -analog_tolerance) 
ar_up = (r_vertical_axis < -analog_tolerance)
ar_down = (r_vertical_axis > analog_tolerance) 
ar_push = gamepad_button_check_pressed(0,gp_stickr) // R3
```

### Dpad
```
key_dpad_u = gamepad_button_check_pressed(0,gp_padu);
key_dpad_d = gamepad_button_check_pressed(0,gp_padd);
key_dpad_l = gamepad_button_check(0,gp_padl);
key_dpad_r = gamepad_button_check(0,gp_padr);
```

### Face Buttons
```
key_x = gamepad_button_check_pressed(0,gp_face3) // X
key_y= gamepad_button_check_pressed(0,gp_face4) // Y
key_b = gamepad_button_check_pressed(0,gp_face2); // B
key_a = gamepad_button_check_pressed(0,gp_face1); // A
```

### Face Buttons Off
```
key_x_off = gamepad_button_check_released(0,gp_face3) // X
key_y_off = gamepad_button_check_released(0,gp_face4) // Y
key_b_off = gamepad_button_check_released(0,gp_face2); // B
key_a_off = gamepad_button_check_released(0,gp_face1); // A
```

### Shoulder Buttons
```
key_l1 = gamepad_button_check_pressed(0,gp_shoulderl); // L1
key_r1 = gamepad_button_check_pressed(0,gp_shoulderr); // R1
key_l2 = gamepad_button_check_pressed(0,gp_shoulderlb); // L2
key_r2 = gamepad_button_check_pressed(0,gp_shoulderrb); // R2
```

### Shoulder Buttons Off
```
key_l1_off = gamepad_button_check_released(0,gp_shoulderl); // L1
key_r1_off = gamepad_button_check_released(0,gp_shoulderr); // R1
key_l2_off = gamepad_button_check_released(0,gp_shoulderlb); // L2
key_r2_off = gamepad_button_check_released(0,gp_shoulderrb); // R2
```

### Select/Start
// SELECT/START
```
key_select = gamepad_button_check_pressed(0,gp_select)
key_start = gamepad_button_check_pressed(0,gp_start)
```

//and dont even think of mapping the crap X button, Microsoft's invasive branding experience has ruined that button. 
