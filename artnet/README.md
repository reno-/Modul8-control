Modul8-control
==============

### Artnet
----------

To be able to move left and down, with positions parameters, I set the MULTIPLICATOR to the Resolution of my canvas, and I use this code in the EventScript of the DMX fixture Modul

    if index + startChannel == dmxChannel :
        if keyword['KEYWORD_NAME'] == 'ctrl_layer_position_x' or keyword['KEYWORD_NAME'] == 'ctrl_layer_position_y':
            value = ((keyword['VAL_MUL'] * (param ['value'] / 255.0)) - (keyword['VAL_MUL'] / 2))
        else:
            value = keyword['VAL_MUL'] * (param ['value'] / 255.0)
        modul8.setValue (keyword['KEYWORD_NAME'], value , keyword['LAYER_POSITION'])