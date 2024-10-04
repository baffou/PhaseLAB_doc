Temperature processing
++++++++++++++++++++++

.. dropdown:: **Temperature processing** |subTitle|  Code to convert a wavefront distorsion image into a temperature map |/subTitle|
    :open:


    .. code:: matlab

        %% BUILDING OF THE MEDIUM -- ME = Medium(n,nS);
        ME = Medium('water','glass');

        %% BUILDING OF THE MICROSCOPE -- Microscope(OBJ,tl_f,Sid4model,software)
        OB = Objective(60,1.3,'Olympus');
        MI = Microscope(OB,180,'sC8-944','PhaseLIVE');
        MI.refl = false;

        %% BUILDING OF THE ILLUMINATION -- IL = Illumination(lambda);
        lambda = 550e-9;
        IL = Illumination(lambda,ME);

        %% IMPORT THE DATA
        folder = pwd;
        Im = importItfRef(folder,MI);

        %% INTERFEROGRAM PROCESSING -- Im.QLSIprocess(IL);
        IM = Im.QLSIprocess(IL,'definition','low');

        %% CREATION OF THE MICROSCOPE
        clear Med
        Med(1) = MediumT('BK7',  1e-3,'progressive');
        Med(2) = MediumT('water',1e-3,'progressive');
        %Med(3) = MediumT('water',0.01e-3,'progressive');

        Med = mesher(Med,MI);

        %% linear algorithm, for temperature increases < 30°C
        [IMT, GreenW, GreenT] = IMs.TMPprocess(Med);

        %% non linear algorithm
        [IMT, GreenW, GreenT] = IMs.TMPprocess(Med,'g',0.4,'nLoop',10,'imExpander',true,'TO',22);

        %% DISPLAY THE RESULTS
        IMT.figureT

