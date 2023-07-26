
    create database TIENDA;
use TIENDA;

create table empleado
(
id_empleado INT PRIMARY KEY AUTO_INCREMENT NOT NULL,
ci_empleado varchar(45) NOT NULL,
nombre VARCHAR(45) NOT NULL,
apellido VARCHAR(45) NOT NULL,
turno VARCHAR(45) NOT NULL
);

create table cliente
(
id_cliente INT PRIMARY KEY AUTO_INCREMENT NOT NULL,
ci_cliente INT(12),
nombre VARCHAR(45) NOT NULL,
apellido VARCHAR(45) NOT NULL
);

create table producto
(
id_producto INT PRIMARY KEY AUTO_INCREMENT NOT NULL,
tipo_producto VARCHAR(45) NOT NULL,
descripcion VARCHAR(45) NOT NULL,
precio INT(10) NOT NULL
);

create table transaccion
(
id_transaccion INT PRIMARY KEY AUTO_INCREMENT NOT NULL,
fecha VARCHAR(45) NOT NULL,
id_empleado INT,
id_cliente INT,
id_producto INT,
CONSTRAINT fk1_transaccion FOREIGN KEY(id_empleado) REFERENCES empleado(id_empleado),
CONSTRAINT fk2_transaccion FOREIGN KEY(id_cliente) REFERENCES cliente(id_cliente),
CONSTRAINT fk3_transaccion FOREIGN KEY(id_producto) REFERENCES producto(id_producto)
);

select * from empleado;
INSERT INTO producto(tipo_producto,descripcion,precio)
VALUES ("Coca-Cola","Pequeño","5Bs"),
		("Coca-Cola","Mediana","8Bs"),
		("Coca-Cola","Grande","12Bs"),
		("Fanta","Grande","5Bs"),
		("Fanta","Mediana","8Bs"),
		("Fanta","Pequeña","12Bs"),
        ("Sprite","Grande","5Bs"),
		("Sprite","Mediana","8Bs"),
		("Sprite","Pequeña","12Bs"),
        ("Pipocas-Saladas","Pequeña","Bs"),
        ("Pipocas-Saladas","Mediana","Bs"),
        ("Pipocas-Saladas","Grande","Bs"),
        ("Pipocas-Dulces","Pequeña","Bs"),
        ("Pipocas-Dulces","Mediana","Bs"),
        ("Pipocas-Dulces","Grande","Bs"),
         ("Pipocas-Mantequilla","Pequeña","Bs"),
        ("Pipocas-Mantequilla","Mediana","Bs"),
        ("Pipocas-Mantequilla","Grande","Bs");
        
