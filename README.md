# Ansible-Spigot #

Ansible-Spigot is an ansible-playbook for deploying a Minecraft Server. More specifically one with plugins.
In this case Spigot. With this playbook you can say which version of spigot you want to run (anything
that's supported in the Spigot build_tools, a list of which can be found: [here][spigot_build_tools]).
Since build_tools is being used you'll need to download it, and make sure you've setup the prerequistes.

Once that's done you should be good to go!

For a little help around the place:
`roles/spigot/files/plugins/` - will be your plugins folder (yes this includes configs)! that will synchronize
everytime you run this deploy script. I.E. all plugins/plugin configs should go here.
`roles/spigot/vars/sekrits.yml` - This contains the environment variables you want to pass onto minecraft.
Right now the only thing that's passed is "ENIVORNMENT", with the value "PRODUCTION" (which has no effect).
I recommend if you are going to use Env vars in this file you run it through [ansible_vault][ansible_vault].
Otherwise if you try to push this to a git repo, your secrets will be there. Oh no :gasp:. Seriously though,
please run it through ansible's vault if you start throwing some secrets in there.
`roles/spigot/defaults/main.yml` - This is where you'll want to point to your local build_tools jar location,
by default it tries to find one at: `~/build_tools.jar`, but you probably have it in a different spot.

Happy mining!

[spigot_build_tools]: https://www.spigotmc.org/wiki/buildtools/
[ansible_vault]: http://docs.ansible.com/ansible/playbooks_vault.html
