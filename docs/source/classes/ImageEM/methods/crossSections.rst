.. dropdown:: **CrossSections** |subTitle| Return the polarisability and cross sections of a NP image. |/subTitle|

    .. raw:: html
      
        <p class="title">Synthax</p>
    
    .. code-block:: matlab

        val = obj.CrossSections()

    .. raw:: html
      
        <p class="title">Description</p>

    This function applies when dealing with the image of a single nanoparticle. It computes the optical properties of a nanoparticle from its image, according to the theory introduced in Ref [#O7_243]_.

    ``obj`` can by a vector of *ImageEM* objects. In this case, the calculation will be performed on all the objects of the list.

    ``val = obj.CrossSections()`` return a *NPprop* object containing the complex optical polarisability of the NP, and the 3 cross-sections.


    .. [#O7_243] *Full optical characterization of single nanoparticles using quantitative phase imaging*, S. Khadir, Daniel Andrén, P. C. Chaumet, S. Monneret, N. Bonod, M. Käll, A. Sentenac, G. Baffou, **Optica** 7, 243-248 (2020)


