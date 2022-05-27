---
layout: default
---

## Netbeans te git clone bug fix işlemi - 30.01.2022

Bu sorunu PEM key generation seçeneği ile çözebiliyoruz.
Önce localde RSA ssh key generate ediyoruz;
ssh-keygen -t rsa -b 2048 -m PEM -C "email@hostname.com" (rsa key generate eder)

Sonra pulic key i, git bash console dan clipboard a alıyoruz;

cat ~/.ssh/id_rsa.pub | clip (public rsa ssh key i clippboard a atar)

eval $(ssh-agent -s) (ssh agenti baslatir)

Sonra gitlab repository deki profile ayarlarındaki SSH sekmesinden, clipboarddaki public SSH key i “Key” textbox ının içine focuslanıp, paste yaptıktan sonra “Add key” butonu ile ekliyoruz.

Sonra client pc de CLI dan connection testi yapıyoruz;
ssh -T git@xxx.com.tr (repository connection test eder)

Sorun yoksa Netbeans de, Team/git/clone… şeklinde new repository clone yapabiliriz;

Kaynaklar:

•	[https://docs.gitlab.com/ee/ssh/#troubleshooting](https://docs.gitlab.com/ee/ssh/#troubleshooting\)


[Ana sayfa](./)
