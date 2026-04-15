# Laboratório 1 do módulo 4

## Objetivo
Compreender o funcionamento do AWS IAM, explorando usuários, grupos e políticas, além de testar permissões na prática.

---

## Etapas do Laboratório

### 1. Acesso ao ambiente
- Iniciado o laboratório na plataforma AWS.
- Acessado o Console de Gerenciamento.
- Navegado até o serviço IAM.

---

### 2. Exploração de usuários

Usuários disponíveis:
- user-1
- user-2
- user-3

Verificações realizadas no user-1:
- Não possui permissões diretas.
- Não pertence a nenhum grupo.
- Possui senha para acesso ao console.

---

### 3. Exploração de grupos

Grupos disponíveis:
- EC2-Admin
- EC2-Support
- S3-Support

Análise das permissões:

EC2-Support:
- Política: AmazonEC2ReadOnlyAccess
- Permite visualizar recursos do EC2 (List e Describe)

S3-Support:
- Política: AmazonS3ReadOnlyAccess
- Permite listar e visualizar objetos no S3

EC2-Admin:
- Política em linha
- Permite:
  - Descrever instâncias
  - Iniciar instâncias
  - Parar instâncias

---

### 4. Associação de usuários aos grupos

Configuração realizada conforme cenário:

- user-1 → S3-Support
- user-2 → EC2-Support
- user-3 → EC2-Admin

Após associação:
- Cada grupo passou a ter 1 usuário

---

### 5. Teste de acesso dos usuários

URL de login do IAM copiada no painel.

Testes realizados em janela anônima:

user-1:
- Consegue acessar o S3
- Não consegue acessar o EC2

user-2:
- Consegue acessar o EC2 em modo leitura
- Não consegue parar instâncias
- Não consegue acessar o S3

user-3:
- Consegue acessar o EC2
- Consegue parar instâncias
- Não possui acesso ao S3

---

## Resultado

- Usuários corretamente vinculados aos grupos
- Permissões aplicadas conforme esperado
- Testes confirmaram as restrições e acessos definidos pelas políticas

---

## Conclusão

O laboratório demonstrou como o AWS IAM permite:
- Gerenciar usuários e grupos
- Aplicar políticas de acesso
- Controlar permissões de forma segura

