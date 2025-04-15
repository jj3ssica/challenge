USE carros;

CREATE TABLE marcas (
    id INT NOT NULL AUTO_INCREMENT,
    nome_marca VARCHAR(255) NOT NULL,
    PRIMARY KEY (id)
);

CREATE TABLE inventario (
    id INT NOT NULL AUTO_INCREMENT,
    modelo VARCHAR(255) NOT NULL,
    transmissao VARCHAR(255) NOT NULL,
    motor VARCHAR(255) NOT NULL,
    combustivel VARCHAR(255) NOT NULL,
    marcas_id INT NOT NULL,
    PRIMARY KEY (id),
    FOREIGN KEY (marcas_id)
        REFERENCES marcas (id)
);

CREATE TABLE clientes (
    id INT NOT NULL AUTO_INCREMENT,
    nome VARCHAR(255) NOT NULL,
    sobrenome VARCHAR(255) NOT NULL,
    endereco VARCHAR(255) NOT NULL,
    PRIMARY KEY (id)
);
    
INSERT INTO clientes (nome, sobrenome, endereco)
VALUES
	('Je', 'Silva', 'Rua 2'),
    ('Ana', 'Oliveira', 'Rua 3'),
    ('Flavio', 'Santos', 'Rua 4'),
    ('Van', 'Sena', 'Rua 5');
    
INSERT INTO marcas (nome_marca, origem)
VALUES
    ('BMW', 'Alemanha'),
    ('MERCEDES', 'Italia'),
    ('RENAULT', 'Franca'),
    ('JAGUAR', 'Inglaterra');

INSERT INTO inventario (modelo, transmissao, motor, combustivel, marcas_id)
VALUES
	('BMW 218', 'Automatica', '2.0', 'Gasolina', 1),
    ('xe 2.0D', 'Manual', '2.0', 'Diesel', 4);S