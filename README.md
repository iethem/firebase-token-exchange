# [Firebase Token Exchange](https://ethem.dev/firebase-token-exchange)

<img width="708" height="517" alt="image" src="https://github.com/user-attachments/assets/36f2df43-3ab0-4abd-b36e-514878b2ce09" />


A simple static HTML tool for exchanging Firebase custom tokens for access tokens. This utility allows you to generate Firebase access tokens from custom tokens, which can then be used for API requests via curl, Postman, or other HTTP clients.

## Features

- **Real-time validation** of Firebase configuration (JSON or JavaScript object format)
- **Custom token input** with support for multi-line tokens
- **Firebase SDK integration** for secure token exchange
- **Copy to clipboard** functionality for easy token usage
- **Pure HTML/CSS/JS** - no external dependencies except Firebase SDK
- **No styling** - clean, minimal interface

## Usage

### Option 1: Live Demo
Try the tool online at: **[https://ethem.dev/firebase-token-exchange](https://ethem.dev/firebase-token-exchange)**

### Option 2: Local Usage
1. Open `index.html` in your web browser
2. Paste your Firebase configuration in the first textarea (supports both JSON and JS object formats)
3. Enter your custom token in the second textarea
4. Click "Generate Access Token"
5. Copy the resulting access token for use in API requests

## Firebase Configuration Format

The tool accepts Firebase configuration in either JSON or JavaScript object format:

### JSON Format:
```json
{
  "apiKey": "your-api-key",
  "authDomain": "your-project.firebaseapp.com",
  "projectId": "your-project-id",
  "storageBucket": "your-project.appspot.com",
  "messagingSenderId": "123456789",
  "appId": "1:123456789:web:abcdef123456"
}
```

### JavaScript Object Format:
```javascript
{
  apiKey: "your-api-key",
  authDomain: "your-project.firebaseapp.com",
  projectId: "your-project-id",
  storageBucket: "your-project.appspot.com",
  messagingSenderId: "123456789",
  appId: "1:123456789:web:abcdef123456"
}
```

## How It Works

1. **Configuration Validation**: The tool validates your Firebase config in real-time, checking for required fields (apiKey, authDomain, projectId)
2. **Token Exchange**: Uses Firebase Auth SDK to sign in with your custom token
3. **Access Token Generation**: Retrieves the Firebase ID token (access token) for authenticated requests
4. **Copy Ready**: The generated token can be copied and used immediately in HTTP requests

## Example Usage with curl

After generating an access token, you can use it in API requests:

```bash
curl -H "Authorization: Bearer YOUR_ACCESS_TOKEN" \
     -H "Content-Type: application/json" \
     https://your-firebase-project.firebaseio.com/your-endpoint.json
```

## Security Notes

- This tool runs entirely in the browser
- No data is sent to external servers except Firebase
- Custom tokens should be generated securely on your server
- Access tokens are temporary and should be refreshed as needed

## Requirements

- Modern web browser with JavaScript enabled
- Valid Firebase project configuration
- Custom token from your authentication server

## File Structure

```
firebase-token-generator/
├── index.html          # Main application file
└── README.md          # This documentation
```

## Browser Compatibility

- Chrome/Chromium
- Firefox
- Safari
- Edge

## File Structure

```
firebase-token-generator/
├── index.html          # Main application file
├── README.md          # This documentation
└── LICENSE            # MIT License
```

## License

This project is open source and available under the MIT License.
