# systemd support files

copy the template and target to `systemd` directory and reload the daemon

    sudo cp tacacs@.service tacacs.target /etc/systemd/system/
    sudo systemctl daemon-reload

copy the settings to the default directory

    sudo cp tacacs.default tacacs.target /etc/default/tacacs-master

edit the `/etc/default/tacacs-master` file to match requirements and start the service instance

    sudo systemctl start tacacs@master

if you wish to start the instance at every boot issue the enable command

    sudo systemctl enable tacacs@master

if you have many instances the can be started/stopped/reloaded all at once using the `tacacs.target`

    sudo systemctl stop tacacs.target
    sudo systemctl reload tacacs.target

