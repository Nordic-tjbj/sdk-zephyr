# Copyright (c) 2018-2021 Nordic Semiconductor ASA
#
# SPDX-License-Identifier: Apache-2.0
#

cmake_minimum_required(VERSION 3.20.0)

if("${BOARD}" STREQUAL "nrf5340dk_nrf5340_cpunet")
	message(INFO " ${BOARD} compile as slave in this sample")
else()
	message(FATAL_ERROR "${BOARD} is not supported for this sample")
endif()

find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})
project(ipc_service_remote)

target_sources(app PRIVATE src/main.c)
