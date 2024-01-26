This project describes how to use an InputDialog Activity with Timeout.

My first attempt was using the Pick and PickBranch Activities with two branches. 
In the first branch I configured the Trigger with the InputDialog Activity and the second branch with a Delay Activity, 
which would be my timeout, but when the InputDialog Activity is executed, the entire process is blocked waiting for the user's response. 
Changing the order of the branches didn't solve the problem either, and using the parallel activity didn't work either. 
The solution was to use the Invoke Workflow File Activity. Below I list the step by step to achieve the desired objective:

Some actions are necessary:
1- Create a Invoke Workflow with the Input Dialog Activity.
2- For the Invoke Workflow File Activity:
     a- Configure the desired Timeout
     b- Select the Isolated property (otherwise the Dialog will not close). 
     c- Isolate the activity with a Try/Catch and
     d- In the informative Message Box Activity in the Catch field, configure a Timeout as well.
