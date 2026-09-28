# Cupu Android Updates

Canal público de distribuição das versões Android do Cupu. Este repositório não contém o código-fonte do aplicativo.

## Arquivos de cada versão

Cada versão publicada contém exatamente estes arquivos para baixar:

- `cupu.apk` — pacote Android assinado com a linhagem de assinatura validada do Cupu.
- `manifest.json` — versão, notas da atualização e SHA-256 do APK.

O app consulta este endereço estável:

`https://github.com/henrymsm7-gif/cupu-android-updates/releases/latest/download/manifest.json`

O manifesto aponta para:

`https://github.com/henrymsm7-gif/cupu-android-updates/releases/latest/download/cupu.apk`

Formato do manifesto:

```json
{
  "version": "1.0.1",
  "version_code": 3,
  "file_url": "https://github.com/henrymsm7-gif/cupu-android-updates/releases/latest/download/cupu.apk",
  "sha256": "<64-character lowercase SHA-256 of cupu.apk>",
  "changelog": "Resumo da atualização."
}
```

## Requisitos para publicar

- Aumentar o `version_code` do Android a cada versão.
- Compilar passando o endereço estável do manifesto em `CUPU_UPDATE_MANIFEST_URL`.
- Conferir ID do pacote, código da versão, assinatura/linhagem e SHA-256 antes de anexar o APK.
- Enviar os dois arquivos à mesma versão do GitHub Release, para que `latest/download` sirva um par correspondente.
- Nunca enviar keystores, senhas, credenciais, arquivos-fonte ou builds de depuração a este repositório.

Nenhum APK será publicado até validarmos a assinatura em relação ao Cupu instalado no Xiaomi.
