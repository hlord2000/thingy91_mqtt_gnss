cmake_minimum_required(VERSION 3.20.0)
find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})

project(nrf9160_mqtt_simple)

# NORDIC SDK APP START

# includes
# zephyr_include_directories(.)
zephyr_include_directories(mqtt gnss datatypes pmic) # can also do this with multiple calls

# sources
target_sources(app PRIVATE src/main.c
            src/datatypes/datatypes.c
            src/mqtt/mqtt_connection.c
            src/gnss/gnss.c
            src/pmic/pmic.c)
# NORDIC SDK APP END