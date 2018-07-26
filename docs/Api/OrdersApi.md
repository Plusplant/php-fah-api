# Swagger\Client\OrdersApi

All URIs are relative to *https://api.floraathome.nl/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create**](OrdersApi.md#create) | **POST** /orders/create | Place an order


# **create**
> \Swagger\Client\Model\InlineResponse2002 create($apitoken, $type, $body)

Place an order

The API method gives you access to the complete assortment. If you want, as a developer, to make a connection with API, you need an API token (send to the known email address in the system). As webshop administrator, you can customize the assortment thru www.floraathome.nl. Changes in the assortment are immediately visible in the API results.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\OrdersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$apitoken = "apitoken_example"; // string | Your unique API token
$type = "type_example"; // string | Choose \"json\" or \"xml\" as format for request and response data
$body = "body_example"; // string | The order object that needs to be created and send via form-data

try {
    $result = $apiInstance->create($apitoken, $type, $body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrdersApi->create: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **apitoken** | **string**| Your unique API token |
 **type** | **string**| Choose \&quot;json\&quot; or \&quot;xml\&quot; as format for request and response data |
 **body** | **string**| The order object that needs to be created and send via form-data |

### Return type

[**\Swagger\Client\Model\InlineResponse2002**](../Model/InlineResponse2002.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: application/xml, application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

