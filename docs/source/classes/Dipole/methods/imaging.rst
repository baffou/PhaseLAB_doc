.. dropdown:: **imaging** |subTitle| Compute the imaging of dipoles though a microscope. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>
    
    .. code-block:: matlab

        % general pattern
        IM = obj.imaging(MI);
        IM = objList.imaging(MI);
        IM = objList.imaging(_____, Name, Value);

        % examples
        MI = Microscope(100);
        IL = Illumination(530e-9);
        DI = Dipole('Au',25e-9);
        DI = DI.shine(IL);
        IM = DI.imaging(MI,"Npx",100);
        dynamicFigure('ph',IM,'bw',{IM.T})

    .. image:: /images/DIimage.png
        :width: 600
        :align: center

    .. raw:: html
      
        <p class="title">Description</p>

    The ``imaging`` method computes and add the image of each dipole of the scene, through the microscope specified by the ``MI`` Microscope object.

