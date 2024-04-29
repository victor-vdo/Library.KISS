# KISS

<p align="justify">
The KISS principle, which stands for "Keep It Simple, Stupid," advocates for simplicity in design and development. It suggests that systems and solutions should be kept as simple as possible, avoiding unnecessary complexity. This principle emphasizes the importance of clarity, readability, and maintainability in code and design.</p>

<p align="justify">
By adhering to the KISS principle, developers aim to create systems that are easier to understand, debug, and maintain. Complex solutions tend to introduce more points of failure and are harder to troubleshoot. Therefore, simplicity is considered a virtue in software development, leading to more efficient and robust solutions.</p>


To simplify this code and apply the KISS (Keep It Simple, Stupid) principle, we can make some changes:

- Keep Methods Simple and Direct: Some methods can be simplified by removing redundancies and keeping only what is necessary.
- Avoid Complex Logic: Avoid complicated logic that makes the code harder to understand.
- Divide into Smaller Methods: Divide complex tasks into smaller, more specific methods, making the code easier to read and maintain.
- Eliminate Redundant Code: Look for code that repeats and abstract it into functions or methods.
- Improve Naming: Use clear and descriptive names for variables, methods, and classes.





```c#
public static class LibraryManager
{
    private static List<Book> books = new List<Book>();
    private static List<User> users = new List<User>();
    private static List<Loan> loans = new List<Loan>();

    public static void Start()
    {
        Console.WriteLine("Bem vindo ao sistema de gerenciamento de biblioteca!");
        while (true)
        {
            ShowMainMenu();
            var option = Console.ReadLine();
            ProcessOption(option);
        }
    }

    private static void ShowMainMenu()
    {
        Console.WriteLine("-----------------------------------------------------");
        Console.WriteLine("Selecione uma opção abaixo:");
        Console.WriteLine("1 - Cadastrar um livro");
        Console.WriteLine("2 - Consultar um livro");
        Console.WriteLine("3 - Consultar todos os livros");
        Console.WriteLine("4 - Remover um livro");
        Console.WriteLine("5 - Cadastrar um usuário");
        Console.WriteLine("6 - Cadastrar um Empréstimo");
        Console.WriteLine("7 - Devolver um livro");
        Console.WriteLine("8 - Sair");
    }

    private static void ProcessOption(string option)
    {
        switch (option)
        {
            case "1":
                BookRegister();
                break;
            case "2":
                SearchBook();
                break;
            case "3":
                ShowAllBooks();
                break;
            case "4":
                RemoveBook();
                break;
            case "5":
                UserRegister();
                break;
            case "6":
                LoanRegister();
                break;
            case "7":
                BookReturn();
                break;
            case "8":
                Environment.Exit(0);
                break;
            default:
                Console.Clear();
                Console.WriteLine("Opção inválida, tente novamente!");
                break;
        }
    }

    private static void BookRegister()
    {
        // Implementação do registro de livros
    }

    private static void SearchBook()
    {
        // Implementação da busca de livros
    }

    private static void ShowAllBooks()
    {
        // Implementação para mostrar todos os livros
    }

    private static void RemoveBook()
    {
        // Implementação para remover um livro
    }

    private static void UserRegister()
    {
        // Implementação para registrar um usuário
    }

    private static void LoanRegister()
    {
        // Implementação para registrar um empréstimo
    }

    private static void BookReturn()
    {
        // Implementação para devolver um livro
    }
}

#region Classes

public abstract class Model
{
    public Guid Id { get; set; }
    public Model()
    {
        Id = Guid.NewGuid();
    }
}

public class User : Model
{
    public User(string name, string email)
    {
        Name = name;
        Email = email;
    }

    public string Name { get; set; }
    public string Email { get; set; }
    public bool Active { get; set; }
}

public class Loan : Model
{
    public Loan(Guid userId, Guid bookId, DateTimeOffset loanDate)
    {
        UserId = userId;
        BookId = bookId;
        LoanDate = loanDate;
    }

    public Guid UserId { get; set; }
    public Guid BookId { get; set; }
    public DateTimeOffset LoanDate { get; set; }
    public bool Active { get; set; }
}

public class Book : Model
{
    public Book(string title, string author, string iSBN, int year)
    {
        Title = title;
        Author = author;
        ISBN = iSBN;
        Year = year;
    }

    public string Title { get; set; }
    public string Author { get; set; }
    public string ISBN { get; set; }
    public int Year { get; set; }
    public bool Active { get; set; }
}
#endregion
```
