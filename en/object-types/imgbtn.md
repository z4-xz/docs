# Image button (lv_imgbtn)

## Overview

The Image button is very similar to the simple Button object. The only difference is it displays user-defined images in each state instead of drawing a button. 
Before reading this please read the [Button](/object-types/btn) section too.

To set the image in a state the `lv_imgbtn_set_src(imgbtn, LV_BTN_STATE_..., &img_src)` The image sources works the same as described in the [Image object](/object-types/img).

If `LV_IMGBTN_TILED` is enabled in *lv_conf.h* three source can be set for state:
- left
- ceter
- right

The *center* image will repeated to fill the width of object. Therefore with `LV_IMGBTN_TILED` you can set the width of the Image button while without it the width will be always the same as the image source's width.


The **states** also work like with Button object. It can be set with `lv_imgbtn_set_state(imgbtn, LV_BTN_STATE_...)`. 

The **toggle** feature can be enabled with `lv_imgbtn_set_toggle(imgbtn, true)`

## Style usage

Similarly to normal Buttons, Image buttons also have 5 independent styles for the 5 state. You can set them via: `lv_imgbtn_set_style(btn, LV_IMGBTN_STYLE_..., &style)`. The styles use the `style.image` properties.

- **LV_IMGBTN_STYLE_REL** style of the released state. Default: `lv_style_btn_rel`
- **LV_IMGBTN_STYLE_PR** style of the pressed state. Default: `lv_style_btn_pr`
- **LV_IMGBTN_STYLE_TGL_REL** style of the toggled released state. Default: `lv_style_btn_tgl_rel`
- **LV_IMGBTN_STYLE_TGL_PR** style of the toggled pressed state. Default: `lv_style_btn_tgl_pr`
- **LV_IMGBTN_STYLE_INA** style of the inactive state. Default: `lv_style_btn_ina`

When labels are created on a button, it's a good practive to set the image button's `style.text` properties too. Because labels have `style = NULL` by default they inherit the parent's (image button) style. 
Hence you don't need to craete a new style for the label. 

## Events
Besided the [Genreric events](/overview/events.html#generic-events) the following [Special events](/overview/events.html#special-events) are sent by the buttons:
 - **LV_EVENT_VALUE_CHANGED** sent when the button is toggled.

Note that the generic input device related events (like `LV_EVENT_PRESSED`) are sent in inactive state too. You need to check the state with `lv_btn_get_state(btn)` to ignore the events from inactive buttons.
 
Learn more about [Events](/overview/events).

## Keys
The following *Keys* are processed by the Buttons:
- **LV_KEY_RIGHT/UP** Go to toggled state if toggling is enabled
- **LV_KEY_LEFT/DOWN** Go to non-toggled state if toggling is  enabled

Note that, as usual, the state of `LV_KEY_ENTER` is translated to `LV_EVENT_PRESSED/PRESSING/RELEASED` etc.

Learn more about [Keys](/overview/indev).
  

## Example

### C

![Image button image](http://docs.littlevgl.com/img/image-button-lv_imgbtn.png)


```eval_rst
.. container:: toggle

    .. container:: header
    
      code

    .. literalinclude:: /examples/imgbtn/imgbtn_1.c
      :language: c
 
```

### MicroPython
No examples yet.

## API 

```eval_rst

.. doxygenfile:: lv_imgbtn.h
  :project: lvgl
        
```