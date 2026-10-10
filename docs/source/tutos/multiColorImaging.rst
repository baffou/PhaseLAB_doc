Multicolor imaging
==================

In 2024, we combined a 2-color camera with a QLSI grating [#colorCGM]_. In these implementations, 2 interferograms are extracted from the raw camera image.

.. [#colorCGM] *Single-shot quantitative phase-fluorescence imaging using cross-grating wavefront microscopy*, B. Marthy, M. Benefice, G. Baffou, **Sci. Rep.**, 14, 2142 (2024)  

The two interferograms can be extracted using the :ref:`splitColors <The_splitColors_method>` method:

.. code-block:: matlab

    Itf0 = importItfRef(folder,MI);
    Itf = Itf0.splitColors();

If the input :matlab:`Itf0` is a list (an array) or :math:`N` |Interfero| objects, then the output :matlab:`Itf` is a :math:`N\times2` array of |Interfero| objects, where each column is one color.

Some color cameras suffer from crosstalk between neighboring dexels of different colors. To correct for this crosstalk, use the |Interfero| method :ref:`crosstalkCorrection <The_crosstalkCorrection_method>`:

.. code-block:: matlab

    Itf0 = importItfRef(folder,MI);
    Itf = Itf0.splitColors();


Then, :matlab:`Itf` can be processed like a normal |Interfero| object array using the :ref:`QLSIprocess <The_QLSIprocess_method>` method:

.. code-block:: matlab

    IM = QLSIprocess(Itf, IL);

and just like :matlab:`Itf`, :matlab:`IM` is a :math:`N\times2` |ImageQLSI| object array.

