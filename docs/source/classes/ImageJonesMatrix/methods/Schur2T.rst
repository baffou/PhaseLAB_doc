.. dropdown:: **Schur2T** |subTitle| Turns the Schur decomposition into a complex transmittance image. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>

    .. code-block:: matlab

        T = obj.Schur2T(U,V);

    .. raw:: html
      
        <p class="title">Description</p>

    ``T = obj.Schur2T(U,V);`` Returns the complex transmittance image ``T`` from the Schur decomposition ``[U, V]``, normally obtained using the ``J2Schur`` method of the class |ImageJonesMatrix|:

    .. code-block:: matlab

        [U, V] = J2Schur(J);
        T      = Schur2T(U,V);
        % or equivalently, in a single step:
        T = J2T(J);

    This function can be used with an array of objects.

    |hr|
        