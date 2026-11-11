# Clear Path · Distribuição de atualizações Android

Repositório **público** exclusivo para disponibilizar arquivos de atualização OTA do aplicativo Clear Path. O código-fonte original do app está em um repositório separado e privado.

## Hospedagem

Configurar **Settings → Pages → Build and deployment → Source: Deploy from a branch → main → /(root)**. O Github Pages serve o conteúdo deste repositório em:

https://thiarllys-melo.github.io/clear-path-updates/

Após a primeira publicação, o aplicativo consulta:

- \`updates/latest.json\` — informações da versão atual;
- \`updates/1.0.N.zip\` — pacote de interface correspondente.

A pasta \`updates/\` será preenchida automaticamente a cada build relevante do repositório **privado** após configurar o segredo \`CLEARPATH_UPDATES_TOKEN\` no repositório privado. É necessário um fine-grained PAT com permissão **Contents: Read and write** exclusivamente para \`Thiarllys-melo/clear-path-updates\`. Nunca publique esse token neste repositório, em issues ou no chat.

O app usa verificação de versão e instala atualizações de **HTML, CSS e JavaScript** somente após confirmação. Mudanças nativas do Android exigem um novo APK com assinatura estável.

## Segurança e distribuição

O GitHub Pages disponibiliza publicamente os arquivos compilados do aplicativo: eles podem ser analisados por qualquer pessoa. Nenhum registro financeiro individual, senha, chave \`service_role\` ou segredo deve ser incorporado aos assets. Chaves públicas/anon de serviços, quando utilizadas, não substituem regras RLS.

Não edite manualmente \`updates/latest.json\` e os arquivos de versão. Eles são produzidos pela CI do Clear Path e verificados por digest SHA-256. Para distribuição a terceiros, assinar criptograficamente os bundles e usar um fluxo de aprovação de releases.
