# general_geochem_plotting_program
A Dash app containing a plotting program designed specifically for geochemical data. Its best use is for rapid data visualization.

The GUI consists of three main plots: A scatter diagram, a REE / spider-diagrams, and a graph dedicated to statistical charts (e.g., histograms, violin plots, box plots). 

## Uploading Data
At the bottom of the screen when the app is run, you may either drag and drop an excel file (<filename>.xlsx) or click and navigate to the file:
<img width="605" alt="Screen Shot 2022-10-23 at 9 36 59 AM" src="https://user-images.githubusercontent.com/65908927/197404302-edef4381-363d-402d-8e41-3e2229445264.png">

The formatting to the program is specific. The column headers in the uploaded excel file must be the variables that you wish to plot. For element and oxide data, they must be in the following format:
sio2, al2o3, feo, mgo, cao, na2o, k2o, tio2, p2o5, mno, Ni, Cr, Sc, V, Ba, Rb, Sr, Zr, Y, Nb, Ga, Cu, Zn, Co, Pb, Th, U, La, Ce, Pr, Nd, Sm, Eu, Gd, Tb, Dy, Ho, Er, Tm, Yb, Lu, Hf, Ta, Cs, P, K, h2o, co2, so2, S, h2s, so4
and they do not need to be in that order. If you do not have P and K calculated, the program will do it for you when making spider-diagrams. All other column headers will be read as-is.

## Scatter Diagram
Once the data is uploaded, dropdown menus are populated with the column headers in your excel file. You must also select the graph type you wish to use under the dropdowns. The slider changes the symbol size. X and Y axis label inputs are below the slider. Subscripts and superscripts require unicode. Symbol color is changed with the two color pickers below the chart.
Once the parameters are picked, click the 'Update Graph' button to make the plot. At this point, you can hover over the data points for some metadata. You can also click and drag a box on the plot to zoom in. Double click to reset.

<img width="1273" alt="Screen Shot 2022-10-23 at 9 53 12 AM" src="https://user-images.githubusercontent.com/65908927/197405022-c0ae5916-fd90-4d28-be73-0120412d5ea4.png">

In the event you wish to add data to the plot, you must re-upload a spreadsheet and search for what you want to add. For instance, in the screenshot below, a new spreadsheet has been uploaded and the unit called 'Pumice Flat' has been searched for under the column name 'unit'. The legend name for the added data follows appropriately. The data is added by clicking the 'Add Data' button.

<img width="1270" alt="Screen Shot 2022-10-23 at 10 01 11 AM" src="https://user-images.githubusercontent.com/65908927/197405296-27b3fd03-fb80-42c0-a0ac-4eb2ce70508b.png">


## Spider Diagram
With regard to ordering your elements, there are three options for creating REE and spider digrams. The first is the classic REE diagram (La-Lu with the exception of Pm) and the other two are spider digarms that are ordered by incompatibility (depending on who you ask). The first (Spider (Compat.)) is the standard order found in White (2013). The other is the order seen in Rudnick and Gao (2003) that is used primarily to look at enrichments of crustal reservoirs relative to BSE.
The normalization schemes will normalize your data as ppm. At this point you should ask yourself which normalization scheme is your favorite and why it is Primitive Mantle. References for the normalizing values are as follows - C1 Chondrite: McDonough and Sun (1995), Primitive Mantle: McDonough and Sun (1995), Eroded Earth: Palme and O'Neill (2003), MORB: White and Klein (2012). K and P are calculated from the oxide abundance in your input dataset.
You may (de-)select elements you wish to include/exclude with the checkboxes above the plot. Symbol size, x and y axis labels, and color is as it is in the scatter plot. At current, the color option treats the color options as classification. That is, there will not be a continuous color gradient applied that is corresponds to elemental concentrations. Note that you must create a graph before the 'Color By:' dropdown populates.

<img width="1274" alt="Screen Shot 2022-10-23 at 10 28 37 AM" src="https://user-images.githubusercontent.com/65908927/197406547-eb3be279-c0b6-43d4-8736-8f0dce65315c.png">


## Statistical Charts
Please note these, and indeed the entire program, is still underconstruction. I currently find the histograms moderately useful at best. I mostly find this section useful to get a broad look at distributions, or, data filtering and classification with box plots.

<img width="1243" alt="Screen Shot 2022-10-23 at 10 35 55 AM" src="https://user-images.githubusercontent.com/65908927/197407052-8ffcc681-75b2-48fa-bb04-c4d8e8996267.png">


<img width="1242" alt="Screen Shot 2022-10-23 at 10 37 36 AM" src="https://user-images.githubusercontent.com/65908927/197407054-cbe9d077-2b5d-4ce9-a738-7d1d7d526304.png">


## Installation and Use
The easiest way to get everything you need to run the program is to download the Anaconda Distirbution: https://www.anaconda.com/products/distribution/installation-success
Once this is done, you can install and run the program locally with virtual environment. In your terminal, type:
```
git clone https://github.com/Lewisc2/General-Geochem-Plotting-Program
cd /filepath/General-Geochem-Plotting-Program
conda create -n General-Geochem-Plotting-Program python=3.9.7
conda activate General-Geochem-Plotting-Program
conda install --file requirements.txt
spyder General-Geochem-Plotting-Program
```

To shutdown the program, in your terminal type
```
conda deactivate
```

Now that all the requirements are installed and the program is cloned, you can reactivate the program at anytime by using only the following lines from above
```
cd /filepath/General-Geochem-Plotting-Program
conda activate General-Geochem-Plotting-Program
spyder General-Geochem-Plotting-Program
```

Happy Plotting






