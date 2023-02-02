### pre-install

```sh
sudo yum install ncurses-devel openssl-devel -y
sudo yum groupinstall "Development Tools" -y
```

### install erlang (otp25.1)
```sh
cd /tmp
wget https://github.com/erlang/otp/releases/download/OTP-25.1/otp_src_25.1.tar.gz -O otp25.tar.gz
# OR if you are facing issue with wget, try downloading the package elsewhere and use ftp to transfer package to the server
tar xfz otp25.tar.gz
cd otp_src_25.1/
./configure
make 
sudo make install
```

### install elixir (1.14.2)

go to https://github.com/elixir-lang/elixir/tags and get a stable version

```sh
cd ..
wget "https://github.com/elixir-lang/elixir/archive/refs/tags/v1.14.2.tar.gz"
# OR if you are facing issue with wget, try downloading the package elsewhere and use ftp to transfer package to the server
tar xfz v1.14.2.tar.gz
cd elixir-1.14.2/
make
# do the rest as root
sudo su
export PATH="${PATH}:/usr/local/bin"
make install
```

### install deps

install the 2 minimal required deps

```sh
mix local.hex --force
mix local.rebar --force
```


If installation and configuration is successful, you should see the following when running the `iex -v` command:

```
Erlang/OTP 25 [erts-13.1.2] [source] [64-bit] [smp:2:2] [ds:2:2:10] [async-threads:1] [jit:ns]

warning: the VM is running with native name encoding of latin1 which may cause Elixir to malfunction as it expects utf8. Please ensure your locale is set to UTF-8 (which can be verified by running "locale" in your shell)
IEx 1.14.2 (compiled with Erlang/OTP 25)
```
