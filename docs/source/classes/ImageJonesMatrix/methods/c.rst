.. dropdown:: **c** |subTitle| Returns the image of one of the 4 Jones matrix coefficients. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>

    .. code-block:: matlab

        img = obj.c(iy, ix);

        % examples
        Jxx = obj.c(1, 1);
        Jxy = obj.c(1, 2);
        Jyx = obj.c(2, 1);
        Jxx = obj.c(2, 2);

    .. raw:: html
      
        <p class="title">Description</p>

    ``img = obj.c(iy, ix);`` returns the ``(iy, ix)`` coefficient of the Jones Matrix, with :math:`iy, ix\in\{1,2\}`.

    |hr|
    