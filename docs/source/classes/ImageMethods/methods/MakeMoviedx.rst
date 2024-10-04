.. dropdown:: **MakeMoviedx** |subTitle| Make a movie from a series of image objects |/subTitle|


    .. raw:: html
      
        <p class="title">Synthax</p>
    
    .. code-block:: matlab

        % prototypes
        objList.makeMoviedx(videoName)
        objList.makeMoviedx(videoName, Name, Value)

        % examples
        objList.makeMoviedx('movie/bacteria.avi')
        objList.makeMoviedx('movie/bacteria.avi', )
        objList.makeMoviedx('movie/bacteria.avi','theta',0,'phi',0,'rate',2,'zrange',[-10 10])


    .. raw:: html
      
        <p class="title">Description</p>

    The ``MakeMoviedx`` method creates an .avi movie from an |ImageEM| or |ImageQLSI| object array. Two inputs are required, the image object array ``IM`` and the path/name of the movie file to be created ``videoname``. It calls the method :ref:`opendx <The_opendx_method>`, from the same class.

    |hr|

    Many Name-value options can be specified to change the rendering.

    - :matlab:`'persp'`  (default: ``1``)

        With :matlab:`'persp'` set to ``1``, the video uses the ``opendx`` method to create a nice 3D rendering of the image. Set this option to ``0`` to cancel this effect.
    
    - :matlab:`'phi'`  (default: ``45``) and :matlab:`'theta'`  (default: ``45``)

        Position of the camera in :matlab:`(\theta, \phi)`. :matlab:`(0,0)` corresponds to the top view.

    - :matlab:`'ampl'`  (default: ``3``)

        sets the magnitude of the 3D visual topography

    - :matlab:`'zrange'`

        2-vector setting the limits of the :math:`z` axis.

    - :matlab:`'colorMap'` (default: ``Parula``)

        Color map.

    - :matlab:`'title'`

        Title to display on the movie, if any.

    - :matlab:`'factor'` (default: ``1``)

        Correction factor to the |OPD|, for instance 5.55e-3 to convert the |OPD| into |DM|.

    - :matlab:`'label'` (default: :matlab:`'Optical path difference (nm)'`)

        Label to put on the color scale.

    - :matlab:`'imType'` (default: :matlab:`'OPD'`)

        Cell array of the images of the object to be displayed within the figure of the movie, side by side: :matlab:`'OPD'`, :matlab:`'T'`, :matlab:`'DWx'`, :matlab:`'DWy'`, :matlab:`'Ph'`.

    - :matlab:`'axisDisplay'` (default: ``true``)

        Display the axes or not.

    - :matlab:`'rate'` (default: ``25``)

        Video rate in frames per second.

    - :matlab:`'frameTime'` (default: ``[]``)

        Time between successive frames. If specified, the time is displayed on each frame.

    - :matlab:`'timeUnit'` (default: ``s``)

        Unit of the time to be displayed. Can be :matlab:`'s'`, :matlab:`'min'` or :matlab:`'h'`.

    - :matlab:`'timeFontSize'` (default: ``[]``)

        Set the font size displayed on the movie.

    - :matlab:`'timeFontColor'` (default: ``[0, 0, 0]``)

        Set the color of the displayed time label. By default it is black, but depending on the colormap of the image, it may be necessary to use a brighter color. White is ``[1, 1, 1]``.

    - :matlab:`'timeSize'`

        If the default size is not appropriate, choose a specific one using this option. ``16`` can be a good starting value.

