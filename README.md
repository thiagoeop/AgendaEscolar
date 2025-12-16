# Agenda Escolar - EduSync

Este é um projeto de agenda escolar que utiliza Supabase para autenticação e armazenamento de dados.

## Configuração do Supabase

1. Crie um projeto no [Supabase](https://supabase.com).
2. Vá para Settings > API e copie a URL do projeto e a chave anon/public.
3. No código, substitua `supabaseUrl` pela URL real do seu projeto Supabase.

### Exemplo:
```javascript
const supabaseUrl = 'https://abcdefghijklmnop.supabase.co';
const supabaseKey = 'sb_publishable_VnUv3wfgnZgYiS2L0e3Skg_CqBaDwT9';
```

## Funcionalidades

- Cadastro de usuários (Aluno, Professor, Servidor)
- Login com autenticação via Supabase
- Calendário escolar com eventos
- Logout seguro

## Como executar

Abra `index.html` no navegador para começar.

## Notas

- Certifique-se de confirmar o e-mail após o cadastro para ativar a conta.
- Os eventos estão hardcoded; para armazenar no banco, adicione uma tabela 'events' no Supabase.