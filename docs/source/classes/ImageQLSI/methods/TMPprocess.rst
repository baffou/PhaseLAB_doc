.. dropdown:: **TMPprocess** |subTitle| Computes a temperature image from a wavefront image. |/subTitle|

    .. raw:: html
      
        <p class="title">Synthax</p>

    .. code-block:: matlab

        objT = obj.TMPprocess(Med)
        objT = obj.TMPprocess(Med, Name, Value)
        objListT = objList.TMPprocess(___)
        [objT, GreenFunction, GreenT_z0] = objList.TMPprocess(___)

    .. raw:: html
      
        <p class="title">Description</p>

    ``obj.TMPprocess()`` computes the 2D temperature map associated with a wavefront distorsion. See Ref. \ [#ACSP10_322]_ for more detail.

    

    |hr|

    Objects *vectors* can also be used with this method. The transformation applies then to all the objects of the vector.

    |hr|

    The output ``objT`` is an object from the class |ImageT|.

    |hr|

    This method accepts one input parameter, the variable :matlab:`Med` from the class |MediumT|, defining the thermal properties of the surrounding medium (thermal conductivities and d\ *n*\ /d\ *T* values). It also accepts Name-value arguments, as listed below.

    |hr|

    Optional outputs are the OPD and temperature Green's functions. They can be reused in subsequent calls of the *TMPprocess* function to save computation time.

    .. raw:: html
      
        <p class="title">Name-value arguments</p>
  
    .. note::
    
        Specify optional pairs of arguments as ``Name1 = Value1, ..., NameN = ValueN``, where ``Name`` is the argument name and ``Value`` is the corresponding value. Name-value arguments must appear after other arguments, but the order of the pairs does not matter.
  

    - :matlab:`'g'` and :matlab:`'loop'` (default values: ``1`` and ``1``)

        For large temperature increases, a non-linear algorithm is required to obtain accurate temperature increase maps, as explained in Ref.\ [#APL102_244103]_. In that case, the :matlab:`'g'` and :matlab:`'loop'` parameters must be specified. Typical values are 0.4 and 10:

        .. code-block:: matlab
            
            objT = TMPprocess(Med, 'g', 0.4, 'loop', 10);
        
        Note that :matlab:`g=1; loop=1` corresponds to the linear algorithm.
        
    - :matlab:`'alpha'` (default value: ``1e-5``)

        This is the Tikhonov parameter.Keeping it at 1e-5 is usually fine. Higher values tend to smooth the image, and underestimate the temperature increase. Smaller values tend to increase the noise on the temperature image.

    - :matlab:`'smoothing'` (default value: ``0``, that is no smoothing)

        When the OPD image is very noisy, one may want to smooth it. This can be done using the :matlab:`smooth` method of the |ImageQLSI| class, but also using this Name-Value argument here. If different from zero (the default value), this smoothing option applies the :matlab:`imgaussfilt` function to the OPD image, the value being the parameter of the *imgaussfilt* function. The smaller the parameter and the stronger the smoothing.

    - :matlab:`'imExpander'`  (default value: ``true``)

        This parameter is a boolean. If set to true, it extrapolates the image over a double-size area to avoid artefacts on the boundaries of the reconstructed temperature image. This parameter is true by default, and we recommend to leave it like that, unless the temperature increase is really located at the center of the image.

    - :matlab:`'T0'` 

        Ambient temperature value, set at 22°C by default.

    - :matlab:`'zT'` 

        Height at which the temperature should be computed. 0 by default, i.e. the interface between the two media.

    - :matlab:`'GreenOPD'` 

        Specifies the OPD Green's function, in case it has aleady been computed before, just to save computation time.

    - :matlab:`'GreenT_z0'` 

        Specifies the temperature Green's function, in case it has aleady been computed before, just to save computation time.

    - :matlab:`'GreenT_3D'` 

        Specifies the 3D temperature Green's function, in case it has aleady been computed before, just to save computation time.


    .. [#ACSN6_2452] *Thermal Imaging of Nanostructures by Quantitative Optical Phase Analysis*, G. Baffou et al., **ACS Nano** 6, 2452 (2012)

    .. [#APL102_244103] *Three-dimensional temperature imaging around a gold microwire*, **Applied Physics Letters** 102, 244103 (2013)
