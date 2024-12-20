.. _The_importItfRef_function:

The |c| importItfRef |/c| function
==================================

.. raw:: html
    
    <p class="title">Synthax</p>

.. code-block:: matlab

    % prototype
    Itf = importItfRef(folder, MI, Name, Value)

.. raw:: html
    
    <p class="title">Description</p>

The function ``importItfRef`` automatically imports the interferoimage(s), and the corresponding reference interferogram(s), from a specified folder. To use this function, it is necessary to specify a software input when defining the |Microscope| object. If several images are contained in the data folder, then they are all imported at once, and ``Itf`` becomes an object array.

|hr|

If the number of images is particularly large, like several 100s, then one can import only a link to the saved file, so that the RAM memory does not get saturated. The synthax is the following:

.. code-block:: matlab

    Itf = importItfRef(folder, MI, 'remote', true);

|hr|

Also, one can import a subset of the images with the keywork selection:

.. code-block:: matlab

    Itf = importItfRef(folder, MI, 'remote', true, 'selection', [1 10 20:50]);
    Itf = importItfRef(folder, MI, 'remote', true, 'selection', 1/20);

Line 1 imports the images 1, 10 and all the images from 20 to 50, while line 2 imports 1 image every 20 images (1, 21, 41, etc).

|hr|

If the computer has got an NVidia card, one can use gpuArray variables instead of simple double matrices to accelerate the image processing.

.. code-block:: matlab

    Itf = importItfRef(folder, MI, 'gpu', true);
    Itf = importItfRef(folder, MI, 'remote', true, 'gpu', true);

Line 1 stores the interferogram matrices in the graphics card. Line 2 does not store anything, because it specifies a remote location of the interferograms on the hard drive. However, when the matrices are called using ``Itf.Itf``, they are stored in the graphic card.

When further using :ref:`the QLSIprocess method <The_QLSIprocess_method>`, The ImageQLSI objects will also contrain gpuArrays.


|hr|


Finally, it is common to have several series of images within the same folder. For instance, when using |PhaseLIVE|, one can choose a prefix for the saved images. Here is a list of interferograms, all saved in the same folder, where the prefixes were successively *ITF* and *ITF2*:

| *ITF_0001.tif*
| *ITF_0002.tif*
| *ITF_0003.tif*
| *ITF_0004.tif*
| *ITF2_0001.tif*
| *ITF2_0002.tif*
| *ITF2_0003.tif*
| *REF_20210924_11h_38min_405sec.tif*
| *REF_20210924_11h_52min_168sec.tif*

By default, |PhaseLAB| will import them all, without difficulty, but one may want to specifically import the *ITF2*-tagged interferograms for instance. In this case, here is the command:

.. code-block:: matlab

    Itf = importItfRef(folder, MI, 'nickname', 'ITF2');

