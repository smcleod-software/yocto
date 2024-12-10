The following fixes the network_disable permission denied error.

Note, this solution was taken from https://www.reddit.com/r/embedded/comments/1cx0csa/embedded_linux_ubuntu_2404_lts_with_yocto_error

This solution is specific to Ubuntu 24.0.4.

Create the following file:

```
sudo vi /etc/apparmor.d/bitbake
```

Add the following to the file:

```
abi <abi/4.0>,
include <tunables/global>
profile bitbake /**/bitbake flags=(unconfirmed) {
userns,
}
```

Then run:

```
sudo apparmor_parser -r /etc/apparmor.d/bitbake
```
