# LIO-SAM-6AXIS

## Problem && Improvement
1. terminate called after throwing an instance of 'std::runtime_error'  what():  PreintegratedImuMeasurements::integrateMeasurement: dt <=0.

Reason: Imu data is repeated or reversed.
Solution: Set dt>0 in imuPreintegration::imuHandle as the condition for imuQueOpt and imuQueImu to perform push_back. Also, Make sure dt>0 in imuIntegratorImu_->integrateMeasurement().

2. for 6AXIS IMU Improvement.
Modify the call about imu orientation in the imuConverter function in utilith.h.


## Acknowledgement

  - LIO-SAM is based on LOAM (J. Zhang and S. Singh. LOAM: Lidar Odometry and Mapping in Real-time).
  - LIO-SAM code: (https://github.com/TixiaoShan/LIO-SAM)
