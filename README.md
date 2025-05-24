# MagicSec (api client)

This repository is a client library that provides a convenient way to interact with the MagicSec Obfuscation Service. This service allows you to obfuscate Lua scripts for various platforms while offering options for security and performance trade-offs.

## Installation

To use magicsec in your project, install it using npm:

```bash
npm install magicsec
```

## Usage

```javascript
import MagicSec, { ObfuscationPayload, ObfuscationResult } from 'magicsec';

// Create an instance of MagicSec with your API key
const apiKey = 'your-api-key';
const magicSec = new MagicSec(apiKey);

// Prepare the obfuscation payload
const payload: ObfuscationPayload = {
  script: 'print("Hello, world!")',
  platformLock: 'lua', // fivem // roblox // csgo // lua
  antiTamper: true,
  watermark: '"Protected by MagicSec"',
  encryptStrings: true,
  constantEncryption: true,
  maxSecurity: true
};

// Obfuscate the script
try {
  const obfuscationResult: ObfuscationResult = await magicSec.obfuscate(payload);
  console.log('Obfuscation successful:', obfuscationResult);
} catch (error) {
  console.error('Obfuscation error:', error.message);
}
```

## Documentation

For detailed information about the available options and methods, refer to the [API documentation](https://magicsec.vip/).

## Contributing

Contributions are welcome! If you find any issues or have suggestions for improvements, feel free to open an issue or submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
