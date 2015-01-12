gen_rule(
    name = "gen_config",
    cmd="cd thirdparty/ctemplate-2.3;./configure;cd -",
    outs=['config.h']
)

gen_rule(
    name = "gen_htmlparser_header",
    cmd = "cd thirdparty/ctemplate-2.3/src;sh ./gen_htmlparser_header.sh;cd -",
    outs = ['src/htmlparser/htmlparser_fsm.h']
    )

cc_library(
    name = 'ctemplate',
    srcs = [
        'diff_tpl_auto_escape.cc',
        'make_tpl_varnames_h.cc',
        'per_expand_data.cc',
        'template_annotator.cc',
        'template_cache.cc',
        'template.cc',
        'template_dictionary.cc',
        'template_modifiers.cc',
        'template_namelist.cc',
        'template_pathops.cc',
        'template_string.cc',
        './base/arena.cc',
        './htmlparser/htmlparser.cc',
        './htmlparser/jsparser.cc',
        './htmlparser/statemachine.cc'
    ],
    incs = ['.', '..'],
    deps = [':gen_config', ':gen_htmlparser_header', '#pthread'],
    warning = 'no'
)
