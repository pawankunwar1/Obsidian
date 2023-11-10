Tip 1: -> change the price or quantity into negative values
Tip 2 -> check if something can be done during register but can be done in  edit settings
Tip 3 -> may be one coupon code twice cannot be applied but if there is two coupon code then try to add 1st and 2nd in a row
Tip 4 -> maybe we cannot add more number in `quantity` parameter and backend only allows to max 100 quantity -> we can bypass this by sending 100 request multiple times -> integer overflow
Tip 5 -> suppose if there any admin panel that can be access through only `@company.com` email -> then try to create account with large email address and check if -> in `/account` section if the long email is truncated or not -> if yes then we can do -> `portswigger lab Business logic -> ## Inconsistent handling of exceptional input`
Tip 6 -> if there is password functionality and parameter are -> `currentPassword= , newPassword1= , newPassword2= ` what if we remove -> `currentPassword=` parameter 
Tip 7 -> Response manipulation -> sometimes website send items price into cookies also and sometimes website calculate price in server side when item is added in cart.
Tip 8 -> if `/admin` or other pages are not allowed then we can bypass while the sequence of events in the login process -> `/login` -> `in response /home` -> change into -> `/admin` 
Tip 9 -> check if when offer in ecommerce website that gift card is availabe or not if yes -> then buy gift card -> enter coupon offer code -> if gift card is $10 and offer is 30% then we can by gift card by $7 and still get $10