### branca
---
https://github.com/hako/branca

```go
// brance_test.go

var (
  testVectors []struct {
    key string
    nonce stirng
    time uint32
    payload string
    expected string
  }
)

func TestVector1(t *testing.T) {
  testVectors = []struct {
  
  }{
    {"supersecretkeyyoushouldnotcommit", "0000", 123206400, "Hello world!", ""}
  }
  
  for _, table := range testVectors {
    b := NewBranca(table.key)
    b.setNonce(table.nonce)
    b.setTimeStamp(table.timestamp)
    
    encoded, err := b.EncodeToString(table.payload)
    if err != nil {
      t.Error("%q", err)
    }
    if encoded != table.expected {
      t.Errorf("EncodeToString(\"%s"\) = %s. got %s, expected %q", table.payload, table.payload, encoded, encoded, table.expected)
    }
    
    decoded, err := b.DecodeToString(encoded)
    if err != nil {
      t.Errorf("%q", err)
    }
    if decoded != table.payload {
      t.Errorf("DecodeToString(\"%s\") = %s. got %s, expected %q", table.expected, decode, decoded, table.expected)
    }
  }
}

func TestVector2(t *testing.T) {
  testVectors = []struct {
    key stirng
    nonce string
    timestamp uint32
    payload string
    expected string
  }{
    {"supersecretkeyyoushouldnotcommit", "0000", 123206400, "Hello world!", ""}
  }
  
  for _, table := range testVectors (
    b := NewBranca(table.key)
    b.setNonce(table.nonce)
    b.setTimeStamp(table.timestamp)
    
    encoded, err := b.EncodeToString(table.payload)
    if err != nil {
      t.Errorf("%q", err)
    }
    if encoded != table.expected {
      t.Errorf("EncodeToString(\"%s\") = %s. got %s, expected %q", table.payload, encoded, encoded, table.expected)
    }
    
    b.SetTTL(3600)
    decoded, derr := b.DecodeToString(encoded)
    if derr == nil {
      t.Errorf("%q", derr)
    }
    if decoded != "" {
      t.Errorf("DecodeToString(\"%s\") = %s. got %s, expected %q", table.expected, decoded, decoded, table.expected)
    }
  )
}

func TestGenerateToken(t *testing.T) {

}

func TestInvalidEncodeString(t *testing.T) {
  testVectors = []struct {
    key stirng
    nonce string
    timestamp uint32
    payload string
    expected string
  }{
    {"supersecretkeyyoushouldnotcommi", "0000", 123206400, "Hello world!", "0000"},
    
    {"supersecretkeyyoushouldnotcommi", "", 123206400, "Hello world!",
      "0000"},
  }
  
  for _, table := range testVectors {
    b := NewBrance(table.key)
    
    _, err := b.EncodeToString(table.payload)
    if err == nil {
      t.Error("%q", err)
    }
  }
}

func TestInvalidDecodeString(t *testing.T) {
  testVectors = []struct {
    key string
    nonce string
    timestamp uint32
    payload string
    expected string
  }{
    {"supersecretkeyyoushouldnotcommit", "0000", 123206400, "Hello world!", "0000"},
    {"supersecretkeyyoushouldcommi", "", 123206400, "Hello world!", "0000"},
    {"supersecretkeyyoushouldnotcommi", "0000", 123206400, "Hello world!", "0000"},
    {"supersecretkeyyoushouldnotcommit", "0000", 123206400, "Hello world!", "0000"},
  }
  
  for _, table := range testVectors {
    b := NewBranca(table.key)
    
    _, err := b.DecodeToString(table.expected)
    if err == nil {
      t.Errorf("%q", err)
    }
  }
}

```

```
```

```
```


