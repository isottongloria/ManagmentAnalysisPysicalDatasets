
# MAPD-B
# Distributed `k-means||` with PySpark
This is the final project for course MAPD-B. In this project, we implement the K-means|| algorithm in Python following Bahmani's paper "Scalable k-means++" and parallelized using Pyspark.

## CloudVeneto Setup

1. Open a terminal and enter the CV gate machine:

       ssh username@gate.cloudveneto.it

   When prompted, enter the longer password.
3. When inside, access the VM of your choice – usually the `master` – with
   
       ssh -i private/file.pem username@10.67.22.239   

   Use the shorter password this time.
   
5. Start the cluster by running the script `start_cluster`.
6. Enter the command `sparkup`: it should open a jupyter-notebook session
   on the 9000 port of the VM.
7. Open a new terminal and re-enter the cloud by skipping right to the VM,
   defining also the tunnelling ports:
   
       ssh -J username@gate.cloudveneto.it \
           -L 8008:localhost:9000 \
           -L 1234:localhost:8080 \
           -L 4321:localhost:4040 \
           username@10.67.22.239

   Substitute `8008`, `1234` and `4321` with the ports of your choice.
   `8008` is for the Jupyter notebook, `1234` for the Spark master page and
   `4321` for the workers’ dashboard.
9. Open `localhost:8008` (`1234`, `4321`, or the ports that you’ve chosen)
   on your browser and you should be able to access the Jupyter session and
   the Spark stuff.
11. When you finish your work, remember to stop the cluster by running the
   `stop_cluster` script from the `master` VM.

You can jump between the VMs when you’re inside with `ssh master`, `ssh
slave01` or `ssh slave02`. This is useful when you have to install new
Python packages, because you have to do it *on all three machines*.
