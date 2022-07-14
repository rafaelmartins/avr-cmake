# SPDX-FileCopyrightText: 2022 Rafael G. Martins <rafael@rafaelmartins.eng.br>
# SPDX-License-Identifier: BSD-3-Clause

cmake_minimum_required(VERSION 3.12)

include(../cmake/avr.cmake)

project(avr-example C)

add_executable(avr-example
    main.c
)
avr_target_set_device(avr-example attiny25 8000000UL)
avr_target_gen_map(avr-example)
avr_target_show_size(avr-example attiny25)
avr_target_generate_hex(avr-example)
avr_target_generate_eeprom_hex(avr-example)

dwtk_init(avr_example)
