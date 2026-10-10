.. dropdown:: **imaging** |subTitle| Compute the image of a nanoparticle though a microscope. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>
    
    .. code-block:: matlab

        % general pattern
        IM = obj.imaging(MI);
        IM = objList.imaging(MI);
        IM = objList.imaging(_____, Name, Value);

        % examples
        OB = Objective(100,1.3);
        MI = Microscope(OB);
        IL = Illumination(530e-9);
        NP = Nanoparticle('Au','cuboid',[1000e-9,40e-9,40e-9],'meshParam',10e-9);
        NP = NP.shine(IL);
        IM = NP.imaging(MI,"Npx",100);
        dynamicFigure('ph',IM,'bw',{IM.T})

    .. image:: /images/cuboidImage.png
        :width: 600
        :align: center

    .. raw:: html
      
        <p class="title">Description</p>

    The ``imaging`` method computes and add the image of each dipole of the scene, through the microscope specified by the ``MI`` Microscope object.

