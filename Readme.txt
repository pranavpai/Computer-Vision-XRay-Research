Xray_subset.ipynb [MAIN NOTEBOOK]
This is our main independent notebook that runs a subset of the original dataset.

Xray.ipynb 
This notebook is a copy of the subset notebook. Run this if you would like to use the complete dataset (~ 9000 images total)

occlusion.ipynb [supporting scripts]
Generates a DataFrame (occlusion_df) that lists the names, areas, and overlap counts for each polygon (object or intersection).
This code is used for quantifying the amount of occlusion in the images in each image.
object detection and visualization, handling overlapping objects in images and analyzing their spatial relationships through graph representation.

G_Xray.ipynb [supporting scripts]
Performs white Space removal and resizing for all train and test images and resizes the images to 584 x 688

*Caveat* - Due to severe computational issues we had to pivot in using the subset data.





