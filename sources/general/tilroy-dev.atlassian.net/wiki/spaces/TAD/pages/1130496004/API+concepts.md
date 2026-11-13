# Source: https://tilroy-dev.atlassian.net/wiki/spaces/TAD/pages/1130496004/API+concepts

Tilroy API documentation

/

API concepts

[Updated Dec 02, 2025](https://tilroy-dev.atlassian.net/wiki/spaces/TAD/history/1130496004)

- Anonymous Fish

More actions

# API concepts

![](https://tilroy-dev.atlassian.net/wiki/aa-avatar/557058:9e831523-ee3d-43f8-863a-c67bcf872b0a)

By Wannes Van der Gucht

2 min

Add a reaction

# Types of endpoints

We have 3 types of endpoints available that serve different purposes

## 1\. **Importing Data into Tilroy**

- **Asynchronous**

- Uses `/import` endpoints

During import, the data provided is validated by Tilroy. If the message does not meet the requirements, the API will return a validation error. It is the responsibility of the implementing party to handle these errors and ensure proper monitoring is in place.

Once a message is accepted (with a **202 OK**), Tilroy takes over the further processing and monitoring. The processing speed depends on the type of message and the current system load. During peak times, delays may occur.

## 2\. **Exporting Tilroy Data**

- **Asynchronous**

- **Near real-time**

- Uses `/export` endpoints

Every time an order, transfer, sale, etc. is updated, a message is generated and made available via the export endpoint. By using `dateExported` and the filter on `dateExportedSince`, new or updated objects since last export can be fetched.

The response is paginated and contains by default 10 items per page. By using the `count` parameter you can increase it to up to 100 items per page.

Open image-20251113-172516.png

These exports function as a kind of feed to pull data into your system for further processing. Messages remain available through the export endpoints for **14 days** by default.

### How to work with the export endpoint

The goal of the export endpoint is to allow you to fetch the changed data from Tilroy and process it in your system.

We advise pulling messages into your system and storing them before processing. This decouples retrieving data from the feed from processing, which may take longer.

## 3\. **Synchronous APIs on Tilroy Data**

- Direct interaction with Tilroy data to retrieve, create, or update information

- Primarily used for **real-time integrations**, such as external webshops

Examples of synchronous APIs:

- **Customer API** – for customer data

- **Voucher API** – for creating or redeeming (gift) vouchers and managing loyalty

- **Basket API** – for manipulating shopping baskets to can get processed as orders or transactions in Tilroy

These endpoints suit applications needing immediate access to current data, such as custom webshops using Tilroy as a backend.

Collapse action bar

View all comments

Open Details Panel

Remix page

Open Rovo Chat

Add a comment

Add a reaction