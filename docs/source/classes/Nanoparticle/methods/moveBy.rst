.. dropdown:: **moveBy** |subTitle| Moves the nanoparticle by a given vector. |/subTitle|
    
    .. raw:: html
      
        <p class="title">Syntax</p>
    
    .. code-block:: matlab

        % general pattern
        obj = obj.moveBy([x, y, z]);
        obj = obj.moveBy(x, y, z)
        obj = obj.moveBy(Name, Value);

        % examples
        obj = obj.moveBy([0.1, 0.3, 0]*1e-6);  % moves the nanoparticle by 0.1 and 0.3 µm in the x and y directions
        obj = obj.moveBy(0.1e-6, 0.3e-6, 0);  % moves the nanoparticle by 0.1 and 0.3 µm in the x and y directions
        obj = obj.moveBy('x', 1e-6);  % moves the nanoparticle by 1 µm in the x direction
        obj = obj.moveBy('x', 1e-6, 'y', 1e-6);  % moves the nanoparticle by 1 µm in both x and y directions
        obj = obj.moveBy('z' = -1e-6, 'y', 0.5-6, 'x', 3e-6);  % moves the nanoparticle in the three directions by specific distances

    .. raw:: html
      
        <p class="title">Description</p>

    Move the nanoparticle by specific amounts along the :math:`x`, :math:`y`, and :math:`z` directions. The motion is relative to the original position. To move the nanoparticle to absolute positions, rather use the *moveTo* method.

    The arguments can be either the 3 shifts in :math:`x`, :math:`y`, and :math:`z` directions; or a 3-vector of these positions; or a Name-Value structure where the Names are ``'x'``, ``'y'``, and/or ``'z'``, in any order.
