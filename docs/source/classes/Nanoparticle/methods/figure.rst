.. dropdown:: **figure** |subTitle| Display the nanoparticle in 3D. |/subTitle|
    
    .. raw:: html
      
        <p class="title">Syntax</p>
    
    .. code-block:: matlab

        obj.figure()

    .. raw:: html
      
        <p class="title">Description</p>

    Displays the morphology of the nanoparticle and its mesh in 3D. For instance:
    
    .. code:: matlab

        % creation of the nanoparticle
        radius = 25e-9;
        NP = Nanoparticle('Au', 'sphere', radius,'meshParam',4e-9);
        NP.figure()


    .. image:: /images/Nanoparticle.png
        :width: 600
        :align: center