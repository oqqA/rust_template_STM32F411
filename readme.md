### Info

This is the template for projects on STM32F411 board

### Dependencies
- [Rust compiler](https://www.rust-lang.org/tools/install)

 > for windows users need [Microsoft C++ Build Tools](https://visualstudio.microsoft.com/ru/thank-you-downloading-visual-studio/?sku=BuildTools) 
- [arm-none-eabi-gdb](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads)

- [OpenOCD](https://xpack.github.io/openocd/install/)
- [ST-LINK USB driver](https://www.st.com/en/development-tools/stsw-link009.html)


- Run commands:
```console
> cargo install cargo-binutils
> rustup component add llvm-tools-preview

> rustup target add thumbv7em-none-eabihf

> cargo build --release
```

### Instruction (build and load)
0. Insert ST-LINK USB and connect on STM32F411
1. Run command on 1-st terminal
``` console
> openocd -f openocd.cfg
```
2. Run command on 2-nd terminal
``` console
> cargo run --release
```

<details>
  <summary>[spoiler] Second way</summary>

    > cargo build --release
    > cargo objcopy --bin stm32f411 --target thumbv7em-none-eabihf --release -- -O binary stm32f411.bin
    > st-flash erase
    > st-flash write stm32f411.bin 0x8000000
</details>

### Detals
based on: https://github.com/rust-embedded/cortex-m-quickstart

examples: https://github.com/stm32-rs/stm32f4xx-hal/tree/master/examples

book: https://rust-embedded.github.io/book