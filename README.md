# NGROK QR Code Generator 🔗

A simple tool that generates QR codes for NGROK URLs, making it easier to access your local development server on mobile devices.
I was tired of rewriting ngrok URLs to my mobile phone, so I created a script to generate QR codes.

## 🌐 Live Demo

Visit [https://puliczek.github.io/ngrokqr/?url=https://your-ngrok-url.ngrok.app](https://puliczek.github.io/ngrokqr/?url=https://your-ngrok-url.ngrok.app)

## 🚀 Quick Start

How it works:
1. Start NGROK for port 3000
2. Fetch the public URL
3. Open the QR code generator in your browser

### Windows (PowerShell)

```powershell
Start-Process powershell "ngrok http 3000"; $url = (Invoke-RestMethod http://localhost:4040/api/tunnels).tunnels[0].public_url; Start-Process "https://puliczek.github.io/ngrokqr/?url=$url"
```


### Linux (Bash) (I don't know if this works)

```bash
ngrok http 3000; url=$(curl -s http://localhost:4040/api/tunnels | jq -r '.tunnels[0].public_url'); xdg-open "https://puliczek.github.io/ngrokqr/?url=$url"
```

### MacOS (Terminal) (I don't know if this works)

```bash
ngrok http 3000; url=$(curl -s http://localhost:4040/api/tunnels | jq -r '.tunnels[0].public_url'); open "https://puliczek.github.io/ngrokqr/?url=$url"
```

### Local Development

If you prefer to run the QR code generator locally, you can download index.html and open directly in your browser.


## 🔒 Privacy Note

 The code is open source and available on GitHub, allowing you to verify the privacy and security measures yourself. The QR code generation process occurs entirely client-side in your browser. No URL data is stored or tracked by this tool. However, since the application is hosted on GitHub Pages, GitHub's standard analytics and logging may capture URL parameters as part of their hosting service.

## 🤝 Contributing

Feel free to open issues or submit pull requests if you have suggestions for improvements.

## 📝 License

This project is open source and available under the MIT License.

## 👨‍💻 Author

Created by [pulik.dev](https://www.pulik.dev)
