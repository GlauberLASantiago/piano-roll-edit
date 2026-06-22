# Piano Roll Edit

Editor de piano roll estático e de página única, executado diretamente no navegador — sem instalação, sem build.

## Funcionalidades

- **Importar** arquivos MIDI (`.mid`, `.midi`) e MusicXML (`.xml`, `.musicxml`)
- **Editar** notas no piano roll:
  - Duplo clique para criar nota
  - Arraste para mover
  - Arraste a borda direita para redimensionar
  - Selecione e pressione `Delete`/`Backspace` para remover
- **Reproduzir** com SoundFont General MIDI (16 instrumentos disponíveis)
- **Controle de BPM** (30–300)
- **Zoom** in/out no eixo temporal
- **Exportar** para MIDI ou MusicXML

## Como usar

Basta abrir o arquivo `index.html` em qualquer navegador moderno — não é necessário servidor web.

```bash
# Exemplo com Python
python3 -m http.server 8080
# Acesse http://localhost:8080
```

Ou abra diretamente:

```
Arquivo → Abrir → index.html
```

## Dependências (via CDN)

| Biblioteca | Versão | Uso |
|---|---|---|
| [@tonejs/midi](https://github.com/Tonejs/Midi) | 2.0.28 | Leitura e escrita de MIDI |
| [soundfont-player](https://github.com/danigb/soundfont-player) | 0.12.0 | Reprodução de áudio com SoundFont |

Não há `package.json` nem etapas de build.

## Arquivo de exemplo

`VitopamosEx.musicxml` — importe-o pela toolbar para testar o editor.

## Estrutura do projeto

```
piano-roll-edit/
├── index.html          # Toda a aplicação (HTML + CSS + JS)
└── VitopamosEx.musicxml # Arquivo MusicXML de exemplo
```

## Compatibilidade

Funciona nos navegadores modernos com suporte a Web Audio API (Chrome, Firefox, Edge, Safari).
