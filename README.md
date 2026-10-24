# Piano Roll Edit

Editor de piano roll estático e de página única, executado diretamente no navegador — sem instalação, sem build.

## Funcionalidades

- **Importar** arquivos MIDI (`.mid`, `.midi`) e MusicXML (`.xml`, `.musicxml`)
- **Editar** notas no piano roll:
  - Duplo clique para criar nota; arraste para mover e use `Shift+clique` para seleção múltipla
  - Arraste a borda direita para redimensionar
  - Copiar/colar, duplicar por compasso, transpor oitavas e ajustar velocity
  - Quantizar à resolução da grade escolhida
  - Desfazer/refazer até 100 edições
- **Faixas MIDI**: selecionar e criar faixas; importação/exportação MIDI preserva nome, canal, programa, velocity e notas por faixa
- **Reproduzir** com SoundFont General MIDI (16 instrumentos disponíveis), com pausa, retomada, playhead e loop por compassos
- **Grade musical**: compassos, fórmula de compasso, resolução configurável (incluindo modo livre) e faixa de oitavas
- **Controle de BPM** (30–300), zoom temporal e atalhos de teclado
- **Exportar** para MIDI ou MusicXML, com múltiplas partes, compasso e armadura de clave

### Atalhos

| Atalho | Ação |
|---|---|
| `Espaço` | Reproduzir / pausar |
| `Home` | Parar e voltar ao início |
| `Delete` / `Backspace` | Excluir seleção |
| `Ctrl/Cmd + C`, `Ctrl/Cmd + V` | Copiar / colar seleção na posição do playhead |
| `Ctrl/Cmd + D` | Duplicar seleção no compasso seguinte |
| `Ctrl/Cmd + Z`, `Ctrl/Cmd + Shift + Z` | Desfazer / refazer |
| Setas | Mover notas; `Shift + ↑/↓` transpõe uma oitava |

O MusicXML gerado mantém as partes, fórmula de compasso e armadura de clave, mas a escrita rítmica continua simplificada e não preserva articulações, vozes, mudanças de andamento ou outros detalhes notacionais avançados. A reprodução usa o instrumento escolhido no controle, enquanto a exportação MIDI mantém o programa associado a cada faixa.

## Como usar

Basta abrir o arquivo `index.html` em qualquer navegador moderno — não é necessário servidor web. A primeira carga precisa de conexão à internet para baixar as bibliotecas CDN e os SoundFonts.

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
