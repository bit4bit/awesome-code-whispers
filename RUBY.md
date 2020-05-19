# RUBY

## https://github.com/ruby/rake/blob/4fe73ff6b19ea1d8490b0442c75fc3a53815c4cf/lib/rake/dsl_definition.rb#L23

tags: ruby,dsl,metaprogramming

~~~ruby
    private(*FileUtils.instance_methods(false))
~~~

## https://github.com/mruby/mruby/blob/d79147fe5dc4ee8b4eff6a37df229d993cf3ce58/lib/mruby/build.rb#L22

tags: ruby,dsl,metaprogramming

~~~ruby
  class Toolchain
    class << self
      attr_accessor :toolchains
    end

    def initialize(name, &block)
      @name, @initializer = name.to_s, block
      MRuby::Toolchain.toolchains[@name] = self
    end

    def setup(conf,params={})
      conf.instance_exec(conf, params, &@initializer)
    end

    self.toolchains = {}
  end
~~~
