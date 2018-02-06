
# Running EasyBuild inside a singularity container

## Install singularity: http://singularity.lbl.gov/install-linux

##  As root:

Build the image
```
$> singularity build centos-7-easybuild-3.5.1 centos-7-easybuild-3.5.1.bootstrap
```

## As regular user:

Once build is done open run the container as standard user (non root)
```
$> singularity shell --shell /bin/bash centos-7-easybuild-3.5.1
```

If you want write permissions in the container:
```
$> chown yourusername centos-7-easybuild-3.5.1
$> singularity shell --shell /bin/bash -w centos-7-easybuild-3.5.1
```

Once inside the container
```
$> source /etc/profile.d/z00_lmod.sh
$> eb --help
```
