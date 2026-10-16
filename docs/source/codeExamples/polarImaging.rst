Temperature processing
++++++++++++++++++++++

.. dropdown:: **Polarization imaging** |subTitle|  Code to process data obtained with a polar_CGM setup |/subTitle|
    :open:


    .. code:: matlab

        %% BUILDING OF THE MEDIUM -- ME = Medium(n,nS);
        ME = Medium('water','glass');

        %% BUILDING OF THE MICROSCOPE -- Microscope(OBJ,tl_f,Sid4model,software)
        OB = Objective(60,0.7,'Olympus');
        Cam = Camera(3.45e-6,1,1);
        Grat = CrossGrating('Gamma',39e-6);
        CGcam = CGcamera(Cam,Grat,1.0615);
        CGcam.setDistance(0.8e-3);
        MI = Microscope(OB,200,CGcam,'PhaseLAB');

        %% BUILDING OF THE ILLUMINATION -- IL = Illumination(lambda);
        lambda = 550e-9;
        IL_L = Illumination(lambda,ME,1,[1 1i 0]);
        IL_R = Illumination(lambda,ME,1,[1 -1i 0]);

        %% IMPORT THE DATA
        folder = pwd;
        ItfL = importItfRef(folder,MI,'remote',1,'selection',1);
        ItfR = importItfRef(folder,MI,'remote',1,'selection',2);
        Bkg = importItfRef(folder,MI,'remote',1,'selection',3);

        %% demosaicing
        ItfR4 = ItfR.splitPolars();
        ItfL4 = ItfL.splitPolars();
        Bkg4  = Bkg.splitPolars();

        %% INTERFEROGRAM PROCESSING -- Im.QLSIprocess(IL);
        IMR = QLSIprocess(ItfR4,IL_R,"darkImage",Bkg4);
        IML = QLSIprocess(ItfL4,IL_L,"darkImage",Bkg4);

        IMbig = [IML, IMR];
        IMbig.figure

        %% defining the ImageQLSIpolar objects
        pImR = ImageQLSIpolar(IMR);
        pImL = ImageQLSIpolar(IML);
        pImR.set_eLim(0.65)
        pImL.set_eLim(0.65)

        % display
        pImL.figure
        pImR.figure

