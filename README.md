# boinc_uploader_centos7
This is a pre-compiled binary for boinc file_upload_handler cgi. The documentation on the boinc project site wasn't entirely clear, but this seems to work.

Here's a list of steps I think were needed to compile successfully. This was done in a `centos:latest` docker container with mounted volume for the output.

```
yum install -y epel-release vim git mod_fcgid auto-tools make autoconf automake curl-devel.x86_64 curl.x86_64 libcurl-devel.x86_64 fcgi-devel mysql-devel.x86_64 libtool gcc gcc-c++ mariadb-devel.x86_64 mariadb-libs.x86_64 
git clone git clone https://github.com/BOINC/boinc.git
git clone https://github.com/BOINC/boinc.git
cd boinc/
./_autosetup 
./configure --enable-fcgi=yes --enable-server --disable-client --disable-manager
make
make install
ls -alh /usr/local/lib/boinc-server-maker/sched/file_upload_handler
ls -alh /usr/local/lib/boinc-server-maker/sched/
ls -alh /usr/local/libexec/cgi-bin/fcgi_file_upload_handler
```

