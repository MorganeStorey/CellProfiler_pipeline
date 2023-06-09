# CellProfiler_pipeline

The .cpproj file contains a CellProfiler image analysis pipeline designed to quantify immunofluorescence signals from confocal data: pSyn (channel 1), LAMP1 (channel 2), TH (channel 3), and p62 (channel 4). This pipeline was designed with the help of Dr. Camille Loiseau as part of my master's thesis.

The pipeline identifies, measures and exports:
- TH+ cell body objects, with a nucleus between 60-180 pixels in diameter and a cytoplasm with a minimum feret diameter above 70 pixels (object "RelateObjects_cell_body").
- pSyn+ aggregate objects between 5-200 pixels in diameter and with a minimum intensity >0.03, if and only if they belong to cell bodies (object "RelateObjects_psyn").
- p62+ objects between 5-200 pixels in diameter, if and only if they belong to cell bodies (object "RelateObjects_p62"). The pipeline also stores p62 objects located within the pSyn convex hull in a separate object (object "RelateObjects_psyn_p62").
- LAMP1+ objects (lysosomes) between 3-20 pixels in diameter, if and only if they belong to cell bodies (object "RelateObjects_lamp1"). The pipeline also stores LAMP1 objects located within the pSyn convex hull in a separate object (object "RelateObjects_psyn_lamp1").

Two example images are avaible in the example_images file to test the pipeline for yourself. To do this, you first need to download CellProfiler on your computer by following the instructions at this adress: 

https://cellprofiler.org/releases

Once downloaded, open the .cpproj file with CellProfiler and drag and drop the images from the example_images file into the first module ("Images"). The pipeline can be run either in one go (press "Analyze images" button) or one step at a time (press "Start Test Mode" button). To understand the way each module functions, I recommend running the pipeline in Test Mode after clicking the eye icons next to each module to show the output of each module. I have included a brief description of the purpose of each module in the comment box to help comprehension (top right of the CellProfiler interface).

The pipeline was developed in CellProfiler v4.2.1. 
