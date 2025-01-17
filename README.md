# miniature-chainsaw
miniature-chainsaw is a very simple script which integrates NetworkManager
dispatcher service with FreeIPA to perform dynaminc DNS updates.

FreeIPA out of the box supports dyunamic DNS updates. However, it is up
to the administrator to provide the update scripts.

I was surprised to find there are not a lot of pre-baked scripts out
there - perhaps I'm not looking in the right places! In any case, I
wanted something reasonably simple, yet robust enough to not break
things.

## Prerequisites
You need to join your device to the FreeIPA domain first, as the script
assumes that the `ipa` command exists and is functional.

`nsupdate` must be installed. On Debian Bookworm, you can find it in the
`bind9-dnsutils` package. On RHEL 9, you'll find it in the `bind-utils` package.

## Installation
Open a shell in your local copy of this repo
```shell
sudo cp script/99-update-dns /etc/NetworkManager/dispatcher.d/99-update-dns
sudo chmod +x /etc/NetworkManager/dispatcher.d/99-update-dns
```
