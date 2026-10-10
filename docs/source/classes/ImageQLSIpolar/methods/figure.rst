.. dropdown:: **figure** |subTitle| Displays the image content of the object in a GUI. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>

    .. code-block:: matlab

        objList.figure()

    .. raw:: html
      
        <p class="title">Description</p>

    ``objList.figure()`` displays the images contained in the object via a GUI. ``objList`` can be a vector of **ImagePolar** objects.
    |hr|
    
    Here is an overview of the interface:

    .. figure:: /images/ImagePolar_figure.png
        :width: 1200
        :align: center

        GUI interface for display and study of ImagePolar objects

    This GUI can display the wavefront images, either the averaged wavefront or the 4 wavefront images. In addition, it displays the ellipticity, the retardance or the dichroism image. For each type of image the limit values for display can be set.

