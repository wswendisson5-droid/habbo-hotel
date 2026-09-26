# Plano de teste — Habbo Hotel

Objetivo: validar se a hospedagem cPanel atual consegue executar o emulador Java de forma persistente, com MariaDB/MySQL e WebSocket para Nitro.

## Base escolhida
- Arcturus Morningstar Extended
- Banco incluído: `Default Database/FullDatabase.sql`
- Configuração de exemplo: `Latest_Compiled_Version/config.ini.example`
- WebSocket Nitro embutido
- Build via Maven / JDK 21

## Ordem do teste
1. Validar build no GitHub Actions.
2. Confirmar Java 21 no cPanel.
3. Criar banco MySQL/MariaDB vazio.
4. Importar `Default Database/FullDatabase.sql`.
5. Ajustar `config.ini` com as credenciais do banco.
6. Configurar WebSocket Nitro (porta e whitelist) no banco.
7. Executar o JAR no cPanel.
8. Confirmar que o processo permanece ativo.
9. Testar conexão WebSocket externa.
10. Só depois integrar o client Nitro.

## Critério de sucesso inicial
O emulador deve:
- conectar ao banco;
- iniciar sem erro fatal;
- abrir a porta configurada;
- manter o processo vivo;
- aceitar conexão WebSocket.

Nenhuma personalização será feita antes dessa validação.
