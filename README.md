# Encrypt Timeout Hook for Arch Linux

This is a custom encrypt hook for Arch Linux that includes a shutdown timeout feature. It prompts for a password to decrypt the root device, and if the user does not enter the correct passphrase within the set timeout, the system will automatically power off.

#### Installation

1. Install the encrypt-timeout-hook package from the AUR using your preferred AUR helper or manually by downloading the package and running makepkg -si.
2. Modify your Arch Linux initramfs configuration file /etc/mkinitcpio.conf to include the new hook. Add encrypt-timeout to the HOOKS array after encrypt.
    ```
    HOOKS=(base udev autodetect modconf block encrypt encrypt-timeout filesystems keyboard fsck)
    ```
3. Regenerate your initramfs by running mkinitcpio -p linux.
4. Reboot your system to activate the new hook.

#### Usage
The hook supports unlocking the root device via passphrase or keyfile. The cryptdevice and cryptkey parameters can be used to specify the device to be unlocked and the keyfile location, respectively.

Without specifying a keyfile, you will be prompted for the password at runtime. This means you must have a keyboard available to input it, and you may need the keymap hook as well to ensure that the keyboard is using the layout you expect.

#### Credits

This hook was created by Spoons and is licensed under the GPL license. Feel free to contribute to the project on GitHub and report any issues or bugs you encounter.
