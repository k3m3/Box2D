set(BOX2D_ROPE_HEADERS
	Rope/b2Rope.h
)
set(BOX2D_GENERAL_HEADERS
	Box2D.h
)
set(BOX2D_COMMON_SOURCES
	Common/b2BlockAllocator.cpp
	Common/b2Draw.cpp
	Common/b2Math.cpp
	Common/b2Settings.cpp
	Common/b2StackAllocator.cpp
	Common/b2Timer.cpp
)
set(BOX2D_COMMON_HEADERS
	Common/b2BlockAllocator.h
	Common/b2Draw.h
	Common/b2GrowableStack.h
	Common/b2Math.h
	Common/b2Settings.h
	Common/b2StackAllocator.h
	Common/b2Timer.h
)
set(BOX2D_COLLISION_SOURCES
	Collision/b2BroadPhase.cpp
	Collision/b2CollideCircle.cpp
	Collision/b2CollideEdge.cpp
	Collision/b2CollidePolygon.cpp
	Collision/b2Collision.cpp
	Collision/b2Distance.cpp
	Collision/b2DynamicTree.cpp
	Collision/b2TimeOfImpact.cpp
)
set(BOX2D_COLLISION_HEADERS
	Collision/b2BroadPhase.h
	Collision/b2Collision.h
	Collision/b2Distance.h
	Collision/b2DynamicTree.h
	Collision/b2TimeOfImpact.h
)
set(BOX2D_SHAPE_SOURCES
	Collision/Shapes/b2CircleShape.cpp
	Collision/Shapes/b2EdgeShape.cpp
	Collision/Shapes/b2ChainShape.cpp
	Collision/Shapes/b2PolygonShape.cpp
)
set(BOX2D_SHAPE_HEADERS
	Collision/Shapes/b2CircleShape.h
	Collision/Shapes/b2EdgeShape.h
	Collision/Shapes/b2ChainShape.h
	Collision/Shapes/b2PolygonShape.h
	Collision/Shapes/b2Shape.h
)
set(BOX2D_DYNAMICS_SOURCES
	Dynamics/b2Body.cpp
	Dynamics/b2ContactManager.cpp
	Dynamics/b2Fixture.cpp
	Dynamics/b2Island.cpp
	Dynamics/b2World.cpp
	Dynamics/b2WorldCallbacks.cpp
)
set(BOX2D_DYNAMICS_HEADERS
	Dynamics/b2Body.h
	Dynamics/b2ContactManager.h
	Dynamics/b2Fixture.h
	Dynamics/b2Island.h
	Dynamics/b2TimeStep.h
	Dynamics/b2World.h
	Dynamics/b2WorldCallbacks.h
)
set(BOX2D_CONTACTS_SOURCES
	Dynamics/Contacts/b2CircleContact.cpp
	Dynamics/Contacts/b2Contact.cpp
	Dynamics/Contacts/b2ContactSolver.cpp
	Dynamics/Contacts/b2PolygonAndCircleContact.cpp
	Dynamics/Contacts/b2EdgeAndCircleContact.cpp
	Dynamics/Contacts/b2EdgeAndPolygonContact.cpp
	Dynamics/Contacts/b2ChainAndCircleContact.cpp
	Dynamics/Contacts/b2ChainAndPolygonContact.cpp
	Dynamics/Contacts/b2PolygonContact.cpp
)
set(BOX2D_CONTACTS_HEADERS
	Dynamics/Contacts/b2CircleContact.h
	Dynamics/Contacts/b2Contact.h
	Dynamics/Contacts/b2ContactSolver.h
	Dynamics/Contacts/b2PolygonAndCircleContact.h
	Dynamics/Contacts/b2EdgeAndCircleContact.h
	Dynamics/Contacts/b2EdgeAndPolygonContact.h
	Dynamics/Contacts/b2ChainAndCircleContact.h
	Dynamics/Contacts/b2ChainAndPolygonContact.h
	Dynamics/Contacts/b2PolygonContact.h
)
set(BOX2D_JOINTS_SOURCES
	Dynamics/Joints/b2DistanceJoint.cpp
	Dynamics/Joints/b2FrictionJoint.cpp
	Dynamics/Joints/b2GearJoint.cpp
	Dynamics/Joints/b2Joint.cpp
	Dynamics/Joints/b2MotorJoint.cpp
	Dynamics/Joints/b2MouseJoint.cpp
	Dynamics/Joints/b2PrismaticJoint.cpp
	Dynamics/Joints/b2PulleyJoint.cpp
	Dynamics/Joints/b2RevoluteJoint.cpp
	Dynamics/Joints/b2RopeJoint.cpp
	Dynamics/Joints/b2WeldJoint.cpp
	Dynamics/Joints/b2WheelJoint.cpp
)
set(BOX2D_JOINTS_HEADERS
	Dynamics/Joints/b2DistanceJoint.h
	Dynamics/Joints/b2FrictionJoint.h
	Dynamics/Joints/b2GearJoint.h
	Dynamics/Joints/b2Joint.h
	Dynamics/Joints/b2MotorJoint.h
	Dynamics/Joints/b2MouseJoint.h
	Dynamics/Joints/b2PrismaticJoint.h
	Dynamics/Joints/b2PulleyJoint.h
	Dynamics/Joints/b2RevoluteJoint.h
	Dynamics/Joints/b2RopeJoint.h
	Dynamics/Joints/b2WeldJoint.h
	Dynamics/Joints/b2WheelJoint.h
)
set(BOX2D_ROPE_SOURCES
	Rope/b2Rope.cpp
)
include_directories( ../ )

if(BOX2D_BUILD_SHARED)
	add_library(Box2D_shared SHARED
		${BOX2D_GENERAL_HEADERS}
		${BOX2D_JOINTS_SOURCES}
		${BOX2D_JOINTS_HEADERS}
		${BOX2D_CONTACTS_SOURCES}
		${BOX2D_CONTACTS_HEADERS}
		${BOX2D_DYNAMICS_SOURCES}
		${BOX2D_DYNAMICS_HEADERS}
		${BOX2D_COMMON_SOURCES}
		${BOX2D_COMMON_HEADERS}
		${BOX2D_SHAPE_SOURCES}
		${BOX2D_SHAPE_HEADERS}
		${BOX2D_COLLISION_SOURCES}
		${BOX2D_COLLISION_HEADERS}
		${BOX2D_ROPE_SOURCES}
		${BOX2D_ROPE_HEADERS}
	)
	set_target_properties(Box2D_shared PROPERTIES
		OUTPUT_NAME "Box2D"
		CLEAN_DIRECT_OUTPUT 1
		VERSION ${BOX2D_VERSION}
	)
endif()

if(BOX2D_BUILD_STATIC)
	add_library(Box2D STATIC
		${BOX2D_GENERAL_HEADERS}
		${BOX2D_JOINTS_SOURCES}
		${BOX2D_JOINTS_HEADERS}
		${BOX2D_CONTACTS_SOURCES}
		${BOX2D_CONTACTS_HEADERS}
		${BOX2D_DYNAMICS_SOURCES}
		${BOX2D_DYNAMICS_HEADERS}
		${BOX2D_COMMON_SOURCES}
		${BOX2D_COMMON_HEADERS}
		${BOX2D_SHAPE_SOURCES}
		${BOX2D_SHAPE_HEADERS}
		${BOX2D_COLLISION_SOURCES}
		${BOX2D_COLLISION_HEADERS}
		${BOX2D_ROPE_SOURCES}
		${BOX2D_ROPE_HEADERS}
	)
	set_target_properties(Box2D PROPERTIES
		CLEAN_DIRECT_OUTPUT 1
		VERSION ${BOX2D_VERSION}
	)
endif()

# These are used to create visual studio folders.
source_group(Collision FILES ${BOX2D_COLLISION_SOURCES} ${BOX2D_COLLISION_HEADERS})
source_group(Collision\\Shapes FILES ${BOX2D_SHAPE_SOURCES} ${BOX2D_SHAPE_HEADERS})
source_group(Common FILES ${BOX2D_COMMON_SOURCES} ${BOX2D_COMMON_HEADERS})
source_group(Dynamics FILES ${BOX2D_DYNAMICS_SOURCES} ${BOX2D_DYNAMICS_HEADERS})
source_group(Dynamics\\Contacts FILES ${BOX2D_CONTACTS_SOURCES} ${BOX2D_CONTACTS_HEADERS})
source_group(Dynamics\\Joints FILES ${BOX2D_JOINTS_SOURCES} ${BOX2D_JOINTS_HEADERS})
source_group(Include FILES ${BOX2D_GENERAL_HEADERS})
source_group(Rope FILES ${BOX2D_ROPE_SOURCES} ${BOX2D_ROPE_HEADERS})

if(BOX2D_INSTALL)
	# install headers
	install(FILES ${BOX2D_GENERAL_HEADERS} DESTINATION include/Box2D)
	install(FILES ${BOX2D_COLLISION_HEADERS} DESTINATION include/Box2D/Collision)
	install(FILES ${BOX2D_SHAPE_HEADERS} DESTINATION include/Box2D/Collision/Shapes)
	install(FILES ${BOX2D_COMMON_HEADERS} DESTINATION include/Box2D/Common)
	install(FILES ${BOX2D_DYNAMICS_HEADERS} DESTINATION include/Box2D/Dynamics)
	install(FILES ${BOX2D_CONTACTS_HEADERS} DESTINATION include/Box2D/Dynamics/Contacts)
	install(FILES ${BOX2D_JOINTS_HEADERS} DESTINATION include/Box2D/Dynamics/Joints)
	install(FILES ${BOX2D_ROPE_HEADERS} DESTINATION include/Box2D/Rope)

	# install libraries
	if(BOX2D_BUILD_SHARED)
		install(TARGETS Box2D_shared EXPORT Box2D-targets 
                  LIBRARY DESTINATION ${LIB_INSTALL_DIR}
                  ARCHIVE DESTINATION ${LIB_INSTALL_DIR}
                  RUNTIME DESTINATION bin)
	endif()
	if(BOX2D_BUILD_STATIC)
		install(TARGETS Box2D EXPORT Box2D-targets DESTINATION ${LIB_INSTALL_DIR})
	endif()

	# install build system hooks for third-party apps
	install(EXPORT Box2D-targets DESTINATION ${LIB_INSTALL_DIR}/Box2D)

        set (BOX2D_INCLUDE_DIR ${CMAKE_INSTALL_PREFIX}/include)
        set (BOX2D_INCLUDE_DIRS ${BOX2D_INCLUDE_DIR} )
        set (BOX2D_LIBRARY_DIRS ${CMAKE_INSTALL_PREFIX}/${LIB_INSTALL_DIR})
        set (BOX2D_LIBRARY Box2D)
        set (BOX2D_LIBRARIES ${BOX2D_LIBRARY})
        set (BOX2D_USE_FILE ${CMAKE_INSTALL_PREFIX}/${LIB_INSTALL_DIR}/cmake/Box2D/UseBox2D.cmake)
        configure_file(Box2DConfig.cmake.in ${CMAKE_CURRENT_BINARY_DIR}/Box2DConfig.cmake @ONLY ESCAPE_QUOTES)
        install(FILES ${CMAKE_CURRENT_BINARY_DIR}/Box2DConfig.cmake UseBox2D.cmake DESTINATION ${LIB_INSTALL_DIR}/cmake/Box2D)
endif(BOX2D_INSTALL)
