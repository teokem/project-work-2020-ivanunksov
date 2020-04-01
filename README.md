# <center>Interactive analysis of molecular motors motion using a Jupyter notebook</center>
## <center>Ivan Unksov</center> 
### <center>ivan.unksov@ftf.lth.se</center> 


Molecular motors are constructs that employ intermolecular interactions to propel themselves. We are developing an artificial molecular motor, the Lawnmower (LM), based on a micron-sized bead coated with the trypsin enzyme. Trypsin molecules cleave a peptide track enabling the LM movement along the track. Anomaluos diffusion coefficent characterizes the motion, and in this notebook we get the coefficient from calculating time averaged mean squared displacement (TA MSD) of a motor.  

## How the notebook works

As some motors in our experiments aggregate or get stuck in their tracks, it is important to choose trajectories for analysis based on how they look. The notebook `LM_tracks_010420` allows for choosing trajectories of motors from a .csv file and analyzing them. It calculates TA MSD for the chosen motors.
<center>$\textrm{TA MSD}=\frac{1}{T-\tau}\sum_{t=0}^{T-\tau} (r(t+\tau)-r(t))^2$ </center>    
where $T$ -  total measurement time, $\tau$ - displacement time. Displacement time maximum is set to one-tenth of $T$.
Note that TA MSDs calculation is time-intense – for a quicker result choose not more than 2 trajectories when running the notebook. The data is fitted using linear regression, and anomalous diffusion coefficient is calculated.
<center>$\alpha=\frac{d(\log{\textrm{TA MSD}})}{d(\log{\tau})}$</center>  
Notebook outputs a .csv file 'TAMSD' with TA MSDs values and an image 'TAMSD&alpha' of plots of $\log{\textrm{TA MSD}}$ vs. $\log{\tau}$ and $\alpha$ vs. $(\textrm{trajectory number})$.

## Packages used in the notebook

| Package    	| Used for                   	|
|------------	|----------------------------	|
| numpy      	| operations with arrays     	|
| pandas     	| operations with dataframes 	|
| matplotlib 	| plots                      	|
| math       	| maths operations           	|
| scipy      	| linear regression fit      	|
| os         	| switching directories      	|
