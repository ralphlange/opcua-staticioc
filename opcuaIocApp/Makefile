TOP=..
include $(TOP)/configure/CONFIG
#----------------------------------------
#  ADD MACRO DEFINITIONS AFTER THIS LINE
#=============================

STATIC_BUILD = YES

#=============================
# Build the IOC application


# Uncomment the following lines for *building* the ioc (needs the client SDK)
PROD_IOC = opcuaIoc
DBD += opcuaIoc.dbd

# Uncomment the following lines for *installing* the distributed ioc binary
#SCRIPTS_IOC = opcuaIoc
#DBD_INSTALLS += ../opcuaIoc.dbd


# opcuaIoc.dbd will be made up from these files:
opcuaIoc_DBD += base.dbd

ifdef BASE_7_0
opcuaIoc_DBD += PVAServerRegister.dbd
opcuaIoc_DBD += qsrv.dbd
opcuaIoc_LIBS += qsrv
opcuaIoc_LIBS += $(EPICS_BASE_PVA_CORE_LIBS)
endif

# Include dbd files from all support applications:
opcuaIoc_DBD += opcua.dbd

# Add all the support libraries needed by this IOC
opcuaIoc_LIBS += opcua

# opcuaIoc_registerRecordDeviceDriver.cpp derives from opcuaIoc.dbd
opcuaIoc_SRCS += opcuaIoc_registerRecordDeviceDriver.cpp
opcuaIoc_SRCS += opcuaIocMain.cpp

# Finally link to the EPICS Base libraries
opcuaIoc_LIBS += $(EPICS_BASE_IOC_LIBS)

#===========================

include $(TOP)/configure/RULES
#----------------------------------------
#  ADD RULES AFTER THIS LINE
	
