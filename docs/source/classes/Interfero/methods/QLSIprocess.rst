.. dropdown:: QLSIprocess |subTitle| Processes and returnes the intensity and wavefront images, as an |ImageQLSI| object. |/subTitle|
    
    .. raw:: html
      
        <p class="title">Syntax</p>
    
    .. code-block:: matlab

        % prototypes
        Im = QLSIprocess(Itf, IL);
        ImList = QLSIprocess(ItfList, IL);
        ImList = QLSIprocess(___, Name, Value);

        % examples
        Im = QLSIprocess(Itf, IL,...
                "apodization", [], ... % true, 1, or the width of the apodization in px
                "auto", true, ...   % Find automatically the spot of highest intensity
                "CGdistanceList", [], ...
                "crop", = [], ... % 'Manual', or [x1;y1;x2;y2] . Ask for, or apply, a crop before processing
                "darkImage", 0, ... % dark Image to be removed
                "darkZoneCorrection", false, ... % algorithm for dark zones correction
                "defintion"; 'high', ...  % 'high' or 'low'}
                "displayBar", true, ... % Display the progression bar in case of multiple images
                "displayCrop",  false, ...  % Display the crops, even when automatic
                "Fcrops", [], ... % use predefined crops in the Fourier space, instead of computing them
                "Fcropshape", 'disc', ...  %'disc' or 'square'
                "method", 'Tikhonov', ...  % 'Tikhonov', 'Errico', 'ASDI' or 'CPM'
                "noRef", false, ... % Do not consider the Ref interferogram to compute the DW and OPD images
                "RemoveCameraOffset", false, ...
                "remotePath", [], ...
                "resetCrops",  false, ...
                "Rdistance", ... = 1 % Multiply the distance of the crop from the center
                                     %of the image by Rdistance. Useful to crop the spots at 45°,
                                     % by just setting R=sqrt(2)
                "Rfactor", 1, ... % Multiply the crop radius by Rfactor
                "saveGradients", false, ...
                "Tnormalisation", true, ... % or false or 'subtraction'
                "unwrap", false);
        

    .. raw:: html

        <p class="title">Description</p>

    This method represents the central function of the PhaseLAB toolbox. The **QLSIprocess** method of the class |Interfero| processes the interferograms, and returns the intensity and wavefront images as a |ImageQLSI| object. As a second input, an **Illumination** object must be specified.

    |hr|

    The method also works with an |Interfero| array, and returns an |ImageQLSI| array: :matlab:`ImList = QLSIprocess(ItfList, IL);`

    .. raw:: html
      
        <p class="title">Name-value inputs</p>



    | **Name**: :matlab:`"apodization"`
    | |gr| **Value**: |c| false |/c|  (default) \| |c| true |/c| \| |c| 20 |/c| |/gr|

    Performs an apodization on the interferogram images to avoid possible artefacts after Fourier transforms. By default, when the value is ``1`` or ``true``, the apodization is 20 px wide. For another width, the value should equal the width in pixels. Here are some examples:

    .. code-block:: matlab

        Im = QLSIprocess(Itf, IL, "apodization", false); % no apodization
        Im = QLSIprocess(Itf, IL, "apodization", true);  % apodization of 20 px
        Im = QLSIprocess(Itf, IL, "apodization", 40);    % apodization of 40 px

    |hr|

    | **Name**: :matlab:`"auto"`
    | |gr| **Value**: |c| true |/c|  (default) \| |c| false |/c| |/gr|

    If true, finds automatically the 0 and 1st order spots in the Fourier space. If false, a window opens to ask the user to click on the spots. This manual mode is honestly never useful. The auto mode always works perfectly. See the :ref:`Process experimental images <process_experimental_images>` section for more details.

    |hr|

    | **Name**: :matlab:`"CGdistanceList"`
    | |gr| **Value**: |c| [ ] |/c|  (default) \| |c| *double* array |/c| |/gr|

    If the input is an *Interfero* array, and if the images have been acquired with various values of grating-camera distances :math:`d`, the list of :math:`d` values can be indicated as a *double* array here. The array must have as many values as the number of *Interfero* objects.

    |hr|

    | **Name**: :matlab:`"crop"`
    | |gr| **Value**: |c| [ ] |/c|  (default) \| |c| 'Manual' |/c| \| |c| (4,1) *double* array |/c| |/gr|

    If :matlab:`crop = 'Manual'`, asks the user to manually crop an area on the interferogram. Only this area will be processed to create waverfront and intensity images of this size. The same crop will be assigned to all subsequent interferograms, if the object is an **Interfero** array.
    If :matlab:`crop = [x1;x2;y1;y2]`, the coordinates of the crop are not defined by a drawing, but by these values :math:`x_1, x_2, y_1, y_2`.

    Examples:

    .. code-block:: matlab

        IM = QLSIprocess(Itf, IL, "crop", 'Manual');
        IM = QLSIprocess(Itf, IL, "crop", [230; 210; 2100; 1680]);

    |hr|

    | **Name**: :matlab:`"darkImage"`
    | |gr| **Value**: |c| 0 |/c|  (default) \| |c| *Interfero* object |/c| |/gr|

    Subtracts a dark image (acquired with the incident light off) to the interferogram. This procedure does not modify the wavefront image ``OPD``, in principle. It is rather aimed to obtain quantitative intensity images ``T``.

    Examples:

    .. code-block:: matlab
        
        % The dark image can be an interferogram:
        Itf = importItfRef('data',MI,'nickname','ITF'); % single or array of Interferograms
        Drk = importItfRef('data',MI,'nickname','DRK'); % single or array (if so, as many) of Interferograms
        IM = QLSIprocess(Itf, IL, "darkImage", Drk);

        % or a regular image:
        Drk = imread('data/darkImage.tif');
        IM = QLSIprocess(Itf, IL, "darkImage", Drk);

    |hr|

    | **Name**: :matlab:`"darkZoneCorrection"`
    | |gr| **Value**: false (Default) \| true |/gr|

    Sharp, dark zones on the interferogram can lead to artefactual wavefront measurements. Bing Xu et al. proposed a correction algorithm in Optics Communications 402 (2017) 276–284. This algorith is used if :matlab:`darkZoneCorrection = true`.

    |hr|

    | **Name**: :matlab:`"defintion"`
    | |gr| **Value**: |c| 'high' |/c|  (default) \| |c| 'low' |/c| |/gr|

    Tells whether the process gives high definition or low definition images.

    | **High definition**: the intensity and wavefront images have the same number of pixels as the interferogram.
    | **Low definition**: the width and height of the intensity and wavefront images are reduced by a factor :math:`\zeta` (zeta), that is the size of the grating unit cell, in camera dexels (usually, :math:`\zeta=3`).

    There is neither more information nor more spatial resolution in the high-definition images. However, the images look much better in this mode. Here is an example of high versus low definition images:

    .. figure:: /images/lowvshighdefinitions.png
        :align: center

        High- versus low-definition wavefront images of a nanoparticle, from the same interferogram.

    |hr|

    | **Name**: :matlab:`"displayBar"`
    | |gr| **Value**: |c| true |/c|  (default) \| |c| false |/c| |/gr|

    Display or not the progression bar when processing multiple interferograms.

    |hr|

    | **Name**: :matlab:`"displayCrop"`
    | |gr| **Value**: |c| true |/c|  (default) \| |c| false |/c| |/gr|

    Display or not the crop in the Fourier space when processing the interferogram. Can make the processing faster if multiple interferograms are processed in a loop, instead of using :matlab:`ItfList.QLSIprocess(...)`. In the latter case, the crop is only displayed once, at the first image.

    |hr|

    | **Name**: :matlab:`"Fcrops"`
    | |gr| **Value**: 3-cell of *FcropParameters* objects. |/gr|

    Enables the use of predefined crops in the Fourier space, meaning that the automatic detection of the diffraction orders is cancelled. Predefined crops normally originate from a previous *QLSIprocess* use. When processing an *Interfero* object using *QLSIprocess*, the crops are saved as a property of the returned |ImageQLSI| object. Here is an example:

    .. code-block:: matlab

        IM1 = QLSIprocess(Itf1, IL);
        IM2 = QLSIprocess(Itf2, IL, "Fcrops", IM1.Fcrops);

    |hr|

    | **Name**: :matlab:`"Fcropshape"`
    | |gr| **Value**: |c| 'disc' |/c|  (default) \| |c| 'square' |/c| |/gr|

    Tells whether the crops in the Fourier space are circular (by default) or square. Does not change much the processed images.

    |hr|

    | **Name**: :matlab:`"method"`
    | |gr| **Value**: |c| 'Tikhonov' |/c|  (default) \| |c| 'Errico' |/c| \| |c| 'CPM' |/c| \| |c| 'ASDI' |/c| |/gr|

    Selects the integration method used to get the wavefront image from the two gradients.

    The Tikhonov method uses the `grad2surf <https://www.mathworks.com/matlabcentral/fileexchange/43149-surface-reconstruction-from-gradient-fields-grad2surf-version-1-0>`_ toolbox developed by  Matthew Harker and Paul O'Leary. It is fast and does not create artefacts on the borders of the images.

    The Errico method uses the `intgrad2 <https://www.mathworks.com/matlabcentral/fileexchange/9734-inverse-integrated-gradient>`_ toolbox developed by John D'Errico. It is slower than Tikhonov.

    The CPM method uses the standard integration algorithm based on Fourier tranforms:

    .. math::
        
        W = \mathcal{F}^{-1}\left[\displaystyle\frac{ \mathcal{F}(\partial_xW + i\partial_yW)}{2i\pi(k_x/N_x + ik_y/N_y)}\right]

    It is fast, but occasionally creates rebounds on the boundaries of the wavefront images.

    The CPM method artificially enlarges the size of the wavefront gradient images with mirror images in order to remove occasional boundary artefacts. Then, it uses the CPM method to reconstruct the wavefront. The procedure is introduced by Bon et al. in Applied Optics 51 (23), 5698-5704.

    |hr|

    | **Name**: :matlab:`"noRef"`
    | |gr| **Value**: |c| false |/c|  (default) \| |c| true |/c|

    If true, does not use the reference interferogram in the processing of the intensity and wavefront images.

    |hr|

    | **Name**: :matlab:`"RemoveCameraOffset"`
    | |gr| **Value**: |c| false |/c|  (default) \| |c| true |/c|

    Removes the offset on the interferogram images, set by the camera constructor. Useless for the reconstruction of the wavefront image. Relevant when quantitative intensity images are seeked. The offset value to substract is indicated in the specification file of the camera included when building the |Microscope| object.


    |hr|
   
    | **Name**: :matlab:`"remotePath"`
    | |gr| **Value**: |c| [ ] |/c|  (default) \| *char* \| *string*

    If not empty, the intensity and wavefront images are not saved in the RAM of the comptuer, but on the hard disk. The value of |c| remotePath |/c| specifies the folder where the images should be saved. It is useful when working with a large set of images, likely to saturate the RAM.

    |hr|

    | **Name**: :matlab:`"resetCrops"`
    | |gr| **Value**: |c| false |/c|  (default) \| |c| true |/c|

    Resets the crops between each processed interferogram, to make sure the algorithm enables the user to click on each image when ``"auto = false"``.

    |hr|

    | **Name**: :matlab:`"Rdistance"`
    | |gr| **Value**: |c| 1 |/c|  (default) \| |c| (1,1) *double* |/c|

    Multiplies the distance of the crop from the center of the Fourier image by the specified value. Useful to crop the spots at 45°, by just setting :matlab:`R=sqrt(2)`.

    |hr|

    | **Name**: :matlab:`"Rfactor"`
    | |gr| **Value**: |c| [] |/c|  (default) \| |c| (1,1) *double* |/c|

    Multiplies the size of the crop in the Fourier image by the specified value. If empty, it equals :matlab:`opt.Rdistance`.

    |hr|

    | **Name**: :matlab:`"saveGradients"`
    | |gr| **Value**: |c| false |/c|  (default) \| |c| true |/c|

    Save the gradients in the properties ``DWx`` and ``DWy`` of the returned |ImageQLSI| object.

    .. code-block:: matlab

        Im = QLSIprocess(Itf, IL, "saveGradients", true);
        dynamicFigure('ph', Im.DWx, 'ph', Im.DWy)

    If the gradients are not saved during the image processing, then the properties ``DWx`` and ``DWx`` of the |ImageQLSI| object can still be accessed. However, the gradients are computed from differentiation of the wavefront image, which can be time consuming and slightly different from the original wavefront gradients. If the gradient images are supposed to be used later, a true-value of this option is recommended.

    |hr|


    | **Name**: :matlab:`"Tnormalisation"`
    | |gr| **Value**: |c| true |/c|  (default) \| |c| false |/c| \| |c| 'subtraction' |/c|

    Sets the way the intensity image is normalized. By default, it is divided by the intensity image of the reference image. To avoid that, one can set the value to ``false``. One can also choose to normalize by *subtracting* the intensity image of the reference, using the value ``'subtraction'`` (relevant when working with fluorescence images for instance).

    |hr|

 
    | **Name**: :matlab:`"unwrap"`
    | |gr| **Value**: |c| false |/c|  (default) \| |c| true |/c|

    Uses an unwrapping algorithm. Not useful in most cases. Slows down a bit the image processing. The algorithm is based on this `Matlab package <https://www.mathworks.com/matlabcentral/fileexchange/68493-robust-2d-phase-unwrapping-algorithm>`_ from Zixin Zhao.










