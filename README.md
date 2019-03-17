# ReadYAML
### What is YAML? 
YAML stands for 'YAML Ain't Markup Language', it is a human-readable data serialisation language and it is commonly used for configuration files.

### What is this thing?
This little MATLAB utility reads in simple YAML files and returns them as structures, where YAML key/value pairs are fields of the structure. See example:

# Example file
### settings.yml
```yaml
# Settings to be used by various SLM / Prairie interfacing scripts

# SLM
TransformFile: 3DTransform_20181017_1617.mat
SLM_Pixels_X: 512
SLM_Pixels_Y: 512
SLM_BitDepth: 8
ZeroOrderBlockSize_PX: 35 
HologramLibraryName: GenerateHologramCUDA  
AutoAdjustWeights: 1  # true
WeightingFile: 20170524_Satsuma_Leica25x_Weights_MaxCoord128.mat

# Galvo positions (GPLMaker)
ScanAmp_X: -8.361121 6.821121  # left,right - save a grid gpl
ScanAmp_Y: 8.345181 -8.145181  # top,bottom - save a grid gpl
FOVsize_OpticalZoom: 1.2
FOVsize_PX: 512
FOVsize_UM_1x: 854.5

# Mark points (XMLMaker)
LaserName: Photostim
LaserPowerScaleFactor: 2.1
LaserPowerFile: Bruker2_PowerFile.mat  #mat file containing PV->mW fit
TriggerLine: PFI1
VoltageOutputCategoryName: Lloyd
VoltageOutputExperimentName: 1msPulseOut_6713AO0

# RawDataStream
FlipEvenLines: 0
```

# Usage
```matlab
settings = ReadYaml('settings.yml')
```
```matlab
settings = 
  struct with fields:
                  TransformFile: '3DTransform_20181017_1617.mat'
                   SLM_Pixels_X: 512
                   SLM_Pixels_Y: 512
                   SLM_BitDepth: 8
          ZeroOrderBlockSize_PX: 35
            HologramLibraryName: 'GenerateHologramCUDA'
              AutoAdjustWeights: 1
                  WeightingFile: '20170524_Satsuma_Leica25x_Weights_MaxCoord128.mat'
                      ScanAmp_X: [-8.3611 6.8211]
                      ScanAmp_Y: [8.3452 -8.1452]
            FOVsize_OpticalZoom: 1.2000
                     FOVsize_PX: 512
                  FOVsize_UM_1x: 854.5000
                      LaserName: 'Photostim'
          LaserPowerScaleFactor: 2.1000
                 LaserPowerFile: 'Bruker2_PowerFile.mat'
                    TriggerLine: 'PFI1'
      VoltageOutputCategoryName: 'Lloyd'
    VoltageOutputExperimentName: '1msPulseOut_6713AO0'
                  FlipEvenLines: 0
```
