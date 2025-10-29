```bash
# vm-test-1
ssh -i "~/.ssh/ekomobong.pem" ubuntu@ec2-98-88-36-29.compute-1.amazonaws.com

# vm-test-2
ssh -i "~/.ssh/ekomobong.pem" ubuntu@ec2-35-175-184-252.compute-1.amazonaws.com

# vm-test-3
ssh -i "~/.ssh/ekomobong.pem" ubuntu@ec2-54-221-185-165.compute-1.amazonaws.com
```

```bash
# Create Swarm (vm-test-1)
docker swarm init --advertise-addr 98.88.36.29
# Make sure to enable port `2377` in the inbound rules.
```

```bash
# join swarm (vm-test-2 & vm-test-3)
docker swarm join --token SWMTKN-1-35ginj4xb66mzm76605lbdvgmtnwcryd0girghhw9qsi3dyi1u-2p32zqbkmnu3commu7gkpofkp 98.88.36.29:2377
```

```bash
# vm-test-1
docker node ls
```
