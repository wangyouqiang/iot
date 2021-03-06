# GetDeviceStatus {#reference_zdy_wqz_wdb .reference}

You can call this operation to view the running status of a specified device.

## Request parameters {#section_ujp_1gm_xdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes|The operation that you want to perform. Set the value to GetDeviceStatus.|
|IotId|String|No| The identifier of the specified device.

 **Note:** If you use this parameter, ProductKey and DeviceName are not required. IotId is a globally unique identifier \(GUID\), and corresponds to a combination of ProductKey and DeviceName. If you use both IotId and the combination of ProductKey and DeviceName, the system follows IotId.

 |
|ProductKey|String|No| Specifies the product key of the specified device.

 **Note:** If you use this parameter, DeviceName is required.

 |
|DeviceName|String|No| The name of the specified device.

 **Note:** If you use this parameter, ProductKey is required.

 |

## Response parameters {#section_dtb_mgm_xdb .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The GUID generated by Alibaba Cloud for the request.|
|Success|Boolean|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.|
|ErrorMessage|String|The error message returned when the call fails.|
|Data|DeviceStatusInfo|The device status returned when the call is successful. For more information, see [DeviceStatusInfo](#table_glr_1hm_xdb).|

|Name|Type|Description|
|:---|:---|:----------|
|Status|String| The status of the specified device. Values include:

 online: The online status.

 offline: The offline status.

 unactive: Indicates that the specified device has not been activated.

 disable: Indicates that the specified device has been disabled.

 |

## Examples {#section_e2g_mhm_xdb .section}

**Request example**

```
https://iot.cn-shanghai.aliyuncs.com/?Action=GetDeviceStatus
 &IotId=MpEKNuEUJzIORNANAWJX0010929900*****
 &<common request parameters>
```

**Response example**

-   JSON format

    ```
    {
      "RequestId":"57b144cf-09fc-4916-a272-a62902d5b207",
      "Success": true
      "Data": {
        "Status": "unactive"
      } 
    }
    ```

-   XML format

    ```
    <? xml version='1.0' encoding='utf-8'? >
    <GetDeviceStatusResponse>
        <RequestId>57b144cf-09fc-4916-a272-a62902d5b207</RequestId>
        <Success>true</Success>
        <Data>
            <Status>unactive</Status>
        </Data>
    </GetDeviceStatusResponse>
    ```


