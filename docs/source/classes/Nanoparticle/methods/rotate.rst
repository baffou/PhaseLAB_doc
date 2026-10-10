.. dropdown:: **rotate** |subTitle| Rotates the nanoparticle. |/subTitle|
    
    .. raw:: html
      
        <p class="title">Syntax</p>
    
    .. code-block:: matlab

        obj = obj.rotate(theta_deg);
        obj = obj.rotate(______, Name, Value);

        % examples
        obj = obj.rotate(90);
        obj = obj.rotate(45, "axis", 'y');
        obj = obj.rotate(30, "axis", 'y');
        obj = obj.rotate(90, "center", [0,0,0]);


    .. raw:: html
      
        <p class="title">Description</p>

    The ``rotate`` method rotates the nanoparticle by a given angle around a specified axis, which is by default :math:`(z)`, and by default around its barycenter. The axis and barycenter can be specified using Name, Values inputs.
    
    .. code:: matlab

        % creation of a ring of nanoparticles
        NP = Nanoparticle(2);
        NP(1) = Nanoparticle('Au', 'rod', [100e-9, 20e-9], "meshParam", 4e-9);
        NP(2) = NP(1).rotate(45);
        NP.figure()

    .. image:: /images/NProtate.png
        :width: 600
        :align: center