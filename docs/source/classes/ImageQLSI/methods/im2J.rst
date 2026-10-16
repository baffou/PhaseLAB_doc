.. dropdown:: **im2J** |subTitle| Converts two sets of 4 QLSI images into a Jones matrix image (|ImageJonesMatrix| object). |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>
    
    .. code-block:: matlab

        J = im2J(IML, IMR); % IML and IMR are (:,4) ImageQLSI arrays

    Returns the Jones Matrix ``J`` object related to two polarization measurements ``IML`` and ``IMR``. A polarization measurements is composed of 4 QLSI measurements assembled as a (1,4) |ImageQLSI| array. These two inputs should correspond to :abbr:`LCP (left-handed circular polarization)` and :abbr:`RCP (right-handed circular polarization)` illuminations. The two input can also consist of a series of polarization measurements, as a (:,4)-array of |ImageQLSI| objects.
