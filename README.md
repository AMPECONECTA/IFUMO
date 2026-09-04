# Desafio Livre — Supabase + GitHub Pages

Aplicativo single-file HTML para Soldado, Pedro e Tainá iniciarem um desafio sem cigarro em **05/09/2026**.

## O que já está implementado

- autenticação Supabase por e-mail e senha;
- três perfis pré-cadastrados: Soldado, Pedro e Tainá;
- reivindicação segura do perfil por código privado;
- terapia comportamental simples de 14 dias;
- botão "Estou com vontade de fumar";
- desafios progressivos de 5, 5, 10 e 15 minutos;
- registro privado de intensidade e gatilho;
- registro privado de deslize;
- feed em tempo real;
- posts com texto e foto;
- reações de incentivo;
- Supabase Realtime;
- Supabase Presence;
- Storage privado para fotos;
- Row Level Security (RLS);
- dados de fissura visíveis somente ao próprio usuário;
- notícias compartilhadas contendo apenas eventos resumidos;
- cálculo local de progresso e economia estimada.

## 1. Criar o projeto Supabase

Crie um projeto no Supabase e aguarde o banco ficar disponível.

No dashboard:

1. abra **SQL Editor**;
2. crie uma nova query;
3. cole todo o conteúdo de `supabase.sql`;
4. execute.

Isso cria tabelas, RLS, Storage, triggers, Realtime e os perfis Soldado/Pedro/Tainá.

### Código privado do desafio

O banco contém apenas o hash do código. O código em texto puro deve ser entregue separadamente aos três participantes e **não deve ser publicado no repositório**.

## 2. Configurar autenticação

No Supabase, deixe Email/Password habilitado em Authentication.

Para uso privado e rápido entre os três, você pode decidir se exige confirmação de e-mail. Se a confirmação ficar ativa, cada pessoa terá de confirmar o e-mail antes de entrar.

Não crie contas com a service_role no navegador.

## 3. Project URL e Publishable Key

No Supabase, abra a área de conexão/API e copie:

- Project URL
- Publishable key (ou anon key do projeto)

Você tem duas opções:

### Opção A — testar sem editar o HTML
Abra `index.html`. A tela inicial pedirá URL e chave pública e salvará somente no navegador.

### Opção B — produção no GitHub
No `index.html`, substitua:

`__SUPABASE_URL__`

e

`__SUPABASE_PUBLISHABLE_KEY__`

pelos valores do projeto.

A publishable/anon key pode aparecer no frontend; a proteção real depende das políticas RLS. **Nunca use a service_role no HTML.**

## 4. GitHub Pages

Crie um repositório, por exemplo:

`desafio-livre`

Envie:

- `index.html`
- `.nojekyll`
- opcionalmente `README.md`

Depois, no GitHub:

1. Settings
2. Pages
3. Deploy from a branch
4. Branch `main`
5. Folder `/ (root)`
6. Save

A publicação costuma ficar em:

`https://SEU-USUARIO.github.io/desafio-livre/`

## 5. Primeiro acesso de cada desafiante

Cada pessoa:

1. abre o site;
2. cria uma conta com e-mail e senha;
3. escolhe Soldado, Pedro ou Tainá;
4. informa o código privado;
5. o nome é ligado à conta e não poderá ser reivindicado por outra pessoa.

## 6. Privacidade

O feed é compartilhado entre os três.

Fotos ficam em bucket privado e o app gera URLs temporárias.

Intensidade da fissura, gatilho, anotações de deslize e a data do último deslize ficam privados por RLS.

Se a pessoa marcar "compartilhar deslize", o grupo recebe apenas uma notícia resumida dizendo que ela registrou e retomou o desafio.

## 7. Fundamento comportamental

O app não substitui atendimento profissional. A abordagem usa:
- data definida para parar;
- identificação de gatilhos;
- atraso de 5 minutos;
- água;
- respiração lenta;
- mudança de ambiente;
- movimento curto;
- apoio social;
- registro e retomada após deslize.

Se a abstinência estiver difícil, tratamento profissional pode incluir aconselhamento e, quando indicado por profissional de saúde, medicamentos para cessação do tabagismo.
