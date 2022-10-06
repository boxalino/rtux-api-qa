We provide here the reference materials for QA in regards of the Boxalino Narrative REST API.

See detailed documentation here: https://boxalino.atlassian.net/wiki/spaces/BPKB/pages/8749643/Narrative+API+-+Technical+Reference

In the curl-requests folder, you will find typical API requests for the most common request cases.

They all start with the 3 parameters:

    "username": "[ACCOUNT]",
    "apiKey": "[API_KEY]",
    "apiSecret": "[API_SECRET]"

Which you need to replace with your credentials.

They all have:

    "dev": false,
    "test": false
	
You might want to do QA on the non-published version of your configuration (test:true) or on your dev data (dev:true)

The all have:

    "sessionId": "e8097b6a-6b25-441e-97eb-2c51cdb80f33",
    "profileId": "5d508aec-30ea-42bb-9111-bbd24526a46d",
    "customerId": null,
	
and the profileId URL parameter matching "5d508aec-30ea-42bb-9111-bbd24526a46d". You might want to set other values in case you want to test specific personalization cases.

They typically have:

    "hitCount": "10",
    "offset": "0",
    "language": "de",
    "groupBy": "products_group_id",
    "returnFields": [
        "selected_title",
        "selected_sales_price",
        "selected_list_price",
        "selected_link",
        "selected_image"
    ],
    "facets": [],
    "sort": [],
    "parameters": []
	
WARNING: the selcted fields (described here: https://boxalino.atlassian.net/wiki/spaces/BPKB/pages/856129551/Selected+fields+Render+products+without+database+look-up)
only exists if you are using the Data API of Boxalino for your products: https://boxalino.atlassian.net/wiki/spaces/BPKB/pages/252149870/doc_product

The files follow the pattern to have the name of the widget first and, optionally some use-case of parameters after with a '-' between.

For example, for search with no results: 'search-no results.json'.

The file all have the curl format as exported from Postman: https://www.postman.com/