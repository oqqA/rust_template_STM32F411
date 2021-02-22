### Info

This is the template for projects on STM32F411 board

### Dependencies
- [Rust compiler](https://www.rust-lang.org/tools/install)

 > for Windows users need [Microsoft C++ Build Tools](https://visualstudio.microsoft.com/ru/thank-you-downloading-visual-studio/?sku=BuildTools)

  - [arm-none-eabi-gdb](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads)

  - [OpenOCD](https://xpack.github.io/openocd/install/)
  - [ST-LINK USB driver](https://www.st.com/en/development-tools/stsw-link009.html)

  - And run command:
    ```console
    > python3 scripts/first_start.py
    ```

### Instruction (build and upload)

1. Insert ST-LINK to PC USB and connect on STM32F411
2. Run command on 1-st terminal
``` console
> openocd -f openocd.cfg
```
2. Run command on 2-nd terminal
``` console
> cargo run --release
```

### Detals
based on: https://github.com/rust-embedded/cortex-m-quickstart

examples: https://github.com/stm32-rs/stm32f4xx-hal/tree/master/examples
or https://github.com/stm32-rs/stm32f4xx-hal/tree/cargo-bloat/examples

hal docs: https://docs.rs/stm32f4xx-hal/0.8.3/stm32f4xx_hal/

book: https://rust-embedded.github.io/book