feat: Add S32K342 App0 application (bootloader compatible)

- Linked at 0x0044C000 (App0 slot, matches bootloader APP0_BASE)
- Initialises clock, pin mux, LPUART2, PIT from scratch after BL jump
- PIT channel 0 fires every 1s, prints heartbeat over LPUART2 (115200)
- Direct STAT register UART polling, same as bootloader (no RTD TX API)
- Re-enables global interrupts after init (BL disables before App_Jump)
