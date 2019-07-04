# shell
some basic shell codes

## add a user
sudo useradd -s /bin/bash -g group –G root -d /home/username username -m
## password
sudo passwd username

## change the authority of dir or file
chmod 700 -R dir/filename
7:owner
0:group
0:others
