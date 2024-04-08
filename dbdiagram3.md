Table Customer {
  customer_id int [pk]
  first_name varchar
  last_name varchar
  email varchar
  phone varchar
  address varchar
}

Table Order {
  order_id int [pk]
  order_date date
  status varchar [note: 'payed, canceled, pending']
  collect_schedule date
  customer_id int [ref: > Customer.customer_id]
}

Table OrderItem {
  order_item_id int [pk]
  quantity int
  price_by_unity float
  unity_value float
  unity_symbol varchar [note: 'Litre, KG, unité']
  price_asso float
  price_per_kg_asso float
  order_id int [ref: > Order.order_id]
  product_id int [ref: > CatalogItems.catalog_id]
}

Table Product {
  product_id int [pk]
  category_id int [ref: > Category.category_id]
  name varchar
  description varchar
  price_unity float
  unity_value float
  unity_symbol varchar
  price_asso float
  price_per_kg_asso float
  stock_quantity int
}

Table Category {
  category_id int [pk]
  name varchar
  description varchar
}

Table Catalog {
  catalog_id int [pk]
  store varchar
}

Table CatalogItems {
  catalog_id int [ref: > Catalog.catalog_id]
  product_id int [ref: > Product.product_id]
}