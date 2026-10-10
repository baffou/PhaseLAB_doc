.. dropdown:: **J2Schur** |subTitle| Returns the Schur decomposition of the Jones Matrix. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>

    .. code-block:: matlab

        [U, V] = obj.J2Schur();

    .. raw:: html
      
        <p class="title">Description</p>

    ``[U, V] = J.J2Schur();`` Returns the Schur decomposition ``[U, V]`` of the Jones Matrix ``J``, where ``V`` is an upper triangular matrix and ``U`` is a unitary matrix. once obtained, they can used to compute the complex transmittance ``T`` using the method ``Schur2T``:

    .. code-block:: matlab

        [U, V] = J2Schur(J);
        T      = Schur2T(U,V);
        % or equivalently, in a single step:
        T = J2T(J);

    This function can be used with an array of objects.

    |hr|
        