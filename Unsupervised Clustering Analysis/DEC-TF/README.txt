Installation command:

pip install -r requirements.txt

Use the following command to run the code train.py in CRC:

#!/bin/csh
#$ -M email@nd.edu 
#$ -m abe
#$ -q gpu
#$ -l gpu_card=2
#$ -N TFjob

module load tensorflow
pip install configargparse --user
pip install -U scikit-learn --user
fsync $SGE_STDOUT_PATH &
python train.py

optional arguments (type after train.py):
  -h, --help            show this help message and exit
  --batch-size BATCH_SIZE
                        Train Batch Size
  --gpu-index GPU_INDEX
                        GPU Index Number

Use the following command to return the latent representation z.tsv and meta.tsv

#!/bin/csh
#$ -M email@nd.edu
#$ -m abe
#$ -q gpu
#$ -l gpu_card=2
#$ -N TFjob

module load tensorflow
pip install configargparse --user
pip install -U scikit-learn --user
fsync $SGE_STDOUT_PATH &
python inference.py

Upload z.tsv and meta.tsv for visualization at: https://projector.tensorflow.org


Note:

I include the checkpoints and the result from my run. Delete first if you want to redo the run.