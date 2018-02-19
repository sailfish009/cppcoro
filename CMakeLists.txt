cmake_minimum_required(VERSION 3.6)
project(libco)

add_compile_options("/await")

set(CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS on CACHE BOOL "option1")
set(BUILD_STATIC_LIBS on CACHE BOOL "option2")
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_LIBRARIES "${CMAKE_CXX_STANDARD_LIBRARIES} ws2_32.lib")

set(SOURCE_FILES
include/cppcoro/detail/continuation.hpp
include/cppcoro/detail/lightweight_manual_reset_event.hpp
include/cppcoro/detail/unwrap_reference.hpp
include/cppcoro/detail/when_all_awaitable.hpp
include/cppcoro/detail/win32.hpp
include/cppcoro/detail/win32_overlapped_operation.hpp
include/cppcoro/net/ip_address.hpp
include/cppcoro/net/ip_endpoint.hpp
include/cppcoro/net/ipv4_address.hpp
include/cppcoro/net/ipv4_endpoint.hpp
include/cppcoro/net/ipv6_address.hpp
include/cppcoro/net/ipv6_endpoint.hpp
include/cppcoro/async_auto_reset_event.hpp
include/cppcoro/async_generator.hpp
include/cppcoro/async_latch.hpp
include/cppcoro/async_manual_reset_event.hpp
include/cppcoro/async_mutex.hpp
include/cppcoro/broken_promise.hpp
include/cppcoro/cancellation_registration.hpp
include/cppcoro/cancellation_source.hpp
include/cppcoro/cancellation_token.hpp
include/cppcoro/config.hpp
include/cppcoro/file.hpp
include/cppcoro/file_buffering_mode.hpp
include/cppcoro/file_open_mode.hpp
include/cppcoro/file_read_operation.hpp
include/cppcoro/file_share_mode.hpp
include/cppcoro/file_write_operation.hpp
include/cppcoro/fmap.hpp
include/cppcoro/generator.hpp
include/cppcoro/io_service.hpp
include/cppcoro/on_scope_exit.hpp
include/cppcoro/operation_cancelled.hpp
include/cppcoro/read_only_file.hpp
include/cppcoro/read_write_file.hpp
include/cppcoro/readable_file.hpp
include/cppcoro/recursive_generator.hpp
include/cppcoro/resume_on.hpp
include/cppcoro/schedule_on.hpp
include/cppcoro/shared_task.hpp
include/cppcoro/single_consumer_async_auto_reset_event.hpp
include/cppcoro/single_consumer_event.hpp
include/cppcoro/sync_wait.hpp
include/cppcoro/task.hpp
include/cppcoro/when_all.hpp
include/cppcoro/when_all_ready.hpp
include/cppcoro/writable_file.hpp
include/cppcoro/write_only_file.hpp
lib/async_auto_reset_event.cpp
lib/async_manual_reset_event.cpp
lib/async_mutex.cpp
lib/cancellation_registration.cpp
lib/cancellation_source.cpp
lib/cancellation_state.cpp
lib/cancellation_state.hpp
lib/cancellation_token.cpp
lib/file.cpp
lib/file_read_operation.cpp
lib/file_write_operation.cpp
lib/io_service.cpp
lib/ip_address.cpp
lib/ip_endpoint.cpp
lib/ipv4_address.cpp
lib/ipv4_endpoint.cpp
lib/ipv6_address.cpp
lib/ipv6_endpoint.cpp
lib/lightweight_manual_reset_event.cpp
lib/read_only_file.cpp
lib/read_write_file.cpp
lib/readable_file.cpp
lib/use.cake
lib/win32.cpp
lib/writable_file.cpp
lib/write_only_file.cpp
)

include_directories(include)

add_library(libco STATIC ${SOURCE_FILES})