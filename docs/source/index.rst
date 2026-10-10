.. PhaseLAB documentation master file, created by
   sphinx-quickstart on Sun Dec 10 05:51:47 2023.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

.. meta::
    :description: The PhaseLAB Matlab toolbox documentation
    :keywords: QLSI, Matlab, toolbox

|PhaseLAB| documentation
########################

|PhaseLAB|  is a Matlab toolbox aimed at dealing with quantitative phase images. It has been developed by Guillaume Baffou, CNRS research scientist at the Fresnel Institute (Marseille, France).

PhaseLAB is licensed under the Creative Commons Attribution-NonCommercial (CC BY-NC) license. This means you are free to use, share, and modify the software, but only for non-commercial purposes.

By using this software, you agree to abide by the terms of the CC BY-NC license. If you have any questions about the license or its terms, please refer to the accompanying license file or contact us for clarification.

The toolbox is accessible at `github.com/baffou/PhaseLAB <https://github.com/baffou/PhaseLAB>`_.



.. grid:: 1

    .. grid-item-card:: Download from GitHub

        .. button-link:: https://github.com/baffou/PhaseLAB

            github.com/baffou/PhaseLAB

.. ==================

.. * :ref:`genindex`
.. * :ref:`search`

.. # = - * " ^ 

**Table of Content**:

.. toctree::
    :maxdepth: 2

    download
    intro

.. toctree::
    :maxdepth: 2
    :caption: Tutorials

    buildMicroscope     <tutos/buildMicroscope>
    importImages        <tutos/importImages>
    processImages       <tutos/processImages>
    displayImages       <tutos/displayImages>
    BackgroundFlattering    <tutos/BackgroundFlattering>
    inSilico            <tutos/inSilico>
    multiColorImaging   <tutos/multiColorImaging>
    TemperatureProcessing   <tutos/TemperatureProcessing>
    PolarizationImaging <tutos/PolarizationImaging>
    GUI                 <tutos/GUI>

.. toctree::
    :maxdepth: 2
    :caption: Code examples

    codeExamples

.. toctree::
    :maxdepth: 3
    :caption: Classes

    Camera     <classes/Camera>
    CameraLive     <classes/CameraLive>
    CGcamera     <classes/CGcamera>
    CrossGrating     <classes/CrossGrating>
    Dipole     <classes/Dipole>
    Illumination <classes/Illumination>
    ImageEM    <classes/ImageEM>
    ImageQLSI    <classes/ImageQLSI>
    ImageQLSIpolar    <classes/ImageQLSIpolar>
    ImageJonesMatrix    <classes/ImageJonesMatrix>
    ImageT    <classes/ImageT>
    ImageTransmittance    <classes/ImageTransmittance>
    Interfero    <classes/Interfero>
    Medium   <classes/Medium>
    MediumT   <classes/MediumT>
    Monochromator   <classes/Monochromator>
    Microscope   <classes/Microscope>
    Nanoparticle   <classes/Nanoparticle>
    Objective   <classes/Objective>
    RelayLens   <classes/RelayLens>

.. toctree::
    :maxdepth: 2
    :caption: Functions

    CGMinSilico    <functions/CGMinSilico>
    imaging        <functions/imaging>
    importItfRef   <functions/importItfRef>
    dynamicFigure  <functions/dynamicFigure>
    dynamicMovie  <functions/dynamicMovie>
    MieScattering  <functions/MieScattering>
    opendx0  <functions/opendx0>



..   :maxdepth: 2
..   :caption: Functions
..   :glob:
..
..   functions/*

