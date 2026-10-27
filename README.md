# Conselho Kadosch Mato Grosso — Programação 2027

Site estático responsivo, instalável como PWA, baseado no documento institucional fornecido. Dados originais transcritos para `dados-2027.js`.

## Publicar no GitHub Pages

1. Crie um repositório público no GitHub, por exemplo `kadosch-2027`.
2. Envie **todos os arquivos e a pasta `assets`** que estão ao lado deste README para a raiz do repositório (não envie apenas o ZIP).
3. Abra **Settings → Pages → Build and deployment → Deploy from a branch**, escolha `main` e a pasta `/(root)`; salve.
4. O site ficará em `https://SEU-USUARIO.github.io/kadosch-2027/` quando o GitHub concluir a publicação.
5. Teste `index.html`, `programacao.html` e a instalação do PWA em um navegador compatível.

## Atualizar a programação

- Acesse `admin.html` e edite os eventos localmente. Clique **Arquivo para publicar (dados-2027.js)** e substitua no repositório o arquivo de mesmo nome. O botão **Exportar JSON** produz uma cópia dos dados para backup/importação. Mudanças locais por si sós **não** atualizam o site para outras pessoas.
- Para comunicados: em `admin.html`, cadastre-os e use **Exportar comunicados JSON**; publique o arquivo como `avisos.json`. O site lê este arquivo quando não há comunicados locais editados no navegador.
- Depois de publicar, recarregue a página para receber a versão atualizada; dispositivos offline podem continuar a apresentar os últimos dados em cache.
- Não armazene informações reservadas: o repositório e os arquivos publicados são públicos.

## Informações e cautelas

- Os 11 encontros (9 ordinários, 2 magnos) e a atividade sem sessão em janeiro foram mantidos como constam no documento.
- 18/08/2027 é uma quarta-feira e foi **preservado** como no documento, sem correção automática.
- A iniciação em novembro consta como **possível**. A instrução e a Ordem do Dia não foram inventadas.
- Não há hora de término no documento. O download `.ics` conserva apenas `DTSTART` e informa essa ausência na descrição. Alguns aplicativos de calendário atribuem uma duração padrão por conta própria. No Google Agenda, é oferecida uma duração **temporária de 1 hora para permitir a criação do formulário**, devendo o usuário ajustá-la antes de salvar. Essa duração não integra a programação oficial.
- O contador considera o fuso de Cuiabá (UTC−4) conforme as regras vigentes para 2027. Caso ocorra alteração legal do fuso ou do horário de verão, atualize `epochAtCuiaba` no `app.js`.
- O painel administrativo é um **editor local**, não um backend com autenticação; não requer senha. Para edição colaborativa segura em tempo real é necessário um serviço externo autenticado.
- Os dois emblemas foram extraídos do próprio documento Word e estão em `assets/`.
- Sem infraestrutura de notificações push; comunicados são exibidos no site. O PWA opera offline depois da primeira visita.

## Testar localmente

Na pasta que contém o site, execute `python -m http.server 8000` e abra `http://localhost:8000`. O service worker funciona em HTTPS ou localhost, não em `file://`.
