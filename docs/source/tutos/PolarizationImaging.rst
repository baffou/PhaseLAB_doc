Polarization imaging
====================

In 2024, we combined a 4-polarization camera with a QLSI grating to achieve polarization resolved wavefront imaging [#polarCGM]_.

.. [#polarCGM] *Single-shot polarization imaging of vectorial metasurfaces using cross-grating wavefront microscopy*, J. Flamant, B. Marthy, K. Zangeneh Kamali, N. Ullberg, G. Demesy, P. Ferrand, M. Käll, G. Baffou, **ACS Nano**, accepted  (2026)  


In this implementation, 4 interferograms are extracted from the raw camera image. For this purpose, the :ref:`splitPolars <The_splitPolars_method>` method is used:

.. code-block:: matlab

    Itf0 = importItfRef(folder,MI);
    Itf = Itf0.splitPolars();

If the input :matlab:`Itf0` is a list (an array) or :math:`N` |Interfero| objects, then the output :matlab:`Itf` is a :math:`N\times4` array of |Interfero| objects, where each column is one polarisation.

Then, :matlab:`Itf` can be processed like a normal |Interfero| object using the :ref:`QLSIprocess <The_QLSIprocess_method>` method:

.. code-block:: matlab

    IM = QLSIprocess(Itf, IL);

and just like :matlab:`Itf`, :matlab:`IM` is a :math:`N\times4` |ImageQLSI| objects.


Polarized light field imaging
+++++++++++++++++++++++++++++

Then, an object organizing the polarization can be created using the :ref:`ImageQLSIpolar <The_ImageQLSIpolar_Class>` constructor:

.. code-block:: matlab

    pIM = ImageQLSIpolar(IM);

or equivalently the **ImageQLSI** method:

.. code-block:: matlab

    pIM = ImageQLSIpolar(IM);

The output ``pIM`` is an |ImageQLSIpolar| object. It proposes many methods to deal with a display polarized field.

An |ImageQLSIpolar| can be displayed using the :ref:`figure <The_figureJ_method>` method:

.. code-block:: matlab

    pIM.figure;

:figure:

.. figure:: /images/pImFigure.png
   :width: 1000
   :align: center




Material imaging
++++++++++++++++

In microscopy, the polarized field usually comes from the fact the the object image is anisotropic, and exhibits birefringence and dichroism properties. It is what we want to study in general. For this purpose, one acquisition is not sufficient. At least two interferograms are required. If these two interferograms correspond to left-handed circular polarization (LCP) and right-handed circular polarization (RCP), then, the two correspond **ImageQLSIpolar** images can be combined using the :ref:`im2J <The_im2J_method>` method to form an |ImageJonesMatrix| object:

.. code-block:: matlab

    J = im2J(pIML,pIMR);
    

An |ImageJonesMatrix| can be displayed using the *figure* method:

.. code-block:: matlab

    J.figure()
    

.. figure:: /images/JonesMatrixDisplay.png
   :width: 600
   :align: center

This figure is not a simple figure. If ``J`` is an array of |ImageJonesMatrix| objects, then one can display the successive Jones matrices by pressing the left and right arrow keys.