Etapa 1:

{
  "pagina_inicial": "www.google.com",
  "idioma_preferido": "Português do Brasil",
  "localizacao": "São Paulo",
  "tema": "Clássico",
  "mostrar_favoritos": "Sim",
  "zoom": "100%"
}

Etapa 2:

Para normalizar as tabelas conforme o modelo relacional, vamos criar duas tabelas: Funcionarios e Emails. A tabela Funcionarios armazenará as informações básicas de cada funcionário, e a tabela Emails armazenará os endereços de e-mail associados a cada funcionário.

CREATE TABLE Funcionarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    endereco VARCHAR(255) NOT NULL,
    cargo VARCHAR(50) NOT NULL,
    jornada INT NOT NULL,
    salario DECIMAL(10,2) NOT NULL
);

CREATE TABLE Emails (
    id INT AUTO_INCREMENT PRIMARY KEY,
    funcionario_id INT,
    email VARCHAR(100) NOT NULL,
    FOREIGN KEY (funcionario_id) REFERENCES Funcionarios(id)
);

INSERT INTO Funcionarios (nome, endereco, cargo, jornada, salario) VALUES
('João Grilo', 'Rua Suassuna, 30, João Pessoa, PB', 'Contador', 40, 3000.00),
('Ada Byron', 'Rua Lovelace, 67, London', 'Developer', 20, 15000.00),
('Gerundino', 'Rua Substantivo, 78, Bairro Predicado, Mesóclise-AC', 'Linguista', 44, 8000.00),
('Chicó', 'Rua Eurico, 50, Apt 28, Bloco C, João Pessoa, PB', 'Developer', 20, 15000.00);

INSERT INTO Emails (funcionario_id, email) VALUES
(1, 'griomailcom'),
(1, 'joaog@mk.com'),
(2, 'ada@mail.com'),
(2, 'abyrong@tech.com'),
(3, 'gerundino@gmail.com'),
(4, 'joao@developer.com');

[
    {
        "id": 1,
        "nome": "João Grilo",
        "endereco": "Rua Suassuna, 30, João Pessoa, PB",
        "cargo": "Contador",
        "jornada": 40,
        "salario": "R$ 3000,00",
        "emails": ["griomailcom", "joaog@mk.com"]
    },
    {
        "id": 2,
        "nome": "Ada Byron",
        "endereco": "Rua Lovelace, 67, London",
        "cargo": "Developer",
        "jornada": 20,
        "salario": "R$ 15000,00",
        "emails": ["ada@mail.com", "abyrong@tech.com"]
    },
    {
        "id": 3,
        "nome": "Gerundino",
        "endereco": "Rua Substantivo, 78, Bairro Predicado, Mesóclise-AC",
        "cargo": "Linguista",
        "jornada": 44,
        "salario": "R$ 8000,00",
        "emails": ["gerundino@gmail.com"]
    },
    {
        "id": 4,
        "nome": "Chicó",
        "endereco": "Rua Eurico, 50, Apt 28, Bloco C, João Pessoa, PB",
        "cargo": "Developer",
        "jornada": 20,
        "salario": "R$ 15000,00",
        "emails": ["joao@developer.com"]
    }
]

Etapa 3:

![image](https://github.com/FelipeLobo015/Atividade-individual---Tema-NoSQL/assets/77967679/8eaf7f1f-4ee7-435c-9b84-9ab4d6b51d10)
