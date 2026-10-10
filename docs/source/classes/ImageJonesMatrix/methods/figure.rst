.. dropdown:: **figure** |subTitle| Displays the 4 images of the Jones Matrix coefficients. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>

    .. code-block:: matlab

        obj.figure()
        hfig = obj.figure();
        hfig = obj.figure("func", val);

        % examples
        hfig = obj.figure();
        hfig = obj.figure("func", abs);
        hfig = obj.figure("func", angle);

    .. raw:: html
      
        <p class="title">Description</p>

    ``obj.figure()`` displays the 4 images of the modulus of the Jones Matrix coefficients, as below.

    .. figure:: /images/JonesMatrixDisplay.png
        :width: 400
        :align: center

    |hr|

    ``obj.figure("func", val)`` where ``val`` should correspond to a predefined matlab function, to be applied to all the displayed image. Indeed, the images are complex and can't be displayed. The default value is ``val = abs``, to display the modulus of the coefficients, but other functions can be used, for instance ``angle``.

        
    If the |ImageJonesMatrix| object ``J`` is an array, then one can switch from one image to another by pressing the left and right arrow keys of the keyboard.