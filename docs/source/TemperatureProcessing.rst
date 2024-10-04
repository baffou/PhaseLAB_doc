.. _Temperature_Processing:

Temperature processing
++++++++++++++++++++++

How can wavefront imaging turn into temperature microscopy?
-----------------------------------------------------------

The wavefront distorsion created by a microscale temperature gradient in the field of view of a microscope can be imaged and processed to retrieve the 3D temperature distribution of the sample. This modality was demonstrated using CGM in 2012, and called TIQSI for Temperature imaging using quadriwave lateral shearing interferometry.\ [#ACSN6_2452]_

Microscale temperature gradients can be created using microscale laser illumination or resistive microwires.\ [#APL102_244103]_ The requirement is only to localize the heat generation at the interface between two media. A significant temperature induced wavefront distorsion is obtained when one media is liquid, which ensures a significant d\ *n*\ /d\ *T* value.

TIQSI enables the retrieval of both the temperature map in 3D, and the heat source density (power per unit area) generated at the interface between the two media.


.. [#ACSN6_2452] *Thermal Imaging of Nanostructures by Quantitative Optical Phase Analysis*, G. Baffou et al., **ACS Nano** 6, 2452 (2012)

.. [#APL102_244103] *Three-dimensional temperature imaging around a gold microwire*, **Applied Physics Letters** 102, 244103 (2013)


Defining the Microscope
-----------------------

One should start building a normal *Microscope* object, as in any |PhaseLAB| code. The only difference might be the specification of a setup in reflection (``MI.refl = false;`` or ``MI.refl = true;``). In the case of a setup in reflection, typically when the substrate is in Silicon or metallic, setting ``MI.refl = true;`` is important because it involves a factor of 2 in the temperature processing algorithm.

.. code-block:: matlab

    %% BUILDING OF THE MEDIUM -- ME = Medium(n,nS);
    ME = Medium('water','glass');

    %% BUILDING OF THE OBJECTIVE -- Objective(Mobj,NA,brand);
    OB = Objective(60,1.3,'Olympus');

    %% BUILDING OF THE MICROSCOPE -- Microscope(OBJ,tl_f,Sid4model,software)
    MI = Microscope(OB,180,'sC8-944','PhaseLIVE');
    MI.refl = false;

    %% BUILDING OF THE ILLUMINATION -- IL = Illumination(lambda);
    lambda = 550e-9;
    IL = Illumination(lambda,ME);

    %% Creation of the temperature medium MediumT(material, thickness [mm], discretization);
    clear Med
    Med(1) = MediumT('BK7',   1e-3, 'progressive');
    Med(2) = MediumT('water', 1e-3, 'progressive');



The :matlab:`Med` object contains all the **thermal** properties of the medium. Make sure it is consistent with the :matlab:`ME` object, which contains the **optical** properties of the system. In a future release, these two objects will be merged. The :matlab:`Med` object can contain 2 or 3 layers. When the solid sample (glass slide or coverslip) is covered with a thick layer of water, one can indicate thicknesses of 1e-3 (the unit is mm), which correspond to infinite media. In case the liquid medium is sandwiched between two glass coverlips for instance, then one has to specify 3 media:


.. code-block:: matlab

    %% Creation of the temperature medium MediumT(material, thickness [mm], discretization);
    clear Med
    Med(1) = MediumT('BK7',  1e-3,'progressive');
    Med(2) = MediumT('water',0.1e-3,'regular');
    Med(3) = MediumT('water',1e-3,'progressive');


Once the media are set, the mesh over the *z* direction can be computed using the command:


.. code-block:: matlab

    Med = mesher(Med,MI);


Finally, after the CGM data are imported and processed using the usual command QLSIprocess, the temperature map can be computed using the :ref:`TMPprocess method <The_TMPprocess_method>` of the class |ImageQLSI|:

.. code-block:: matlab

    IMT = IMs.TMPprocess(Med);

The function accepts several optional parameters. See the :ref:`related documentation <The_TMPprocess_method>` for more information.

Finally, the results can be displayed using the :matlab:`figureT` method.

.. code-block:: matlab

    IMT.figureT();












