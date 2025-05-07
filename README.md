# Sovol SV06 Klipper

Firmware e configuracoes do klipper para a SV06

- INPUT SHAPER ACELEROMETRO ADXL345
  https://www.klipper3d.org/Measuring_Resonances.html
  https://www.klipper3d.org/RPi_microcontroller.html
  Referencia:
  https://www.youtube.com/watch?v=9S7uGbbBfx0

Comando para o printer.cfg:
[mcu host]
serial: /tmp/klipper_host_mcu

[adxl345] #BTT PI
cs_pin: host:gpio67
spi_bus: spidev0.0
axes_map: x,y,z

[resonance_tester]
accel_chip: adxl345
accel_per_hz: 70
probe_points:
    100, 100, 20

[input_shaper]
#shaper_freq_x: 55.8
#shaper_type_x: mzv

#shaper_freq_y: 41.2
#shaper_type_y: mzv
#shaper_type: ei

![Imagem do WhatsApp de 2025-05-07 à(s) 17 02 28_a810db7e](https://github.com/user-attachments/assets/df9837db-1e70-4014-959b-bb5d767ce461)


- INPUT SHAPER MANUAL
  https://www.klipper3d.org/Resonance_Compensation.html
  
Medicoes feitas com 

100mm/s, 6 oscilacoes e 12mm de extensao no X 

100mm/s, 5 oscilacoes e 10,5mm de extensao no Y

![Imagem do WhatsApp de 2024-04-24 à(s) 21 40 01_a7f280b8](https://github.com/ofelipevilela/sovol-sv06-klipper/assets/165967059/28841caa-f47e-4ed6-9ea0-455654381047)
![Imagem do WhatsApp de 2024-04-24 à(s) 21 40 02_92d90285](https://github.com/ofelipevilela/sovol-sv06-klipper/assets/165967059/21bd08fc-efa6-4a7a-b943-86a0179033ef)

- Resultados :
  
input_shaper x = 46  # aumentei um pouco da foto pois ainda havia ressonancia
 
input_shaper y = 42,5

![Imagem do WhatsApp de 2024-04-24 à(s) 21 40 03_30a27b59](https://github.com/ofelipevilela/sovol-sv06-klipper/assets/165967059/d3354e6a-246b-43ec-b855-843025f4853a)
![Imagem do WhatsApp de 2024-04-24 à(s) 21 40 04_3f2d36d4](https://github.com/ofelipevilela/sovol-sv06-klipper/assets/165967059/8d1763f4-8253-4fc5-b771-01d35b454547)



- PRESSURE ADVENCE

  Altura com melhor resultado = 12,5mm

  Fator multiplicativo = 0,005

  Resultado: pressure_advence = 0,0622
  
![Imagem do WhatsApp de 2024-04-24 à(s) 21 40 04_66743071](https://github.com/ofelipevilela/sovol-sv06-klipper/assets/165967059/69383014-c6ff-424f-99fc-9e5edaa75f19)
