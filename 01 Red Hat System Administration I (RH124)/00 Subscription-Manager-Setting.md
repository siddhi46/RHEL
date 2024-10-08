sudo subscription-manager remove --all
sudo subscription-manager unregister
sudo subscription-manager clean
sudo subscription-manager register --username atul_kamble --password LEJ@5 --auto-attach
subscription-manager register --username atul_kamble --password LEJ@5 --auto-attach --force
sudo subscription-manager register
username:atul_kamble
password:LEJ@5
sudo subscription-manager refresh
sudo subscription-manager list --available
sudo subscription-manager list --available --all
sudo subscription-manager attach --pool=2c94c2e3890c6f900189690a359d0f05
sudo yum update -y