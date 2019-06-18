# Check box (lv_cb)
## Overview

The Check Box objects are built from a Button **background** which contains an also Button **bullet** and a **label** to realize a classical check box. 
The **text** can be modified by the `lv_cb_set_text(cb, "New text")` function. It will dynamically alloacte the text. 
To set a static text use `lv_cb_set_static_text(cb, txt_buf)`. This way only a pointer will be stored to `txt_buf` so it needs shouldn't deallocated while the checkbox exists. 

You can manually **check / un-check** the Check box  via `lv_cb_set_checked(cb, true/false)`.

To make the chackbox inactive use `lv_cb_set_inactive(cb, true)`.


## Styles

The Check box styles can be modified with `lv_cb_set_style(cb, LV_CB_STYLE_..., &style)`.

- **LV_CB_STYLE_BG** Background style. Uses all `style.body` properties. The label's style comes from  `style.text`. Default: `lv_style_transp`
- **LV_CB_STYLE_BOX_REL** Style of the released box. Uses the `style.body` properties. Default: `lv_style_btn_rel`
- **LV_CB_STYLE_BOX_PR** Style of the pressed box. Uses the `style.body` properties. Default: `lv_style_btn_pr`
- **LV_CB_STYLE_BOX_TGL_REL** Style of the checked released box. Uses the `style.body` properties. Default: `lv_style_btn_tgl_rel`
- **LV_CB_STYLE_BOX_TGL_PR** Style of the checked released box. Uses the `style.body` properties. Default: `lv_style_btn_tgl_pr`
- **LV_CB_STYLE_BOX_INA** Style of the inactive box. Uses the `style.body` properties. Default: `lv_style_btn_ina`


## Events
Besided the [Genreric events](/overview/events.html#generic-events) the following [Special events](/overview/events.html#special-events) are sent by the Check boxes:
 - **LV_EVENT_VALUE_CHANGED** sent when the Check box is toggled.

Note that the generic input device related events (like `LV_EVENT_PRESSED`) are sent in inactive state too. You need to check the state with `lv_cb_is_inactive(cb)` to ignore the events from inactive Chek boxes.
 
Learn more about [Events](/overview/events).


## Keys
The following *Keys* are processed by the Buttons:
- **LV_KEY_RIGHT/UP** Go to toggled state if toggling is enabled
- **LV_KEY_LEFT/DOWN** Go to non-toggled state if toggling is  enabled

Note that, as usual, the state of `LV_KEY_ENTER` is translated to `LV_EVENT_PRESSED/PRESSING/RELEASED` etc.

Learn more about [Keys](/overview/indev).


## Example

### C

![Checkbox image](http://docs.littlevgl.com/img/check-box-lv_cb.png)

```eval_rst
.. container:: toggle

    .. container:: header
    
      code

    .. literalinclude:: /examples/cb/cb_1.c
      :language: c
 
```

### MicroPython
No examples yet.

## API 

```eval_rst

.. doxygenfile:: lv_cb.h
  :project: lvgl
        
```