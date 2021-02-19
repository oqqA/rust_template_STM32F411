### Info

This is the template for projects on STM32F411 board

3 ways to upload firmware:

- DFU mode (recommend)
- ST-Link
- UART

### Dependencies
- [Rust compiler](https://www.rust-lang.org/tools/install)

 > for Windows users need [Microsoft C++ Build Tools](https://visualstudio.microsoft.com/ru/thank-you-downloading-visual-studio/?sku=BuildTools)


<details>
    <summary>[spoiler] DFU mode</summary>

- [dfu-util](https://sourceforge.net/projects/dfu-util/)
</details>

<details>
  <summary>[spoiler] ST-Link</summary>

  - [arm-none-eabi-gdb](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads)

  - [OpenOCD](https://xpack.github.io/openocd/install/)
  - [ST-LINK USB driver](https://www.st.com/en/development-tools/stsw-link009.html)

  - And run command:
    ```console
    > python3 scripts/first_start.py
    ```
</details>
<details>
  <summary>[spoiler] UART</summary>

<>todo
</details>

### Instruction (build and upload)

<details>
  <summary>[spoiler] DFU mode</summary>

0. Hold the button BOOT0
1. Connect STM32F411 to PC
2. Release the button BOOT0
3. Run command:
``` console
> python3 scripts/run.py
```
</details>

<details>
  <summary>[spoiler] ST-Link</summary>

0. Insert ST-LINK to PC USB and connect on STM32F411
1. Run command on 1-st terminal
``` console
> openocd -f openocd.cfg
```
2. Run command on 2-nd terminal
``` console
> cargo run --release
```
</details>

<details>
  <summary>[spoiler] UART</summary>
<>todo
</details>

### Detals
based on: https://github.com/rust-embedded/cortex-m-quickstart

examples: https://github.com/stm32-rs/stm32f4xx-hal/tree/master/examples

book: https://rust-embedded.github.io/book