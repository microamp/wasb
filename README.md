# wasb

Write a Slack bot

## Quickstart

First, create a new bot user on Slack. Then, prepare a new config file for the bot.

```bash
cp config.json.template echo-config.json
```

Update the config with the bot's API token.

You can run the bot by running the following command.

```bash
go run cmd/echo/echo.go -config=echo-config.json
```

## Write your own

Your custom bot needs to implement the `WASB` interface.

```go
type WASB interface {
	ReceiveMessage() (*Msg, error)
	IsValidMessage(m *Msg) bool
	SendMessage(m *Msg) error
	TearDown() error
}
```

As a simple example, see how `Echo` implements it in [`cmd/echo/echo.go`](https://github.com/microamp/wasb/blob/master/cmd/echo/echo.go).

## License

MIT
