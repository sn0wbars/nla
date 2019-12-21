These are the synthetic datasets used for evaluating the dense matching module in the paper.

When you want to mimic the same experiment, you should read in the intrinsic/extrinsic camera parameters, skip the BA step, and run the dense matching algorithm (plane sweeping).



Some notes:

- Each dataset name represents the log10 of the baseline, for example, -1.5 means the baseline (diameter) of the circular motion is 10^-1.5 of the distance from the camera to the closest scene point, which is 1.9399.

- K.txt in each dataset folder contains the 3x3 intrinsic camera matrix.

- RT%%%%.txt in each dataset folder contains the 4x4 extrinsic camera matrix relative to the first frame.

- LabelGT.txt contains the ground-truth depth labels which must be compared only to the resulted depth labels computed by using min_w=0.0 and max_w=0.56704 in DfUSMC::DenseMatching function.
  Here, the max_w value equals to 1/1.9399 (closest depth) times 1.1(margin).
