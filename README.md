# newbill

CREATE TABLE customer (id int(11) NOT NULL AUTO_INCREMENT, name VARCHAR(100), sm_id VARCHAR(20),address VARCHAR(200), email VARCHAR(20), phone VARCHAR(20),PRIMARY KEY (id)); 

insert into customer (name,sm_id, address, email, phone) values ('Kumar', '1234','Address Line 1 chennai','test@test.com', '9822221110');

CREATE TABLE service_provider (provider_id int(11) NOT NULL AUTO_INCREMENT,provider_name varchar(50),PRIMARY KEY (provider_id));
insert into service_provider (provider_name) values ("TNEB");
insert into service_provider (provider_name) values ("Water Supply");
insert into service_provider (provider_name) values ("BSNL");


CREATE TABLE slab (provider_id int(11),start_reading int(11),end_reading int(11),rate DECIMAL(5,2));
insert into slab (provider_id, start_reading, end_reading, rate) values (1,0,300,1.25);
insert into slab (provider_id,start_reading, end_reading, rate) values (1,301,600,1.75);
insert into slab (provider_id,start_reading, end_reading, rate) values (1,601,1000,2.25);
insert into slab (provider_id,start_reading, end_reading, rate) values (1,1000,99999,2.75);
insert into slab (provider_id,start_reading, end_reading, rate) values (2,0,300,1);
insert into slab (provider_id,start_reading, end_reading, rate) values (2,301,600,1.50);
insert into slab (provider_id,start_reading, end_reading, rate) values (2,601,1000,2.50);
insert into slab (provider_id,start_reading, end_reading, rate) values (2,1000,99999,3.75);

CREATE TABLE customer_service (cust_id int(11),provider_id int(11),sm_id int(11),currency_type varchar(5),PRIMARY KEY (cust_id,provider_id,sm_id));


CREATE TABLE customer_invoice (invoice_id int(11) NOT NULL AUTO_INCREMENT,cust_id int(11),provider_id int(11),sm_id int(11),currency_type varchar(5),start_ts date,start_reading INTEGER(30),end_ts date,end_reading INTEGER(30),total_units INTEGER(30),calculated_amount DECIMAL(10,2),tax DECIMAL(10,2),bill_amount DECIMAL(10,2),PRIMARY KEY (invoice_id));
insert into customer_invoice (cust_id,provider_id,sm_id,currency_type,start_ts,start_reading,end_ts,end_reading,total_units,calculated_amount,tax,bill_amount) values (?,?,?,?,?,?,?,?,?,?,?,?);

insert into sm_usage (sm_id, start_ts,start_reading, end_ts, end_reading,status) values ('1234568','2015-06-30 05:00:00', '50012', '2015-06-30 05:15:00','50023',null);
insert into sm_usage (sm_id, start_ts,start_reading, end_ts, end_reading,status) values ('1234568','2015-06-30 05:32:00', '50023', '2015-06-30 05:39:00','50029',null);
insert into sm_usage (sm_id, start_ts,start_reading, end_ts, end_reading,status) values ('1234568','2015-06-30 06:09:00', '50029', '2015-06-30 06:22:00','50044',null);
insert into sm_usage (sm_id, start_ts,start_reading, end_ts, end_reading,status) values ('1234568','2015-06-30 07:10:00', '81234', '2015-06-30 09:25:00','81259',null);
insert into sm_usage (sm_id, start_ts,start_reading, end_ts, end_reading,status) values ('1234568','2015-06-30 09:45:00', '81259', '2015-06-30 11:04:00','81294',null);

http://localhost:8080/BillingSystem/rest/getBill/bysmid/1234568

https://github.com/stanleysundar/Billing.git
