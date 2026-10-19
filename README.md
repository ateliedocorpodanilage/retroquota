# RetroQuota

RetroQuota é um monitor de uso para ferramentas de desenvolvimento com IA. Ele exibe limites, janelas de renovação e atividade de Claude, Codex, Cursor, Antigravity e outros providers compatíveis, em uma interface inspirada em monitores CRT vintage.

O projeto combina os recursos de monitoramento com uma interface inspirada em monitores CRT: brilho verde/âmbar, scanlines e uma tela compacta que pode ficar presa à borda ou flutuar livremente pela área de trabalho.

## Recursos

- modo preso à borda ou modo flutuante;
- arraste entre múltiplos monitores;
- minimizar para a bandeja do sistema;
- seleção dos providers exibidos;
- limites atuais, janelas de reset e estado de atividade;
- configuração persistida por usuário;
- integração opcional com hooks do Claude Code;
- código-fonte aberto sob licença MIT.

## Desenvolvimento no Windows

Pré-requisitos:

- Rust com o alvo `x86_64-pc-windows-msvc`;
- Visual Studio com ferramentas C++ MSVC;
- WebView2 Runtime.

```powershell
cd windows
cargo test --locked
cargo build --release --locked
```

Os executáveis são gerados em `windows/target/release/`:

- `quotacrt.exe` — aplicativo principal;
- `quotacrt-hook.exe` — auxiliar opcional para eventos de sessão.

## Distribuição

O instalador público será publicado em GitHub Releases como `RetroQuota-Setup.exe`. O updater já aponta para `https://github.com/ateliedocorpodanilage/retroquota`.

Para distribuição confiável no Windows, recomenda-se assinar o instalador e os executáveis com um certificado Authenticode. A assinatura de commits GitHub e a assinatura do executável são processos diferentes.

## Privacidade

RetroQuota lê somente dados locais necessários para obter os estados de uso dos providers configurados. Credenciais pertencentes às ferramentas originais não devem ser copiadas para o repositório, incluídas em logs ou compartilhadas em issues.

## Atribuição

RetroQuota é uma derivação independente baseada na arquitetura Windows do projeto Codenotch. Consulte `NOTICE.md` e `LICENSE` para os avisos de licença e atribuição.
