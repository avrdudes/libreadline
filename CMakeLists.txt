#
# CMakeLists.txt
# Copyright (C) 2023 Marius Greuel
#

cmake_minimum_required(VERSION 3.12)
project(libreadline)

add_library(libreadline STATIC
    src/bind.c
    src/bind.c
    src/display.c
    src/histfile.c
    src/isearch.c
    src/mbutil.c
    src/readline.c
    src/shell.c
    src/tilde.c
    src/vi_mode.c
    src/callback.c
    src/history.c
    src/keymaps.c
    src/misc.c
    src/rltty.c
    src/signals.c
    src/undo.c
    src/xmalloc.c
    src/compat.c
    src/funmap.c
    src/histsearch.c
    src/kill.c
    src/nls.c
    src/savestring.c
    src/terminal.c
    src/util.c
    src/complete.c
    src/histexpand.c
    src/input.c
    src/macro.c
    src/parens.c
    src/search.c
    src/text.c
    )

target_compile_definitions(libreadline PRIVATE
    HAVE_CONFIG_H=1
    READLINE_STATIC=1
    )

if(MSVC)
    target_compile_definitions(libreadline PRIVATE _CRT_NONSTDC_NO_WARNINGS=1 _CRT_SECURE_NO_WARNINGS=1)
    target_include_directories(libreadline PUBLIC src/msvc)
endif()
