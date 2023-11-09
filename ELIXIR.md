# ELIXIR

### [lib/nimble_pool.ex](https://github.com/dashbitco/nimble_pool/blob/c2bfbeca410a4550f0d31446bb8aded17acceb94/lib/nimble_pool.ex#L379)

tags: elixir,pattern

note: using pin operator for query map

~~~elixir
    %{requests: requests, ...} = state
    ..
    case requests do    
      %{^ref => {pid, mon_ref, :state, worker_state}} ->
        ...
      %{} ->   
        ...
    end
~~~

### [test/support/conn_case](https://github.com/adriankumpf/teslamate/blob/56a6aa3e7f3ca42f41e6e4d80ef61fcf05397b34/test/support/conn_case.ex#L50)

tags: elixir,pattern

note: using tags to enable feature

~~~elixir
    ...
    conn =
      Phoenix.ConnTest.build_conn()
      |> Plug.Conn.assign(:signed_in?, !!tags[:signed_in])
    ...
~~~
