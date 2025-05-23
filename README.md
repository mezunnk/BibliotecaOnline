# Biblioteca Online

Uma aplicação web para gerenciamento de uma biblioteca universitária, permitindo cadastro e consulta de livros, reserva de exemplares e histórico de reservas.

## Funcionalidades

- **Autenticação e Autorização** com ASP.NET Core Identity
  - Roles: **admin** e **aluno**
- **CRUD de Livros** (apenas admin)
- **Busca no Catálogo** por título, autor e categoria
- **Sistema de Reservas** para usuários logados
- **Histórico de Reservas** na página "Minhas Reservas"
- **Seed** de usuário administrador (`admin@biblioteca.com` / `Senha@123`)

## Tecnologias

- ASP.NET Core 8.0 MVC
- Entity Framework Core com SQL Server LocalDB
- ASP.NET Core Identity
- Razor Views e Bootstrap 5
- C# 11

## Pré-requisitos

- [.NET 8.0 SDK](https://dotnet.microsoft.com/download)
- SQL Server LocalDB (incluso no Visual Studio)
- Visual Studio 2022 ou superior

## Instalação e Execução

1. Clone o repositório:
   ```bash
   git clone https://github.com/mezunnk/BibliotecaOnline.git
   cd BibliotecaOnline
   ```
2. Exclua pastas de build e banco (bin, obj, .vs) se existirem.
3. Ajuste a string de conexão no `appsettings.json`:
   ```json
   "DefaultConnection": "Server=(localdb)\\MSSQLLocalDB;Database=TrabalhoBiblioteca;Trusted_Connection=True;MultipleActiveResultSets=true"
   ```
4. Aplique as migrations e atualize o banco:
   ```powershell
   dotnet tool install --global dotnet-ef    # se necessário
   dotnet ef database update
   ```
5. Execute a aplicação:
   ```bash
   dotnet run
   ```
6. Acesse no navegador:
   ```
   https://localhost:7056
   ```
7. Faça login como administrador:
   - **Email:** `admin@biblioteca.com`
   - **Senha:** `Senha@123`

## Estrutura do Projeto

- **/Areas/Identity**: páginas de login, registro e partial de menu
- **/Controllers**: `LivroesController` e `ReservasController`
- **/Models**: `AplicacaoUsuario`, `Livro`, `Reserva`
- **/Data**: `ApplicationDbContext`
- **/Views**: Views personalizadas para Livros e Reservas

## Contato

Qualquer dúvida ou sugestão, abra uma issue no repositório.
