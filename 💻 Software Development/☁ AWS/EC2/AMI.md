---
description: Amazon Machine Image
---
# Visibility

* Public: Everyone can see and use them
* Explicit: You can allow specific users to see them
* Implicit: Private

This is not the same as publishing them to the AMI marketplace though.

# Limits

* EC2 has a limit on the maximum number of running instances per region.
* There are a lot of limits, they can be viewed via EC2 -> Limits.
* If needed you can ask AWS to raise the limits.
* All AMIs are region specific
* The max number of AMIs is 10'000 since they're using EBS snapshots.

# Creating an AMI

1. Load EC2 dashboard
2. Go to instances and select instance
3. Actions -> Images and Templates -> Create Image
4. Give it a name & create

# Launch own AMI

1. Load EC2 dashboard
2. Launch instances
3. My AMIs
