import codecademylib
import pandas as pd

inventory = pd.read_csv('inventory.csv')
print(inventory.head(10))

staten_island = inventory.iloc[:10] # first 10 columns saved as staten island.

product_request = staten_island.product_description # product description from variable state_island.

seed_request = inventory[(inventory.location == 'Brooklyn') & (inventory.product_type == 'seeds')]

in_stock = lambda row: 'True' \
	if row['quantity'] > 0 \
  else 'False'
  
inventory.in_stock = inventory.apply(in_stock, axis = 1)

total_value = inventory.price * inventory.quantity

inventory['total_value'] = total_value

combine_lambda = lambda row: \
	'{} - {}'.format(row.product_type,
                  row.product_description)
inventory['full_description'] = inventory.apply(combine_lambda, axis = 1)
