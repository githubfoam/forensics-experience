# dockerization sandbox

docker host - centos
~~~
$ hostnamectl
   Static hostname: control01
         Icon name: computer-vm
           Chassis: vm
        Machine ID: cfa0388701ff415dbceb1d083ec3fdfd
           Boot ID: e3ed69389e714d6fbd983d0276ad5fb3
    Virtualization: kvm
  Operating System: CentOS Linux 7 (Core)
       CPE OS Name: cpe:/o:centos:centos:7
            Kernel: Linux 3.10.0-957.1.3.el7.x86_64
      Architecture: x86-64
~~~
docker guest - ubuntu - portable
~~~
$ sudo docker run -it --rm foremost:1.0 uname -a
Linux bfb46994de64 3.10.0-957.1.3.el7.x86_64 #1 SMP Thu Nov 29 14:49:43 UTC 2018 x86_64 x86_64 x86_64 GNU/Linux
~~~
foremost
~~~
$ docker build . -f /vagrant/Dockerfile.foremost -t foremost:latest
$ docker run foremost -h

add additional file headers for detection, e.g. adding entries or uncomment examples:
/etc/foremost.conf

The parameter -t all tries to recover all known file types.
# foremost -t all -i /path/to/image -o outputdir

foremost -t doc,jpg,pdf,xls -i image.dd
ls output

foremost -t jpeg -i /dev/sda1
foremost -t pdf -T -i /dev/sda1
# what partition to search
mount
lsblk

~~~
~~~
Digital Forensics Tool Testing Images
http://dftt.sourceforge.net/
~~~
