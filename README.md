# lifeworks
 downloading Vagrant \
 also considering using jupyter-notebook to serve a python code interpreter which will have the fizzbuzz test easy to run
 vagarant will have to port forward jupyter-notebook to host port so that notebook can be accessed
 wrote fizzbuzz in python using ipython notebook interpreter locally
> def fizzbuzz():
>    for i in range(1,101):  
>        if i%3==0 and i%5==0:
>            print "fizubuzz"
>        elif i%3==0:
>            print "fizz"
>        elif i%5==0:
>            print "buzz"
>        else:
>            print str(i)

 checked results of fizzbuzz to reasonable depth\
 1\
 2\
 fizz\
 4\
 buzz\
 fizz\
 7\
 8\
 fizz\
 buzz\
 11\
 fizz\
 13\
 14\
 fizubuzz\
 16\
 17\
 fizz\
 19\

tried vagrant up. it fails with plugin conflicting dependecy errors.\ 
 trying vagrant plugin expunge --reinstall
 "vagrant expunge has been declined"
uninstalled and reinstalled vagrant.
same results as above. 

installing hostmanager pluging, it manages hosts file

vagrant plugin install vagrant-hostmanager
 
 trying vagrant again
 1. vagrant up 
 vagrant comes up !!!
default: SSH address: 127.0.0.1:2222
    default: SSH username: vagrant
    default: SSH auth method: private key
==> default: Machine booted and ready!
 default: Mounting shared folders...
    default: /vagrant => /home/sanket-rhythmone/lifeworks

trying vagrant ssh default
Errors - OpenSSL version mismatch. Built against 1000200f, you have 1000105f

inspecting vagrantbox ssh config info using 
vagrant ssh-config
gives details about the vagrant box, and there is a ssh private key location too.

trying alternative ssh login vagrant ssh using ssh key and 127.0.0.1 port2222
WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!
Host key verification failed.
remove known host for vagrant 
ssh-keygen -f "/home/sanket-rhythmone/.ssh/known_hosts" -R "[127.0.0.1]:2222"

now trying ssh again 
ssh -i /home/sanket-rhythmone/lifeworks/.vagrant/machines/default/virtualbox/private_key -p 2222 vagrant@127.0.0.1
Welcome to your Scale Factory virtual machine.
[vagrant@centos6 ~]$
success loggin into vagrant

