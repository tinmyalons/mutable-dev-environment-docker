# Mutable Instruments dev environment for building hex and wav on Github Codespaces (VS Code Remote Container)

This environment realizes coding and building hex and wav file at everywhere using web browser and cloud service.

## Instruction

1. Fork this repo to your account. Then edit .devcontainer/devcontainer.json USER_GITHUB_URL if using your forked eurorack repo.

    For example,

    change comment out lines from

    ``` json
        // Use 'postCreateCommand' to run commands after the container is created.
        "postCreateCommand": "./.devcontainer/1_clone-code.sh",
        // Comment out and edit to clone your github repository instead.
        // "postCreateCommand": "USER_GITHUB_URL=https://github.com/your-account-name/eurorack.git && ./.devcontainer/1_clone-code.sh $USER_GITHUB_URL",

        "containerEnv": {
            // Comment out and edit to clone your github repository instead.
            // "USER_GITHUB_URL": "https://github.com/your-account-name/eurorack.git"
        }
    ```

    to

    ``` json
        // Use 'postCreateCommand' to run commands after the container is created.
        // "postCreateCommand": "./.devcontainer/1_clone-code.sh",
        // Comment out and edit to clone your github repository instead.
        "postCreateCommand": "USER_GITHUB_URL=https://github.com/your-account-name/eurorack.git && ./.devcontainer/1_clone-code.sh $USER_GITHUB_URL",

        "containerEnv": {
            // Comment out and edit to clone your github repository instead.
            "USER_GITHUB_URL": "https://github.com/your-account-name/eurorack.git"
        }
    ```

    and edit above "your-account-name".

2. Create Github Codespaces. (Or open mutable-dev-environment folder using VS Code in your local machine. Then reopen using Remote container.)

3. In the TERMINAL, execute module's build command.

For example,

```
make -f marbles/bootloader/makefile hex
make -f marbles/makefile
make -f marbles/makefile wav
```

then, marbles.hex and marbles.wav file is generated in the eurorack-modules/build/marbles folder.

And you can download the files.

## notes

The concept of adopting remote container is compatibility of using vagrant environment.

So username is the same as vagrant environment.

But mount folder name is "/workspaces/mutable-dev-environment" instead of "/vagrant" because of supporting Github Codespaces.

## limitation

This environment doesn't support writing firmware to device.

To update firmware, please use playing wav file.

To first write firmware to DIY module to the empty MCU, please use firmware writing tool (openocd etc) in the host computer.

Currently this environment with using local docker host with VS code remote container doesn't support arm64 local machine.
