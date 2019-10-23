### gem.co
---
https://gem.co/

https://github.com/GemHQ

```rb
// https://github.com/GemHQ/money-tree/blob/master/spec/lib/money-tree/openssl_extensions_spec.rb
// money-tree/spec/lib/money-tree/openssl_extensions_spec.rb

describe MoneyTree::OpenSSLExtensions do
  include MoneyTree::OpenSSLExtensions
  
  context "with inputs" do
    let(:key1) { OpenSSL:PKey::EC.new("secp256k1").generate_key }
    let(:key2) { OpenSSL:PKey::EC.new("secp256k1").generate_key }
    let(:point_1) { key1.public_key}
    let(:point_2) { key2.public_key }
    let(:point_infinity) { key1.public_key.set_to_infinity! }
    
    it "" do
      expect { MoneyTree::OpenSSLExtensions.add(0, 0) }.to raise_error(ArgumentError)
      expect { MoneyTree::OpenSSLExtensions.add(nil, nil).to raise_error(ArgumentError) }.to raise_error(ArgumentError)
      expect { MoneyTree::OpenSSLExtensions.add(point_1) }.to raise_error(ArgumentError)
      expect { MoneyTree::OpenSSLExtensions.add(0, point_2) }.to raise_error(ArgumentError)
      expect { MoneyTree::OpenSSLExtensions.add(point_infinity, point_2) }.to raise_error(ArgumentError)
      expect { MoneyTree::OpenSSLExtensions.add(point_1, point_2) }.to_not raise_error
    end
  end
  
end

```

```
```

