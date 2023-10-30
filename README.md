*Link RDS:*

https://us-east-1.console.aws.amazon.com/rds/home?region=us-east-1#database:id=database-1;is-cluster=false


*Modelo lógico:*

<img width="436" alt="modeloLogico" src="https://github.com/renanribeir0/PonderadaS2/assets/110369271/7fe81d54-80c9-486f-bc34-00e8200fa3b0">


*Banco de dados criado:*

<img width="788" alt="image" src="https://github.com/renanribeir0/PonderadaS2/assets/110369271/c884d734-68e6-4729-92b0-bf89d46ca998">

*Tabelas criada:*

<img width="198" alt="image" src="https://github.com/renanribeir0/PonderadaS2/assets/110369271/e9a048c5-ef97-44b4-a288-f275200712d5">

*Script:*
[Upluse ponderadaBanco;

INSERT INTO Veiculo (Nome, Modelo, Placa, AnoFabricacao) VALUES
    ('Veiculo1', 'Modelo1', 'XYZ123', 2020),
    ('Veiculo2', 'Modelo2', 'ABC789', 2019);

INSERT INTO Paciente (Nome, DataNascimento, Endereco) VALUES
    ('Paciente1', '1990-01-15', 'Endereco1'),
    ('Paciente2', '1985-05-20', 'Endereco2');

INSERT INTO Entrega (VeiculoID, PacienteID, DataEntrega) VALUES
    (1, 1, '2023-01-10'),
    (1, 2, '2023-01-15'),
    (2, 1, '2023-01-20');

SELECT
    MONTH(DataEntrega) AS Mes,
    YEAR(DataEntrega) AS Ano,
    VeiculoID,
    COUNT(DISTINCT PacienteID) / COUNT(DISTINCT MONTH(DataEntrega)) AS MediaPacientesPorMes
FROM Entrega
GROUP BY Mes, Ano, VeiculoID;
oading Script.sql…]()

*Média:*

<img width="776" alt="image" src="https://github.com/renanribeir0/PonderadaS2/assets/110369271/1b26c75e-49a7-4f5b-8304-0f11e140ade4">


*Código:*
use ponderadaBanco;

INSERT INTO Veiculo (Nome, Modelo, Placa, AnoFabricacao) VALUES
    ('Veiculo1', 'Modelo1', 'XYZ123', 2020),
    ('Veiculo2', 'Modelo2', 'ABC789', 2019);

INSERT INTO Paciente (Nome, DataNascimento, Endereco) VALUES
    ('Paciente1', '1990-01-15', 'Endereco1'),
    ('Paciente2', '1985-05-20', 'Endereco2');

INSERT INTO Entrega (VeiculoID, PacienteID, DataEntrega) VALUES
    (1, 1, '2023-01-10'),
    (1, 2, '2023-01-15'),
    (2, 1, '2023-01-20');

SELECT
    MONTH(DataEntrega) AS Mes,
    YEAR(DataEntrega) AS Ano,
    VeiculoID,
    COUNT(DISTINCT PacienteID) / COUNT(DISTINCT MONTH(DataEntrega)) AS MediaPacientesPorMes
FROM Entrega
GROUP BY Mes, Ano, VeiculoID;

