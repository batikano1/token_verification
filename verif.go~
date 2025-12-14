// Package example a example plugin.
package token_verification

import (
	"context"
	"net/http"
)

// Config the plugin configuration.
type Config struct {}

// CreateConfig creates the default plugin configuration.
func CreateConfig() *Config {
	return &Config()
}

// Example a plugin.
type Token struct {
	next     http.Handler
	name     string
}

// New created a new plugin.
func New(ctx context.Context, next http.Handler, config *Config, name string) (http.Handler, error) {
	return &Token{
		next: next,
		name: name,
	}, nil
}

func (t *Token) ServeHTTP(rw http.ResponseWriter, req *http.Request) {
	rw.Write([]byte("Hello World\n"))
}
