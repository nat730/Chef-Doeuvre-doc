Table CUSTOMER {
  customer_id int [pk]
  first_name varchar
  last_name varchar
  email varchar
  phone varchar
  address varchar
}

Table ORDER {
  order_id int [pk]
  order_date varchar
  status varchar
  customer_id int [ref: > CUSTOMER.customer_id]
}

Table ORDER_ITEM {
  item_id int [pk]
  quantity int
  price float
  order_id int [ref: > ORDER.order_id]
  product_id int [ref: > PRODUCT.product_id]
}

Table PRODUCT {
  product_id int [pk]
  name varchar
  description varchar
  price float
  price_per_kg float
  price_asso float
  price_per_kg_asso float
  stock_quantity int
  category_id int [ref: > CATEGORY.category_id]
}

Table CATEGORY {
  category_id int [pk]
  name varchar
  description varchar
}


