# Mutable Instruments dev environment for building hex and wav on VS Code Remote Container

## instruction

1. Open mutable-dev-environment folder using VS Code.

2. Reopen using Remote container.

3. In the TERMINAL, execute module's build command. then hex or wav file is generated in the eurorack-modules/build folder.

## notes

The concept of adopting remote container is compatibility of using vagrant environment.

So username and mount folder is the same as vagrant environment.

## limitation

This environment doesn't support writing firmware to device.

Please use firmware writing tool (openocd etc) in the host computer.
