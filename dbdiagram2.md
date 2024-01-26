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
    order_date date
    status enum
    collect_schedule date
    customer_id int [ref: > CUSTOMER.customer_id]
  }

  Table ORDER_ITEM {
    item_id int [pk]
    quantity int
    price_by_unity float
    unity_value float
    unity_symbol varchar
    price_asso float
    price_per_kg_asso float
    order_id int [ref: > ORDER.order_id]
    product_id int [ref: > PRODUCT.product_id]
  }

  Table PRODUCT {
    product_id int [pk]
    name varchar
    description varchar
    price_unity float
    unity_value float
    unity_symbol varchar
    price_asso float
    price_per_kg_asso float
    stock_quantity int
    category_id int [ref: > CATEGORY.category_id]
  }

  Table Catalog_ITEM {
    Catalog_item_id int [pk]
    quantity int
    price_unity float
    product_id int [ref: > PRODUCT.product_id]
    Catalog_id int [ref: > Catalog.Catalog_id]

  }

  Table Catalog {
    Catalog_id int [pk]
    order_date varchar
    status varchar
    }

  Table CATEGORY {
    category_id int [pk]
    name varchar
    description varchar
  }