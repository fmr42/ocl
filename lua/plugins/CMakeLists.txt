set( RTT_DEFINITIONS "${OROCOS-RTT_DEFINITIONS}" )

orocos_plugin( rttlua-plugin lua_plugin.cpp ../rtt.cpp )
target_link_libraries(rttlua-plugin ${LUAJIT_LIBRARY})

# TLSF version
if(BUILD_LUA_RTT_TLSF)
  orocos_plugin( rttlua-tlsf-plugin lua_plugin.cpp ../rtt.cpp)
  target_link_libraries(rttlua-tlsf-plugin tlsf_rtt ${LUAJIT_LIBRARY})
  set_target_properties(rttlua-tlsf-plugin PROPERTIES COMPILE_FLAGS "-DLUA_RTT_TLSF")
endif(BUILD_LUA_RTT_TLSF)

