#Código del ejercicio negocio de WardwareStore

CREATE TABLE IF NOT EXISTS providers (
	provider_code SERIAL PRIMARY KEY,
	name VARCHAR(40) NOT NULL,
	address VARCHAR(25) NOT NULL,
	city VARCHAR(40) NOT NULL,
	province VARCHAR(40) NOT NULL
);

CREATE TABLE IF NOT EXISTS categories (
	category_code SERIAL PRIMARY KEY,
	name VARCHAR(40) NOT NULL
);

CREATE TABLE IF NOT EXISTS parts (
	part_code SERIAL PRIMARY KEY,
	name VARCHAR(35) NOT NULL,
	color VARCHAR(20) NOT NULL,
	price NUMERIC(10,2) NOT NULL,
	category_code INT NOT NULL,
	
	FOREIGN KEY (category_code)
	REFERENCES categories(category_code)
);

CREATE TABLE IF NOT EXISTS purchase_order (
	order_id SERIAL PRIMARY KEY,
	amount INT NOT NULL,
	date DATE NOT NULL,
	time TIME WITH TIME ZONE NOT NULL,
	
	provider_code INT NOT NULL,
	part_code INT NOT NULL,
	
	FOREIGN KEY (provider_code)
	REFERENCES providers(provider_code),
	
	FOREIGN KEY (part_code)
	REFERENCES parts(part_code)
);


![Diagramas](/c@r10s/AproT/ptoyectosDevF/Imagenesproyprot)






