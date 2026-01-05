# WiFi QR Code Generator

Монгол хэл дээрх, хялбар WiFi QR код үүсгэгч веб аппликейшн. Client-side JS ашигласан тул таны мэдээлэл сервер лүү илгээгдэхгүй.

## Онцлог
- 🔒 100% Client-side (Аюулгүй)
- 🌓 Dark/Light горим
- 📱 Responsive дизайн (Tailwind CSS)
- 📥 QR код татаж авах боломж

## Local дээр ажиллуулах (Docker-гүй)

Файлыг шууд хөтөч дээр нээх боломжтой:
1. `index.html` файлыг Chrome/Firefox дээр нээ.

## Docker ашиглан ажиллуулах

1. Image үүсгэх:
```bash
docker build -t wifi-qr-gen .
```

2. Container ажиллуулах:
```bash
docker run -p 8080:8080 wifi-qr-gen
```

3. Хөтөч дээр `http://localhost:8080` хаягаар орно.

## Google Cloud Run дээр байршуулах

1. Google Cloud CLI суулгасан байх шаардлагатай.
2. Төслөө сонгох:
```bash
gcloud config set project [PROJECT_ID]
```

3. Cloud Build ашиглан deploy хийх:
```bash
gcloud run deploy --source .
```
- Service name: `wifi-qr-gen` гэж өгнө.
- Region сонгоно.
- "Allow unauthenticated invocations" гэдэгт `y` гэж хариулна.

## Файлын бүтэц
- `index.html`: Үндсэн код (HTML/JS/CSS)
- `Dockerfile`: Docker тохиргоо
- `nginx.conf`: Nginx серверийн тохиргоо
