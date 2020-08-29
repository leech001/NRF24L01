# NRF24L01
HAL library for NRF24L01 on STM32

#USE
```
uint8_t nrf_data[32] = {0,};
const uint64_t pipe1 = 0xF0F0F0F0A1LL;
while (!isChipConnected());
        NRF_Init();
        setDataRate(RF24_250KBPS);
        setChannel(76);
        openWritingPipe(pipe1);
        maskIRQ(true, true, true);

        nrf_data[0] = adc >> 8;
        nrf_data[1] = adc & 0xff;
        for (uint8_t i = 0; i < 5; i++) {
            write(&nrf_data, strlen((const char *) nrf_data));
            HAL_Delay(200);
        }
```