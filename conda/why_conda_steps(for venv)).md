try to install scipy uising pip having error like ERROR: Failed cleaning build dir for numpy and failde to build wheel.
then found a stackoverflow to use conda. need virtual invironment and anaconda (had sley error of ~/ path..where i am 
using ~/ but aredy in folder where anacoda is so. resolved  without ~/ ).then follow this article to create v env

https://www.machinelearningplus.com/deployment/conda-create-environment-and-everything-you-need-to-know-to-manage-conda-virtual-environment/

         " conda create --name {env_name} {python==3.7.5} "

  but for getting py version 
  https://www.geeksforgeeks.org/machine-learning/set-up-virtual-environment-for-python-using-anaconda/
           
           " conda search "^python$" "
