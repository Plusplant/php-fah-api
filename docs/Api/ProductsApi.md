# Swagger\Client\ProductsApi

All URIs are relative to *https://api.floraathome.nl/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**getAllProducts**](ProductsApi.md#getAllProducts) | **GET** /products/get | Returns a full list of products
[**getRecentProducts**](ProductsApi.md#getRecentProducts) | **GET** /products/recent | Return a list of products that where changed after a certain datetime


# **getAllProducts**
> \Swagger\Client\Model\InlineResponse200 getAllProducts($apitoken, $type)

Returns a full list of products

Thanks to the API link, Flora@Home gets all your customers orders automatically. Including the correct data to send the product to the customer. Flora@Home transfers this in to an order to the breeder. The breeder does not get the data from your clients, only the product that they need to deliver. Flora@Home has a REST API that enables you to exchange data with webshops.<br/><br/>We advise developers to use the v1/products/get endpoint to do a full product synchronisation once every 24 hours.<br/>The v1/products/recent endpoint can be used to get only recent product changes after a certain datetime.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\ProductsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$apitoken = "apitoken_example"; // string | Your unique API token
$type = "type_example"; // string | Choose \"json\" or \"xml\" as format for request and response data

try {
    $result = $apiInstance->getAllProducts($apitoken, $type);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ProductsApi->getAllProducts: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **apitoken** | **string**| Your unique API token |
 **type** | **string**| Choose \&quot;json\&quot; or \&quot;xml\&quot; as format for request and response data |

### Return type

[**\Swagger\Client\Model\InlineResponse200**](../Model/InlineResponse200.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getRecentProducts**
> \Swagger\Client\Model\InlineResponse2001 getRecentProducts($apitoken, $type, $fromdt)

Return a list of products that where changed after a certain datetime

Return a list of product that where added, updated or deleted after a cetain datetime. The datetime cannot be older than one week<br/><br/>We advise developers to use this endpoint in combination with /v1/products/get.<br/>The recommended practice is to do a full sync of the products every 24 hours using the /v1/products/get endpoint and use the /v1/products/recent endpoint to update your products every 15 minutes.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\ProductsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$apitoken = "apitoken_example"; // string | Your unique API token
$type = "type_example"; // string | Choose \"json\" or \"xml\" as format for request and response data
$fromdt = "fromdt_example"; // string | ISO8601 DateTime string of your last successfull sync, only products changed after fromdt will be returned.

try {
    $result = $apiInstance->getRecentProducts($apitoken, $type, $fromdt);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ProductsApi->getRecentProducts: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **apitoken** | **string**| Your unique API token |
 **type** | **string**| Choose \&quot;json\&quot; or \&quot;xml\&quot; as format for request and response data |
 **fromdt** | **string**| ISO8601 DateTime string of your last successfull sync, only products changed after fromdt will be returned. |

### Return type

[**\Swagger\Client\Model\InlineResponse2001**](../Model/InlineResponse2001.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

