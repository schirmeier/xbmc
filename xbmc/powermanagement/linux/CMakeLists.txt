set(SOURCES LinuxPowerSyscall.cpp)

set(HEADERS FallbackPowerSyscall.h
            LinuxPowerSyscall.h)

if(DBUS_FOUND)
  list(APPEND SOURCES ConsoleUPowerSyscall.cpp
                      LogindUPowerSyscall.cpp
                      UPowerSyscall.cpp)
  list(APPEND HEADERS ConsoleUPowerSyscall.h
                      LogindUPowerSyscall.h
                      UPowerSyscall.h)
endif()

if(SOURCES)
  core_add_library(powermanagement_linux)
endif()
