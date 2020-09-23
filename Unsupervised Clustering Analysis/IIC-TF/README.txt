Install the requirements:

pip install -r requirements.txt

To run the code in CRC use the following command:

#!/bin/csh
#$ -M email@nd.edu
#$ -m abe
#$ -q gpu
#$ -l gpu_card=2
#$ -N TFjob

module load tensorflow/2.0
pip install tensorflow-datasets --user
fsync $SGE_STDOUT_PATH &
python models_iic.py
