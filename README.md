OKEx api v3 usage :
-------------------

### 1.Downloads or updates OKEX code's dependencies, in your command line:

```
go get -u https://github.com/beaquant/go-okex-v3
```
###
```
package okexv3

import (
	"fmt"
	"github.com/okcoin-okex/open-api-v3-sdk/okex-go-sdk-api"
	"testing"
)

func TestOKExServerTime(t *testing.T) {
	serverTime, err := NewOKExClient().GetServerTime()
	if err != nil {
		t.Error(err)
	}
	fmt.Println("OKEx's server time: ", serverTime)
}

func NewOKExClient() *okex.Client {
	var config okex.Config
	config.Endpoint = "https://www.okex.com/"
	config.ApiKey = ""
	config.SecretKey = ""
	config.Passphrase = ""
	config.TimeoutSecond = 45
	config.IsPrint = true
	config.I18n = okex.ENGLISH

	client := okex.NewClient(config)
	return client
}
