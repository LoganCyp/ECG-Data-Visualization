# ECG Data Visualization

A Visualization Software for Electro Cardiograph Scans

## 



Loading in The Dataset and plotting using a random plot function.

    load('ECGData/ECGData.mat');

    PlotRandomScan(ECGData,14); 
    
The random data function that pulls the scans from the .mat file

    function PlotRandomScan(ECGData,randomSeed)

    if nargin==2
        rng(randomSeed)
    end

    M = size(ECGData.Data,1);
    idxsel = randperm(M,4);
    for numplot = 1:4
        subplot(2,2,numplot)
        plot(ECGData.Data(idxsel(numplot),1:3000))
        ylabel('Volts')
    if numplot > 2
        xlabel('Samples')
    end
    title(ECGData.Labels{idxsel(numplot)})
    end

    end




