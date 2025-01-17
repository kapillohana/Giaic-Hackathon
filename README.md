# Giaic-Hackathon
Detailed System Architecture
User Interaction:

Browses products on the Frontend (Next.js).
Adds items to the cart and places an order.
Tracks shipment status and processes payment.
Frontend (Next.js):

Communicates with Sanity CMS to fetch product details and submit order data.
Sends requests to Third-Party APIs for shipment tracking and payment processing.
Displays responses dynamically to the user.
Sanity CMS:

Manages:
Product Data: Name, price, stock, images.
Order Records: Customer info, product details, payment status.
Provides APIs:
GET /products: Fetch product details.
POST /orders: Save new orders.
Third-Party APIs:

Shipment Tracking API:
Provides real-time shipment updates via GET /shipment.
Example Response: {"orderId":123, "status":"In Transit", "ETA":"15 mins"}.
Payment Gateway API:
Handles payment transactions via POST /payment.
Example Payload: {"amount":100, "currency":"USD", "orderId":123}.
Example Response: {"paymentStatus":"Success", "transactionId":"XYZ123"}.
Workflow Examples
Product Browsing Workflow:
User requests product data on the frontend.
Frontend fetches data via Sanity CMS API.
Product details are displayed dynamically.
Order Placement Workflow:
User adds items to the cart and proceeds to checkout.
Frontend sends order data to Sanity CMS API.
Payment is processed via Payment Gateway API.
Confirmation is displayed and recorded.
Shipment Tracking Workflow:
User queries shipment status on the frontend.
Frontend sends a request to the Shipment Tracking API.
Real-time tracking info is displayed.
