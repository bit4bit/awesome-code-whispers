# GO

## [golang/dep/cmd/dep/main.go]https://github.com/golang/dep/blob/87f309484f0da00d4559dbe0ae5698f589f9a0d0/cmd/dep/main.go#L93

tags: go,preinit

~~~go
// A Config specifies a full configuration for a dep execution.
type Config struct {
	WorkingDir     string    // Where to execute
	Args           []string  // Command-line arguments, starting with the program name.
	Env            []string  // Environment variables
	Stdout, Stderr io.Writer // Log output
}

// Run executes a configuration and returns an exit code.
func (c *Config) Run() int {
	commands := commandList()
  ...
~~~
