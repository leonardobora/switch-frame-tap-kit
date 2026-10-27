# Switch Frame Tap — kit portátil (TV Android e Windows)

Empacotamento de bolso do **Switch Frame Tap** para levar o Switch (inclusive o **Lite**) para a
casa de outra pessoa: o viewer de **Windows** para jogar num monitor qualquer e o **APK** para
Android TV / Google TV via rede.

> **Este repositório não é o projeto original.** Ele só redistribui, sem modificação, os binários
> oficiais da release `v0.7.19` de [TomasUribe/switch-frame-tap](https://github.com/TomasUribe/switch-frame-tap),
> licenciados em **GPL-2.0** (o texto está em [`LICENSE`](LICENSE)). Todo o crédito é do autor
> original; para código-fonte, issues e releases novas, use o repositório dele.

## Por que existe

O Switch Lite **não tem saída de vídeo** — sem dock, sem HDMI, sem DisplayPort por USB-C. Nenhum
cabo, adaptador ou placa de captura tira imagem dele. O caminho é a CFW (Atmosphère) com o
sysmodule do Frame Tap, que publica a tela por USB ou pela rede.

Este kit resolve o lado do *host*: o que rodar no PC do amigo e o que instalar na TV.

## Conteúdo

| Arquivo | O que é |
|---|---|
| `windows/SwitchFrameTap.exe` | viewer de Windows (SDL2, já com as DLLs) |
| `windows/README-WINDOWS.txt` | instruções oficiais (driver WinUSB, teclas, gravação) |
| `android/switch-frame-tap-0.7.19-android.apk` | app para Android / Android TV (pacote `io.github.switchframetap.tv`, Android 6+) |

## PC do amigo (cabo USB) — menor latência

1. No console: sysmodule do Frame Tap ativo e um jogo aberto.
2. Cabo USB-C **de dados** do console no PC.
3. Uma vez só, instalar o driver **WinUSB com o [Zadig](https://zadig.akeo.ie/)**: `Options → List All Devices` → **"Switch Frame Tap" (1209 5F1E)** → `WinUSB` → `Install Driver`. O console só aparece no Zadig enquanto o sysmodule está rodando.
4. Abrir `windows/SwitchFrameTap.exe`.

Teclas: `F11` tela cheia · `Esc` sai · `M` silencia · **`R` grava MP4** (H.264 nativo do console).

## TV Android / Google TV — rede, sem cabo

1. No console, no app *Switch Frame Tap*: ligar **Network streaming** e reiniciar.
2. Instalar o APK na TV (Downloader, pendrive, ou `adb install -r`).
3. Abrir o app → **Network**. Ele acha o console pelo beacon **UDP 9951**; se não achar, digitar o
   IP na mão (**TCP 9950**).
4. Com um jogo aberto no console, o stream começa.

## Limites que valem saber

- **Switch Lite nunca passa de 720p30** — 1080p60 exige dock + patches, que o Lite não tem.
- **Frame Tap e sysDVR são exclusivos no USB**: os dois disputam o mesmo gadget (`1209:5f1e` é do
  Frame Tap; `18d1:4ee0` é o sysDVR segurando o USB). DBI/MTP aberto também atrapalha.
- Wi-Fi rende menos que cabo e esquenta o console; sessões longas na tomada.
- Console em CFW: o streaming é local (não passa pela Nintendo), mas o risco normal de ban online
  continua existindo.

## Verificação de integridade

```
sha256sum -c SHA256SUMS
```

Os tamanhos e hashes são os dos arquivos publicados na release oficial `v0.7.19`.

## Licença

GPL-2.0 — ver [`LICENSE`](LICENSE). Os binários aqui são cópias não modificadas dos artefatos
oficiais; obras de terceiros embarcadas (SDL2, libusb, FFmpeg, fontes DejaVu, FSR1) mantêm suas
licenças em `windows/licenses/`.
