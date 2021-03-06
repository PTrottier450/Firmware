############################################################################
#
#   Copyright (c) 2015 PX4 Development Team. All rights reserved.
#   Copyright (c) 2017 Createk Design Lab. All rights reserved.
#
# Redistribution and use in source and binary forms, with or without
# modification, are permitted provided that the following conditions
# are met:
#
# 1. Redistributions of source code must retain the above copyright
#    notice, this list of conditions and the following disclaimer.
# 2. Redistributions in binary form must reproduce the above copyright
#    notice, this list of conditions and the following disclaimer in
#    the documentation and/or other materials provided with the
#    distribution.
# 3. Neither the name PX4 nor the names of its contributors may be
#    used to endorse or promote products derived from this software
#    without specific prior written permission.
#
# THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
# "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
# LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS
# FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE
# COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT,
# INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING,
# BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS
# OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED
# AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT
# LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN
# ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
# POSSIBILITY OF SUCH DAMAGE.
#
############################################################################
include_directories(Api/core/inc Api/platform/inc)
set(SOURCES
		Api/core/src/vl53l0x_api.c
		Api/core/src/vl53l0x_api_calibration.c
		Api/core/src/vl53l0x_api_core.c
		Api/core/src/vl53l0x_api_ranging.c
		Api/core/src/vl53l0x_api_strings.c
		Api/platform/src/vl53l0x_i2c_comms.c
		Api/platform/src/vl53l0x_platform.c)
#		Api/platform/src/vl53l0x_platform_log.c)

set(HEADERS
		Api/core/inc/vl53l0x_api.h
		Api/core/inc/vl53l0x_api_calibration.h
		Api/core/inc/vl53l0x_api_core.h
		Api/core/inc/vl53l0x_api_ranging.h
		Api/core/inc/vl53l0x_api_strings.h
		Api/core/inc/vl53l0x_def.h
		Api/core/inc/vl53l0x_device.h
		Api/core/inc/vl53l0x_interrupt_threshold_settings.h
		Api/core/inc/vl53l0x_tuning.h
		Api/platform/inc/vl53l0x_i2c_platform.h
		Api/platform/inc/vl53l0x_platform.h
		Api/platform/inc/vl53l0x_platform_log.h
		Api/platform/inc/vl53l0x_types.h)

px4_add_module(
	MODULE drivers__vl53l0x
	MAIN vl53l0x
	COMPILE_FLAGS
	SRCS
        vl53l0x.cpp
		${HEADERS}
		${SOURCES}
	DEPENDS
		platforms__common
	)
# vim: set noet ft=cmake fenc=utf-8 ff=unix :
