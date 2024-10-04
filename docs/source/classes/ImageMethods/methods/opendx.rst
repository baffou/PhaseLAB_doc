.. dropdown:: **opendx** |subTitle| Display a 3D rendering of the image |/subTitle|

    .. raw:: html
      
        <p class="title">Synthax</p>
    
    .. code-block:: matlab

        % prototypes
        opendx(obj)
        opendx(obj, Name, Value)

        % examples
        opendx(IM)
        objList.makeMoviedx(IM, 'theta', 10, 'phi', 30, 'zrange', [-10 120]*1e-9, 'ampl', 4)

    .. raw:: html
      
        <p class="title">Description</p>

    The ``opendx`` method diplays images from |ImageEM| or |ImageQLSI| objects with a nice 3D rendering.

    |hr|

    Many Name-value options can be specified to change the rendering.

    - :matlab:`'persp'`  (default: ``1``)

        With ``'persp'`` set to ``1``, the video uses the ``opendx`` method to create a nnince 3D rendering of the image. Set this option to ``0`` to cancel this effect.
    
    - :matlab:`'phi'`  (default: ``45``) and :matlab:`'theta'`  (default: ``45``)

        Position of the camera in :math:`(\theta, \phi)`

    - :matlab:`'ampl'`  (default: ``3``)

        sets the magnitude of the 3D relief

    - :matlab:`'zrange'`

        2-vector setting the limits of the *z* axis.

    - :matlab:`'colorMap'` (default: :matlab:`parula`)

        Color map.

    - :matlab:`'title'`

        Title to display on the movie, if any.

    - :matlab:`'factor'` (default: ``1``)

        Correction factor to the |OPD|, for instance 5.55e-3 to convert the |OPD| into |DM|.

    - :matlab:`'label'` (default: :matlab:`'Optical path difference (nm)'`)

        Label to put on the color scale.

    - :matlab:`'imType'` (default: :matlab:`'OPD'`)

        Cell array of the properties of the object to be displayed: ``'OPD'``, ``'T'``, ``'DWx'``, ``'DWy'``, ``'Ph'``.

    - :matlab:`'axisDisplay'` (default: :matlab:`true`)

        Display the axes or not.

