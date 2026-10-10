lexique rst

.. DROP DOWN

.. dropdown:: **Temperature processing** |subTitle|  Code to convert a wavefront distorsion image into a temperature map |/subTitle|
    :open:

    Un petit texte de dropdown ouvert

.. dropdown:: **Temperature processing** |subTitle|  Code to convert a wavefront distorsion image into a temperature map |/subTitle|
    :closed:

    Un petit texte de dropdown fermé


.. BLOC DE CODE MATLAB

.. code:: matlab

    %% BUILDING OF THE MEDIUM -- ME = Medium(n,nS);
    ME = Medium('water','glass');

    %% BUILDING OF THE MICROSCOPE -- Microscope(OBJ,tl_f,Sid4model,software)
    OB = Objective(60,1.3,'Olympus');
    MI = Microscope(OB,180,'sC8-944','PhaseLIVE');

.. titre html

.. raw:: html
    
    <p class="title">Bloc de texte html</p>

:py:func:`opendx0`




