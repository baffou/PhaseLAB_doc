
.. dropdown:: **getROI** |subTitle| Returns the camera ROI coordinates. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>
    
    .. code-block:: matlab

        % prototype
        val = obj.getROI();

    .. raw:: html
      
        <p class="title">Description</p>

    ``val = obj.getROI();``  return a 4-vector containing the coordinates of the bottom-left and top-right corners of the ROI, as ``val = [x1,x2,y1,y2]``.
