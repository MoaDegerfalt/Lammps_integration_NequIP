# Lammps_integration_NequIP
How to deploy models and benchmark using LAMMPS. 

For now this is a stupid way but it works. 
1. Move the folders containing the trained models that you want to deploy in to a folder named build/
2. Make an array containing the folder names DIRS = (run1 run2 ...)
3. Now there is a folder in ~/lammps/models/ containing the deployed models, deployed_run1.pth deployed_run2.pth ...
4. In order to run and benchmark the deployed model som python programming is required. Working progress. 
    - Run_lammps script use the input file in.lammps in this file there is a path to the deployed model that needs to be a variable.
    - using sbatch --array=0-100 run_lammps the variable is created that can be used to change the model thats is being benchmarked.
    - One stupid but simple way of solving it could be to create one in.lammps file for each model and simply name them in.lammps_${SLURM_ARRAY_TASK_ID} 0-how many filed you have.
    - Now comes the problem of logging the output data in a good way. Could this be done using wandb.ai? How to connect the hyperparameters to the benchmark of growth rate? 
