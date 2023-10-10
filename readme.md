# Instructions for songserm.com Google Analytics Enhanced Ecommerce Datalayer

## 1- View Item

To implement the "View Item" data layer code on the specified page, you'll need to insert the following script into the HTML of that page. Make sure to replace the placeholders with actual data:

Trigger on this page view: https://www.songserm.com/booking?from=80d891af-5b84-4a4d-8f62-fe765a69e08e&to=a1338dc4-1872-42a5-beb7-cc017ba4aa73&endDate=2023-10-27&adult=1&child=0&infant=0

```html
<script>
window.dataLayer = window.dataLayer || [];
window.dataLayer.push({ ecommerce: null }); 
window.dataLayer.push({
  event: "view_item",
  ecommerce: {
    currency: "THB",
    value: 250, // Replace with the actual item price
    items: [
      {
        item_id: "SKU_OR_ID", // Replace with SKU, ID, or item name
        item_name: "Koh Samui to Koh Phangan", // Replace with the item name
        price: 250, // Replace with the actual item price
        quantity: 1 // Replace with the number of travelers
      }
    ]
  }
});
</script>
```

## 2- Add To Cart

For the "Add To Cart" event, you can implement it when a user adds an item to their cart. Typically, this involves capturing the product details when the user clicks the "Add to Cart" button. Assuming you have an HTML button with an ID like "add-to-cart-button," you can use JavaScript to capture the product details and push the data to the DataLayer. Here's a simplified example:

Trigger on the click on Choose Ticket on this page: https://www.songserm.com/booking?from=80d891af-5b84-4a4d-8f62-fe765a69e08e&to=a1338dc4-1872-42a5-beb7-cc017ba4aa73&endDate=2023-10-27&adult=1&child=0&infant=0

```html
<script>
document.getElementById("add-to-cart-button").addEventListener("click", function() {
  window.dataLayer = window.dataLayer || [];
  window.dataLayer.push({
    event: "add_to_cart",
    ecommerce: {
      currency: "THB",
      value: 250, // Replace with the actual item price
      items: [
        {
          item_id: "SKU_OR_ID", // Replace with SKU, ID, or item name
          item_name: "Koh Samui to Koh Phangan", // Replace with the item name
          price: 250, // Replace with the actual item price
          quantity: 1 // Replace with the travellers count
        }
      ]
    }
  });
});
</script>
```

## 3- Begin Checkout

To implement the "Begin Checkout" data layer code on your website, you'll need to insert the following script into the HTML of the relevant page where the checkout process begins. Make sure to replace the placeholders with actual data:

Checkout Page View: https://www.songserm.com/booking/checkout

```html
<script>
window.dataLayer = window.dataLayer || [];
window.dataLayer.push({ ecommerce: null });
window.dataLayer.push({
  event: "begin_checkout",
  ecommerce: {
    currency: "THB",
    value: 250, // Replace with the total value of the items in the cart
    items: [
      {
        item_id: "SKU_OR_ID_1", // Replace with SKU, ID, or item name for the item
        item_name: "Ticket 1", // Replace with the name of the item
        price: 100, // Replace with the price of the item
        quantity: 2 // Replace with the travellers count
      }
    ]
  }
});
</script>
```

## 4- Add Payment Info

To implement the "Add Payment Info" data layer code on your website, you'll need to insert the following script into the HTML of the relevant page where users add their payment information during the checkout process. Make sure to replace the placeholders with actual data:

Checkout page after adding the contact information https://www.songserm.com/booking/checkout or on this page view: https://songserm.nellika.co/booking/checkout/payment

```html
<script>
window.dataLayer = window.dataLayer || [];
window.dataLayer.push({ ecommerce: null });
window.dataLayer.push({
  event: "add_payment_info",
  ecommerce: {
    currency: "THB",
    value: 250, // Replace with the total value of the items in the cart
    items: [
      {
        item_id: "SKU_OR_ID_1", // Replace with SKU, ID, or item name for the item
        item_name: "Ticket 1", // Replace with the name of the item
        price: 100, // Replace with the price of the item
        quantity: 2 // Replace with the travellers count
      }
      // Add additional items if needed
    ]
  }
});
</script>
```

## 5- Purchase Complete

To implement the "Purchase" data layer code on your website, you'll need to insert the following script into the HTML of the page where the purchase is completed. Make sure to replace the placeholders with actual data:

Trigger on the thank you page: https://songserm.nellika.co/process?paidType=STRIPE&status=SUCCESS&reference=PUQV23103101&token=cs_test_a15nM0HuDi1KFrZxPSSaYuTeXRyY2h3NAQkkqvSGpRnRgFYH4uVcbbfzTx

```html
<script>
window.dataLayer = window.dataLayer || [];
window.dataLayer.push({ ecommerce: null });
window.dataLayer.push({
  event: "purchase",
  ecommerce: {
    currency: "THB",
    value: 250, // Replace with the total value of the purchase
    transaction_id: "12345", // Replace with a unique transaction ID
    affiliation: "songserm.com",
    items: [
      {
        item_id: "SKU_OR_ID_1", // Replace with SKU, ID, or item name for the item
        item_name: "Ticket 1", // Replace with the name of the item
        price: 100, // Replace with the price of the item
        quantity: 2 // Replace with the travellers count
      }
      // Add additional items as needed
    ]
  }
});
</script>
```

