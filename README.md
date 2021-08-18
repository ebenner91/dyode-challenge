# dyode-challenge

# DYODE. Dev Challenges

## Liquid Challenge

#### These questions should be answered with real world solutions in liquid

1. Describe how you would make a line of text in a homepage section editable from theme customization and how you would access this in liquid.
  
Answer:  This would depend on the client's needs for this section. If it's a simple line of text I would add a text field to the section schema. If they need longer text and/or need to be able to bold, italicize, or hyperlink parts of the text, I would use a richtext field. I would access my text or richtext field within the applicable element using `{{ section.settings.my_text_field }}`. When using richtext, I make sure not to contain the field in a `<p>` tag, as the `<p>` tags used within the richtext field with break the layout.
2. How would you add the collection featured image as a banner on the collection liquid template?

Answer: `<div class="collection-banner">{{ collection.featured_image | img_tag }}</div>`
3. Using liquid code and HTML, create a simple pagination container, "< 1 2 ... 5 >".
  
Answer: 
``` 
    {{ paginate | default_pagination: next: '<', previous: '>' }}
```
4. Using liquid code, access the product named "Blue T-Shirt". Store the id, title, handle, price, url, and image in variables.
  
Answer: Assuming the product handle matches the name of the product:
```
{%- liquid
 assign product = all_products['blue-t-shirt'] 
 assign productId = product.id 
 assign productTitle = product.title
 assign productPrice = product.price
 assign productUrl = product.url
 assign productImage = product.featured_image
-%}
```
5. Using liquid code, create a key:value array using the list below. Loop through the array. Upon key type, store the value in a variable to be used later:
   - fruit:apple
   - vegetable:carrot
   - cloth:t-shirt
   - denim:jeans
  
Answer: It's not possible to create an associative array in liquid, so you would need to create two separate arrays and access them in parallel. Assuming I wanted to loop through and store the value for cloth:
```
{%- liquid
    assign keysArray = "fruit,vegetable,cloth,denim" | split: ","
    assign valuesArray = "apple,carrot,t-shirt,jeans" | split: ","

    for key in keysArray
        if key == "cloth"
            assign value = valuesArray[forloop.index0]
        endif
    endfor
-%}
```


## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn serve
```

### Compiles and minifies for production
```
yarn build
```

### Lints and fixes files
```
yarn lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
