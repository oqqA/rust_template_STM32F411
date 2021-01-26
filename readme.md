### Instruction

``` console
> openocd -f openocd.cfg
```

``` console
> cargo run --release
```

<details>
  <summary>[spoiler] Second way</summary>

    ``` console
    > cargo build --release
    > cargo objcopy --bin stm32f411 --target thumbv7em-none-eabihf --release -- -O binary stm32f411.bin
    > st-flash erase
    > st-flash write stm32f411.bin 0x8000000
    ```
    or one line command:
    ``` console
    > cargo build --release && cargo objcopy --bin stm32f411 --target thumbv7em-none-eabihf --release -- -O binary stm32f411.bin && st-flash write stm32f411.bin 0x8000000
    ```
</details>

