#Data
Data are values of *quantitative* or *qualitative* variables belonging to a set of items.

#Type of Data
1.    Raw data
2.    Processed data

## Raw data
1. 0 software processing
2. 0 manipulation
3. 0 exclusion of data
4. 0 summarization

## Processed data
1. One variable per column
2. One observation per row
3. One table for each kind of variable
4. One column to link to related table
5. One header row
6. One physical file per table


#The Components of Tidy data
1. The raw data
2. The tidy data
3. The code book
4. The instruction list

##The code book
1. Information about variables
2. Information about the summary choices 
3. Information about the experimental study design

##The instruction list
1. Script
2. Input raw data
3. Output tidy data
4. Parameters to the script

#Principles of Analytics Graphics

##Principle 1 Show comparisons

##Principle 2 Show causality,mechanism,explanation, systematic structure

##Principle 3 Show multivariate data

##Principle 4 Integration of evidence

##Principle 5 Describe and document the evidence with appropriate labels,scales, sources etc.,

##Principle 6 Content is king.

###Edward Tufte Beautiful Evidence www.edwardtufte.com

#Why do we use graphs ?

1. To undertand data properties.
2. To find patterns in data.
3. To suggest modeling strategies.
4. To debug analyses.
5. To communicate results.

### Exploratory graphs deals with first 4.

#Simple one dimensional summary

1. Five-number summary
2. Boxplots
3. Histograms
4. Density plot
5. Barplot

#Simple two dimensional summary 

1. Multiple/overlayed 1-D plots(lattice/ggplot2)
2. Scatterplots
3. Smooth scatterplots

# > 2 dimensions

1. Overlayed/multiple 2D plots
2. Use color,size,shape to add dimensions
3. Spinning plots
4. Actual 3-D plots.


#Graphics Plotting system

## The Base plotting system

## The Lattice system
Most useful for conditioning types of plot (xyplot,bwplot)

##  ggplot2

Takes good of both worlds

## Base Plotting system

1. graphics - contains plotting functions for the base graphics systems.
2. grDevices - contains code for graphics devices X11 , pdf, postscript,PNG

## Two phases

1. Initializing the plot
2. Annotating an existing plot

## Lattice plotting system

1. lattice - producing graphics
2. grid - graphing system.

# Graphics devices

?Devices

1. Screen devices
2. File devices
   a. Vector formats
      * pdf
      * svg
      * win.metafile
      * postscript
   b. Bitmaps
      * png
      * jpeg
      * tiff
      * bmp



