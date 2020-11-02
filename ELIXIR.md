# ELIXIR

## NimblePool

### [lib/nimble_pool.ex]https://github.com/dashbitco/nimble_pool/blob/c2bfbeca410a4550f0d31446bb8aded17acceb94/lib/nimble_pool.ex#L379

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

