README
======

This bundle requires,

1.  Setting up of two new TextMate [static environment variables][3] which are - `ERLANG_LIB` and `ERL_PATH`. 
2.  Adding host entry to your computer's local network name. 

In order to find the correct values for `ERLANG_LIB` and `ERL_PATH` launch `erl` in your terminal and type `code:lib_dir().` and `string:concat(code:root_dir(), "/bin").`

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

Next find your computer's local network name. Please click one of the following links to get more information on how to determine your computer's local network name. For,

*   [10.6][4]
*   [10.5][5]
*   [10.4][6]

Assuming your computer's local network name is `My-Computer.local`, you can add a host entry to this name by typing the following command in a terminal.

    sudo dscl localhost -create /Local/Default/Hosts/My-Computer.local IPAddress 127.0.0.1

TODO
----

*   Add ebin's in `TM_PROJECT_DIRECTORY` to Erlang's code_path for autocompletion

CREDITS
-------

*   Most of the logic for Erlang code completion is from Alain O'Dea's [erlang code completion][1] repo 
*   eflymake from Kevin Smith's [hl-emacs][2] repo 

[1]: http://github.com/AlainODea/erlang_code_completion
[2]: http://github.com/kevsmith/hl-emacs
[3]: http://manual.macromates.com/en/environment_variables.html
[4]: http://docs.info.apple.com/article.html?path=Mac/10.6/en/8597.html
[5]: http://docs.info.apple.com/article.html?path=Mac/10.5/en/8324.html
[6]: http://docs.info.apple.com/article.html?path=Mac/10.4/en/mh632.html
