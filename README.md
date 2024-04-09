Delete unnecessary files

    dpkg-query -W -f '${Version}\n' 'linux-image-[^g]*'|sort -u|sed -e '/^$/d' -e 's/\~[^~]*$//' -e 's/\.[^.]*$//' -e "/$(uname -r|sed 's/-generic//')/d" -e 's/.*/linux-*-&*/'|tr '\n' ' '|xargs -pr sudo apt-get remove --purge -y

Updating Firefox: 

    # atnaujina visus sarasus, pagal kuriuos atnaujinamos programos
    apt-get update
    # pats FF update
    apt-get upgrade firefox-esr

Garso ijungimas (root useriui by default neleidzia)

    gedit .bashrc
    # failo pabaigoj pridedam 2 eilutes:
    pulseaudio -D
    clear

Interneto (eth0) ijungimas

    apt-get install net-tools

