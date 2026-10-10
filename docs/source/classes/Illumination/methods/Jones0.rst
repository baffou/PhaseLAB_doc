.. dropdown:: **Jones0** |subTitle| Applies a Jones matrix to an *Illumination* object. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>
    
    .. code-block:: matlab

        % prototype
        IL.Jones0(mat)

        % example
        IL.Jones0([1i, 1; 1, 0]])

    .. raw:: html
      
        <p class="title">Description</p>

    Applies the effect of an optical plate to the illumination beam, according to the Jones matrix formulation. The names can be:
    For instance, here is a circularly polarized light that passes through a linear polarizer oriented along :math:`x`:

    .. code-block:: matlab

        >> IL = Illumination(532e-9);
        >> IL.polar = [1 1i 0];
        >> IL.Jones0([1, 0; 0, 0])
        >> disp(IL.polar)

        0.7071 + 0.7071i   0.0000 + 0.0000i   0.0000 + 0.0000i
