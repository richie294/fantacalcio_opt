# README

### Regression Notebook

The <Regression> notebook uses historical data up to 2017-2018 season for players in the Italian First Division to fit a regression 
model for every position. Positions are goalkeeper (por), defender (dif), midfielder (cen) and striker (att). Depending on the 
position, different features are used for prediction of the value added to the team. For example, goalkeepers only have goals conceded
as feature while defenders, midfielders and strikers have goals, assists and yellow/red cards. 

### Normal Optimization 

The parameters estimated in the previous notebook are used for the prediction of the value added to the team for a single player. 
Values are to be manually inputted by the user for single players depending on the position (por, dif, cen, att). Based on calculations
made with the regression prediction, categories are created for each position (e.g. <p1>, <p2>, <p3> for goalies) in which the 
expected value added and the expected bid price. 
An integer linear optimization is then performed in the General Function section through the <f> function based on the line-up
<formazione> and credits allocated to the starting line-up <crediti>. 
At the end, a simulation is performed based on the line-up and credits allocated to the starting line-up to determine which 
line-ups yield the best trade-off between value added by starting line-up and remaining credits for the rest of the team.

### Mantra Optimization 

The main difference between Normal and Mantra modes is that in the latter there are more positions; for instance, instead of defender 
there are central, left and right defender. Some players have more than one position. 
The first part of the notebook is the same as Normal version: coefficients of the regression are copied and functions for value added
prediction are created. 
After, for every valuable player three entries are to be inputted: estimation of features based on prediction function, estimated bid 
price and position. A matrix is subsequently cretaed for each position so these data point can be better handled. 
Subsequently, in the General Function section, the <f> function works similarly as the previous notebook. Depending on the starting 
line-up, matrices and vectors for the linear optimization are created and the optimization is ran. 
In the last section, simulations are ran with different line-ups and credit allocations similarly as in the previous notebook, with 
the caveat that this time credit allocation is just for the midfielders and strikers. The remaining credits are then used to 
complete the line-up and overall team score. The <extra> variable calculates the the value added to the team by the other players in 
the starting line-up and it is decided qualitatively. 
The plots show the overall score of the team during the season depending on the line up. A horizontal line for overall score equal to 
70 (equal to 2 fanta-goals) is used as the value to be overcome the most. Interestingly, line-ups with two strikers are the ones that
yield the highest overall score and the overall score drops below the 70 threshold when too much credit is allocated to too few players. 
