Change bold
html:{% if value == 'SUBTOTAL' %}<b><i><span style="color: black;">SUBTOTAL</span></i></b>{% else %} {{ linked_value }}{% endif %};;


group a dimension
if(${products.brand} = offset(${products.brand},-1),"",${products.brand})


get the counts for changes in the dimension

if(match(${products.brand},${products.brand})=offset(match(${products.brand},${products.brand}),-1)
      , 1+row()-match(${products.brand},${products.brand})
      , 1)

      get the subtotal
      if(
  NOT(${products.brand} = offset(${products.brand},1)),
    sum(offset_list(${order_items.total_sale_price},-(${partition_row_number}-1),${partition_row_number})),null)