add_library(lib_rpl INTERFACE)

get_filename_component(src_loc "." REALPATH)

set(lib_rpl_sources
INTERFACE
    rpl/details/callable.h
    rpl/details/superset_type.h
    rpl/details/type_list.h
    rpl/after_next.h
    rpl/before_next.h
    rpl/combine.h
    rpl/combine_previous.h
    rpl/complete.h
    rpl/conditional.h
    rpl/consumer.h
    rpl/deferred.h
    rpl/distinct_until_changed.h
    rpl/event_stream.h
    rpl/fail.h
    rpl/filter.h
    rpl/flatten_latest.h
    rpl/lifetime.h
    rpl/map.h
    rpl/mappers.h
    rpl/merge.h
    rpl/never.h
    rpl/producer.h
    rpl/range.h
    rpl/rpl.h
    rpl/skip.h
    rpl/take.h
    rpl/then.h
    rpl/type_erased.h
    rpl/variable.h
)
nice_target_sources(lib_rpl ${src_loc} "${lib_rpl_sources}")

target_include_directories(lib_rpl
INTERFACE
    ${src_loc}
)

target_link_libraries(lib_rpl
INTERFACE
    external_gsl
)
