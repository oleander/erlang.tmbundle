README
======

This bundle requires setting up of two new TextMate [static environment variables][3] which are - `ERLANG_LIB` and `ERL_PATH`. 

In order to find the correct values for `ERLANG_LIB` and `ERL_PATH` launch `erl` in you terminal and type `code:lib_dir().` and `string:concat(code:root_dir(), "/bin").`

Set the value of `ERLANG_LIB` to the result of `code:lib_dir().` and value of `ERL_PATH` to the result of `string:concat(code:root_dir(), "/bin").`

For example,

    Erlang R14A (erts-5.8) [source] [64-bit] [smp:2:2] [rq:2] [async-threads:0] [hipe] [kernel-poll:false]
    
    Eshell V5.8  (abort with ^G)
    1> code:lib_dir().
    "/opt/local/lib/erlang/lib"
    2> string:concat(code:root_dir(), "/bin").
    "/opt/local/lib/erlang/bin"
    3>

In this case `ERLANG_LIB` is set to `/opt/local/lib/erlang/lib` and `ERL_PATH` to `/opt/local/lib/erlang/bin`

TODO
----

*   Add ebin's in `TM_PROJECT_DIRECTORY` to Erlang's code_path for autocompletion
*   In `Support/completion/src/tm_menu.erl`, find a better way to get the path to `tm_dialog`

CREDITS
-------

*   Most of the logic for Erlang code completion is from Alain O'Dea's [erlang code completion][1] repo 
*   eflymake from Kevin Smith's [hl-emacs][2] repo 

[1]: http://github.com/AlainODea/erlang_code_completion
[2]: http://github.com/kevsmith/hl-emacs
[3]: http://manual.macromates.com/en/environment_variables.html
