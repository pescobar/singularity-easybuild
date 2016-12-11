
# Running EasyBuild inside a singularity container

## Install singularity: http://singularity.lbl.gov/install-linux

##  As root:

First create an empty image
```
$> singularity create -s 4096 centos7.2-easybuild3.0.1
```

Now bootstrap it
```
$> singularity bootstrap centos7.2-easybuild3.0.1 centos-7.2-easybuild-3.0.1.bootstrap
```

## As regular user:

Once bootstrap is done open run the container as standard user (non root)
```
$> singularity shell --shell /bin/bash centos7.2-easybuild3.0.1
```

If you want write permissions in the container:
```
$> chown yourusername centos7.2-easybuild3.0.1
$> singularity shell --shell /bin/bash -w centos7.2-easybuild3.0.1
```

Once inside the container
```
$> source /etc/profile.d/z00_lmod.sh
$> eb --help
```
