# VirtualBox

### SSH access

Set up port forwarding (from host machine, assuming it's c 2222):

    VBoxManage modifyvm "mybox" --natpf1 "rails,tcp,,3000,,3000"
	VBoxManage modifyvm "mybox" --natpf1 "guestssh,tcp,,2222,,22"

For easy SSH access, add this to `~/.ssh/config`:

    Host mybox
      Hostname localhost
      Port     2222
      User     <username>
      ForwardX11 yes

To copy your local SSH config into the VM, run:

    rsync -av ~/.ssh mybox:


- ssh into the VM: `ssh username@mybox`
- Copy the content of your local `~/.ssh/id_rsa.pub` into `~/.ssh/authorized_keys` on VM
- Set up a bash alias in `~/.bash_profile`: `alias box=ssh -Y mybox`
- Now you can reconnect to VM with the new 'box' command
- You can now turnoff the VM and save a snapshot of this blank state