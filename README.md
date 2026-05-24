# TGS-ads

Configuração remota de anúncios para o **TGS Pack Manager**.

## Arquivo principal

- `pack-manager.json` — lido pelo app em cada exportação

## Como atualizar

1. Edite `pack-manager.json` neste repositório
2. Faça commit e push na branch `main`
3. O Pack Manager busca a nova config em até ~5 minutos (cache) ou na próxima exportação após fechar o app

## Modos de anúncio

### Anúncios de rede (CPM) — Google Ad Manager

Preencha `vastTagUrl` com sua tag VAST. Deixe `ads` vazio.

```json
{
  "version": 1,
  "enabled": true,
  "ads": [],
  "vastTagUrl": "https://pubads.g.doubleclick.net/gampad/ads?...",
  "analyticsUrl": null
}
```

### Patrocínios diretos (MP4)

Remova ou deixe `vastTagUrl` como `null` e adicione vídeos em `ads`:

```json
{
  "version": 1,
  "enabled": true,
  "ads": [
    {
      "id": "sponsor-001",
      "type": "video",
      "url": "https://cdn.exemplo.com/anuncio.mp4",
      "title": "Patrocinado por Servidor X",
      "clickUrl": "https://discord.gg/exemplo",
      "minWatchPercent": 100
    }
  ],
  "vastTagUrl": null,
  "analyticsUrl": null
}
```

> Se `vastTagUrl` estiver preenchido, ele tem **prioridade** sobre `ads`.

### Desativar anúncios temporariamente

```json
"enabled": false
```

## URL usada pelo app

```
https://raw.githubusercontent.com/T1NG4/TGS-ads/main/pack-manager.json
```
