create time: 2022-07-08

# User API v0.7.8

## POST /v1.0/api/user/login

POST /v1.0/api/user/login

> Body request parameter

```Plaintext
{
  "username": "username",
  "password": "password",
  "service": "https://url.com"
}
```

### request parameter

| name       | location | type   | necessary | description                      |
| ---------- | -------- | ------ | --------- | -------------------------------- |
| body       | body     | object | no        | none                             |
| » username | body     | string | yes       | Username                         |
| » password | body     | string | yes       | Password                         |
| » service  | body     | string | yes       | The address of the logon request |

> return example

### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

### return structure

## GET /v1.0/api/user/logout

GET /v1.0/api/user/logout

### request parameter

| name  | location | type   | description |
| ----- | -------- | ------ | ----------- |
| email | query    | string | Email       |
| rzpj  | header   | string | Certificate |

> return example

### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

### return structure

## GET /v1.0/api/user

GET /v1.0/api/user

### request parameter

| name | location | type   | description |
| ---- | -------- | ------ | ----------- |
| rzpj | header   | string | Certificate |

> return example

> success

```Plaintext
{
  "id": "f703a998-d0fc-45d7-8d49-f468ffd913de",
  "username": "apidocs",
  "email": "876012439@qq.com",
  "firstName": "Time",
  "lastName": "Deep",
  "status": "NORMAL",
  "createTime": 1650274106201,
  "updateTime": 1650274106201
}
```

### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

### return structure

status code **200**

| name         | type    | constraint | description |
| ------------ | ------- | ---------- | ----------- |
| » id         | string  | none       | UID         |
| » username   | string  | none       | Username    |
| » email      | string  | none       | Email       |
| » firstName  | string  | none       | First name  |
| » lastName   | string  | none       | Last name   |
| » status     | string  | none       | Status      |
| » createTime | integer | none       | Created     |
| » updateTime | integer | none       | Update      |

## **POST /v1.0/user/register**

POST /v1.0/user/register

> Body request parameter

```Plaintext
{
  "username": "lgq_test",
  "password": "Aaaaaaa1",
  "confirmPassword": "Aaaaaaa1",
  "firstName": "li",
  "lastName": "gaoqiang",
  "email": "2085860762@qq.com",
  "captcha": "927624",
  "phone": "15397182393",
  "country": "China",
  "affiliation": "Education",
  "organization": "Zhejiang university",
  "userType": "Public User",
  "industry": "Physical Oceanography"
}
```

### request parameter

| name              | location | type   | necessary | description |
| ----------------- | -------- | ------ | --------- | ----------- |
| body              | body     | object | no        | none        |
| » username        | body     | string | yes       | none        |
| » password        | body     | string | yes       | none        |
| » confirmPassword | body     | string | yes       | none        |
| » firstName       | body     | string | yes       | none        |
| » lastName        | body     | string | yes       | none        |
| » email           | body     | string | yes       | none        |
| » captcha         | body     | string | yes       | none        |
| » affiliation     | body     | string | yes       | none        |
| » organization    | body     | string | yes       | none        |
| » userType        | body     | string | yes       | none        |
| » industry        | body     | string | yes       | none        |

> return example

### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

### return structure

## **POST /v1.0/user/mail/captcha**

POST /v1.0/user/mail/captcha

> Body request parameter

```Plaintext
{
  "email": "2757412961@qq.com"
}
```

### request parameter

| name    | location | type   | necessary | description |
| ------- | -------- | ------ | --------- | ----------- |
| rzpj    | header   | string | no        | none        |
| body    | body     | object | no        | none        |
| » email | body     | string | yes       | none        |

> return example

### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

### return structure

# Data Hub API v0.7.8

## DataAtom

### GET /v1.0/api/data-central/atom/{uid}

GET /v1.0/api/data-central/atom/{uid}

Query DataAtom by uid

#### request parameter

| name | location | type   | necessary | description  |
| ---- | -------- | ------ | --------- | ------------ |
| uid  | path     | string | yes       | DataAtom UID |
| rzpj | header   | string | no        | Certificate  |

> return example

> http success

```Plaintext
{
  "code": 200,
  "message": "success",
  "data": {
    "id": 1,
    "uid": "7fd6e867-54a3-46f3-9869-290097de74ce",
    "name": "http_reconstruct_coastline",
    "dataType": "JSON",
    "atomType": "HTTP",
    "userId": "ADMIN",
    "privilege": "PUBLIC",
    "status": "HEALTHY",
    "isOfficial": 1,
    "browseGraph": "http://ip:port/static/reconstruct-coastlines.png",
    "keyword": "paleogeography",
    "description": "description",
    "taskId": null,
    "boundaryWKT": null,
    "coordinateReference": null,
    "projection": null,
    "space": {
      "type": null,
      "resolution": "500m",
      "elevation": null,
      "extent": {
        "minX": -180,
        "maxX": 180,
        "minY": -90,
        "maxY": 90
      },
      "geoIdentifier": null
    },
    "temporal": {
      "geologicTime": null,
      "geologicAge": null,
      "base": 760,
      "top": 0,
      "gtsVersion": null
    },
    "fields": [
      {
        "type": "FLOAT",
        "fieldName": "time",
        "description": "time"
      },
      {
        "type": "VARCHAR",
        "fieldName": "model",
        "description": "models of reconstruct: ['SCOTESE&WRIGHT2018', 'SETON2012', 'PEHRSSON2015', 'DOMEIER2014', 'MATTHEWS2016_pmag_ref', 'MATTHEWS2016_mantle_ref', 'MATTHEWS2016', 'VH_VDM', 'GOLONKA', 'RODINIA2013', 'PALEOMAP', 'MULLER2016']"
      }
    ],
    "intellectualProp": null,
    "license": null,
    "discipline": "/",
    "authorName": null,
    "authorMail": null,
    "doi": null,
    "associatedResource": null,
    "associatedResourceUrl": null,
    "createTime": 1648795083357,
    "updateTime": 1648795457805,
    "httpDpMeta": {
      "dpAddress": "14F3D2D7A4021000",
      "security": {
        "useTls": false
      },
      "transfer": {
        "endpoint": [
          "ip:port/reconstruct/coastlines"
        ],
        "protocol": "http"
      },
      "httpRoute": {
        "contentType": "application/json",
        "method": "GET"
      }
    }
  }
}
```

#### return result

| status code | status code message                                     | description  | data mode |
| ----------- | ------------------------------------------------------- | ------------ | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | http success | Inline    |

#### return structure

status code **200**

| name                     | type     | constraint | description                                                  |
| ------------------------ | -------- | ---------- | ------------------------------------------------------------ |
| » code                   | integer  | none       | Status Code                                                  |
| » message                | string   | none       | Status Information                                           |
| » data                   | object   | none       | DataAtom Information                                         |
| »» id                    | integer  | none       | DataAtom ID                                                  |
| »» uid                   | string   | none       | DataAtom UID                                                 |
| »» name                  | string   | none       | Unit name                                                    |
| »» dataType              | string   | none       | Data type,Value = FILE, TABLE, JSON, PICTURE..               |
| »» atomType              | string   | none       | Metadata type,Value = LAYER_SERVICE,HTTP,JDBC,MYSQL,POSTGRESQL |
| »» userId                | string   | none       | none                                                         |
| »» privilege             | string   | none       | AccessPermission,Value= public, private                      |
| »» status                | string   | none       | Access Status,Value = SETTING,HEALTHY, UNHEALTHY             |
| »» isOfficial            | integer  | none       | Is it official                                               |
| »» browseGraph           | string   | none       | Browse Graph                                                 |
| »» keyword               | string   | none       | Keyword                                                      |
| »» description           | string   | none       | Description                                                  |
| »» taskId                | null     | none       | Taskid                                                       |
| »» boundaryWKT           | null     | none       | The range of the query space, which is returned in WKT format. |
| »» coordinateReference   | null     | none       | coordinate Reference                                         |
| »» projection            | null     | none       | Projection coordinate system                                 |
| »» space                 | object   | none       | Spatial Information                                          |
| »»» type                 | null     | none       | Type                                                         |
| »»» resolution           | string   | none       | Spatial resolution                                           |
| »»» elevation            | null     | none       | Elevation                                                    |
| »»» extent               | object   | none       | extent                                                       |
| »»»» minX                | integer  | none       | Minimum x                                                    |
| »»»» maxX                | integer  | none       | Maximum x                                                    |
| »»»» minY                | integer  | none       | Minimum y                                                    |
| »»»» maxY                | integer  | none       | Maximum y                                                    |
| »»» geoIdentifier        | null     | none       | GeoIdentifier                                                |
| »» temporal              | object   | none       | Time                                                         |
| »»» geologicTime         | null     | none       | Geologic time，e.g, Quaternary                               |
| »»» geologicAge          | null     | none       | Geological age，e.g,1，100 to 200.2                          |
| »»» base                 | integer  | none       | The earliest possible time point，e.g,150.3                  |
| »»» top                  | integer  | none       | The latest possible time t，e.g,10.2                         |
| »»» gtsVersion           | null     | none       | Geological Age version，e.g,INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05 |
| »» fields                | [object] | none       | Field Information                                            |
| »»» type                 | string   | none       | Field type，Value = INT, FLOAT, DOUBLE, BOOLEAN, COLUMNNAME, GEOMETRY, VARCHAR |
| »»» fieldName            | string   | none       | Fieldname                                                    |
| »»» description          | string   | none       | Description                                                  |
| »» intellectualProp      | null     | none       | IntellectualProp                                             |
| »» license               | null     | none       | license                                                      |
| »» discipline            | string   | none       | Discipline                                                   |
| »» authorName            | null     | none       | Author name                                                  |
| »» authorMail            | null     | none       | Author email                                                 |
| »» doi                   | null     | none       | The unique identifier of the data object                     |
| »» associatedResource    | null     | none       | Associated resources                                         |
| »» associatedResourceUrl | null     | none       | Link                                                         |
| »» createTime            | integer  | none       | Created                                                      |
| »» updateTime            | integer  | none       | Update Time                                                  |
| »» httpDpMeta            | object   | none       | Data center information                                      |
| »»» dpAddress            | string   | none       | DpAddress                                                    |
| »»» security             | object   | none       | Encrypted information                                        |
| »»»» useTls              | boolean  | none       | TLS encryption                                               |
| »»» transfer             | object   | none       | Transfer information                                         |
| »»»» endpoint            | [string] | none       | Endpoint                                                     |
| »»»» protocol            | string   | none       | Data source protocol                                         |
| »»» httpRoute            | object   | none       | HTTP Route                                                   |
| »»»» contentType         | string   | none       | Content Type                                                 |
| »»»» method              | string   | none       | Request Mode                                                 |

### POST /v1.0/api/data-central/atom/list/user

POST /v1.0/api/data-central/atom/list/user

Enter a field to obtain the list of DataAtom belonging to the user

#### request parameter

| name           | location | type   | necessary | description                                                  |
| -------------- | -------- | ------ | --------- | ------------------------------------------------------------ |
| page           | query    | string | no        | In the previous page, if you want to display the first page, use 0 |
| pageSize       | query    | string | no        | Number of Entries displayed per page                         |
| spatialWkt     | query    | string | no        | Enter wkt as the spatial query and return the boundaryWKT. If you do not specify this parameter, you will not be added to the spatial query. |
| top            | query    | string | no        | Maximum time range for querying data                         |
| base           | query    | string | no        | Minimum time range for querying data                         |
| datasetId      | query    | string | no        | Dataset ID                                                   |
| keyword        | query    | string | no        | Keyword                                                      |
| startTimestamp | query    | string | no        | Start time                                                   |
| endTimestamp   | query    | string | no        | End time                                                     |
| status         | query    | string | no        | Access Status,Value = [SETTING, HEALTHY, UNHEALTHY, LAYERED] |
| atomType       | query    | string | no        | Atom Type, Value = [BASE, JDBC, HTTP, LAYER_SERVICE, POSTGRESQL, MYSQL] |
| dataType       | query    | string | no        | DataType，Value = FILE, TABLE, JSON, PICTURE, VECTOR, RASTER |
| rzpj           | header   | string | yes       | Certificate                                                  |

> return example

> success

```Plaintext
{
    "code": 200,
    "message": "success",
    "data": {
        "total": 1,
        "list": [
            {
                "uid": "cac31bc3-71ea-4fcd-a825-8ef291a37d9e",
                "name": "OneSediment Detrital Zicron Data",
                "dataType": "TABLE",
                "atomType": "JDBC",
                "privilege": "PRIVATE",
                "status": "HEALTHY",
                "isOfficial": 0,
                "browseGraph": "dde.jpg",
                "keyword": "Detrital Zicron, Sediment",
                "description": "Detrital Zicron Data From OneSediment",
                "coordinateReference": "WGS84",
                "projection": "Equirectangular",
                "authorName": "DDE",
                "authorMail": "DDE@dde.org",
                "doi": "",
                "associatedResource": "The Global Detrital Zircon Database: Quantifying the Timing and Rate of Crustal Growth",
                "associatedResourceURL": "http://hdl.handle.net/10919/27785",
                "space": {
                    "type": "TextTable",
                    "resolution": "",
                    "extent": {
                        "minX": -180,
                        "maxX": 180,
                        "minY": 90,
                        "maxY": -90
                    }
                },
                "temporal": {
                    "geologicTime": "",
                    "geologicAge": "",
                    "gtsVersion": "International 2016 chart",
                    "base": 750,
                    "top": 0
                },
                "fields": [
                    {
                        "fieldName": "ref_no",
                        "type": "VARCHAR",
                        "description": "reference number of zicron detrital"
                    },
                    {
                        "fieldName": "lead_author",
                        "type": "VARCHAR",
                        "description": "lead author of reference paper"
                    }
                ],
                "httpDpMeta": {
                    "transfer": {
                        "protocol": "http",
                        "endpoint": [
                            "ip:port/reconstruct/coastlines"
                        ]
                    },
                    "security": {
                        "useTls": false
                    },
                    "httpRoute": {
                        "contentType": "application/json",
                        "method": "GET"
                    }
                }
            }
        ]
    }
}
```

#### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

#### return structure

status code **200**

| name                     | type     | constraint | description                                                  |
| ------------------------ | -------- | ---------- | ------------------------------------------------------------ |
| » code                   | integer  | none       | Status Code                                                  |
| » message                | string   | none       | Status Information                                           |
| » data                   | object   | none       | DataAtom Information                                         |
| »» id                    | integer  | none       | DataAtom ID                                                  |
| »» uid                   | string   | none       | DataAtom UID                                                 |
| »» name                  | string   | none       | Unit name                                                    |
| »» dataType              | string   | none       | Data type,Value = FILE, TABLE, JSON, PICTURE..               |
| »» atomType              | string   | none       | Metadata type,Value = LAYER_SERVICE,HTTP,JDBC,MYSQL,POSTGRESQL |
| »» userId                | string   | none       | Userid                                                       |
| »» privilege             | string   | none       | AccessPermission,Value= public, private                      |
| »» status                | string   | none       | Access Status,Value = SETTING,HEALTHY, UNHEALTHY             |
| »» isOfficial            | integer  | none       | Is it official                                               |
| »» browseGraph           | string   | none       | Browse Graph                                                 |
| »» keyword               | string   | none       | Keyword                                                      |
| »» description           | string   | none       | Description                                                  |
| »» taskId                | null     | none       | Taskid                                                       |
| »» boundaryWKT           | null     | none       | The range of the query space, which is returned in WKT format. |
| »» coordinateReference   | null     | none       | coordinate Reference                                         |
| »» projection            | null     | none       | Projection coordinate system                                 |
| »» space                 | object   | none       | Spatial Information                                          |
| »»» type                 | null     | none       | Type                                                         |
| »»» resolution           | string   | none       | Spatial resolution                                           |
| »»» elevation            | null     | none       | Elevation                                                    |
| »»» extent               | object   | none       | extent                                                       |
| »»»» minX                | integer  | none       | Minimum x                                                    |
| »»»» maxX                | integer  | none       | Maximum x                                                    |
| »»»» minY                | integer  | none       | Minimum y                                                    |
| »»»» maxY                | integer  | none       | Maximum y                                                    |
| »»» geoIdentifier        | null     | none       | GeoIdentifier                                                |
| »» temporal              | object   | none       | Time                                                         |
| »»» geologicTime         | null     | none       | Geologic time，e.g, Quaternary                               |
| »»» geologicAge          | null     | none       | Geological age，e.g,1，100 to 200.2                          |
| »»» base                 | integer  | none       | The earliest possible time point，e.g,150.3                  |
| »»» top                  | integer  | none       | The latest possible time t，e.g,10.2                         |
| »»» gtsVersion           | null     | none       | Geological Age version，e.g,INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05 |
| »» fields                | [object] | none       | Field Information                                            |
| »»» type                 | string   | none       | Field type，Value = INT, FLOAT, DOUBLE, BOOLEAN, COLUMNNAME, GEOMETRY, VARCHAR |
| »»» fieldName            | string   | none       | Fieldname                                                    |
| »»» description          | string   | none       | Description                                                  |
| »» intellectualProp      | null     | none       | IntellectualProp                                             |
| »» license               | null     | none       | license                                                      |
| »» discipline            | string   | none       | Discipline                                                   |
| »» authorName            | null     | none       | Author name                                                  |
| »» authorMail            | null     | none       | Author email                                                 |
| »» doi                   | null     | none       | The unique identifier of the data object                     |
| »» associatedResource    | null     | none       | Associated resources                                         |
| »» associatedResourceUrl | null     | none       | Link                                                         |
| »» createTime            | integer  | none       | Created                                                      |
| »» updateTime            | integer  | none       | Update Time                                                  |
| »» httpDpMeta            | object   | none       | Data center information                                      |
| »»» dpAddress            | string   | none       | DpAddress                                                    |
| »»» security             | object   | none       | Encrypted information                                        |
| »»»» useTls              | boolean  | none       | TLS encryption                                               |
| »»» transfer             | object   | none       | Transfer information                                         |
| »»»» endpoint            | [string] | none       | Endpoint                                                     |
| »»»» protocol            | string   | none       | Data source protocol                                         |
| »»» httpRoute            | object   | none       | HTTP Route                                                   |
| »»»» contentType         | string   | none       | Content Type                                                 |
| »»»» method              | string   | none       | Request Mode                                                 |

### POST /v1.0/api/data-central/atom/list/public

POST /v1.0/api/data-central/atom/list/public

Obtains a list of public DataAtom

#### request parameter

| name           | location | type   | necessary | description                                                  |
| -------------- | -------- | ------ | --------- | ------------------------------------------------------------ |
| page           | query    | string | no        | In the previous page, if you want to display the first page, use 0 |
| pageSize       | query    | string | no        | Number of Entries displayed per page                         |
| spatialWkt     | query    | string | no        | Enter wkt as the spatial query and return the boundaryWKT. If you do not specify this parameter, you will not be added to the spatial query. |
| top            | query    | string | no        | Maximum time range for querying data                         |
| base           | query    | string | no        | Minimum time range for querying data                         |
| datasetId      | query    | string | no        | Dataset ID                                                   |
| keyword        | query    | string | no        | Keyword                                                      |
| startTimestamp | query    | string | no        | Start time                                                   |
| endTimestamp   | query    | string | no        | End time                                                     |
| status         | query    | string | no        | [SETTING, HEALTHY, UNHEALTHY, LAYERED]                       |
| path           | query    | string | no        | Directory path                                               |
| atomType       | query    | string | no        | Atom Type,Value= [BASE, JDBC, HTTP, LAYER_SERVICE, POSTGRESQL, MYSQL] |
| dataType       | query    | string | no        | DataType，Value = FILE, TABLE, JSON, PICTURE, VECTOR, RASTER |
| rzpj           | header   | string | no        | Certificate                                                  |

> return example

> success

```Plaintext
{
  "code": 200,
  "message": "success",
  "content": {
    "total": 2,
    "dataAtoms": [
      {
        "id": 1,
        "uid": "77cc1c2f-2da2-464c-8aed-83c955dcf18f",
        "name": "layer",
        "dataType": "TABLE",
        "atomType": "LAYER_SERVICE",
        "userId": "ADMIN",
        "privilege": "PUBLIC",
        "status": "HEALTHY",
        "isOfficial": 1,
        "browseGraph": "dde.jpg",
        "keyword": "dde",
        "taskId": 0,
        "coordinateReference": null,
        "projection": null,
        "space": {
          "type": null,
          "resolution": "500m",
          "elevation": null,
          "extent": {
            "minX": 0,
            "maxX": 90,
            "minY": 0,
            "maxY": 50
          },
          "geoIdentifier": null
        },
        "temporal": {
          "geologicTime": "Neoproterozoic and Phanerozoic",
          "geologicAge": "None",
          "base": 150,
          "top": 10,
          "gtsVersion": "International 2016 chart"
        },
        "fields": [
          {
            "type": "VARCHAR",
            "fieldName": "name",
            "description": "null"
          }
        ],
        "createTime": 1646922764937,
        "updateTime": 1646922764937
      },
      {
        "id": 2,
        "uid": "65bf0a0d-a04a-466a-86a7-d70e391e82c3",
        "name": "jdbc",
        "dataType": "TABLE",
        "atomType": "JDBC",
        "userId": "ADMIN",
        "privilege": "PUBLIC",
        "status": "HEALTHY",
        "isOfficial": 1,
        "browseGraph": "dde.jpg",
        "keyword": "dde",
        "taskId": 0,
        "coordinateReference": null,
        "projection": null,
        "space": {
          "type": null,
          "resolution": "500m",
          "elevation": null,
          "extent": {
            "minX": 0,
            "maxX": 90,
            "minY": 0,
            "maxY": 50
          },
          "geoIdentifier": null
        },
        "temporal": {
          "geologicTime": "Neoproterozoic and Phanerozoic",
          "geologicAge": "None",
          "base": 150,
          "top": 10,
          "gtsVersion": "International 2016 chart"
        },
        "fields": [
          {
            "type": "VARCHAR",
            "fieldName": "name",
            "description": "null"
          }
        ],
        "createTime": 1646921724886,
        "updateTime": 1646922066159
      }
    ]
  }
}
```

#### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

#### return structure

status code **200**

| name                    | type     | constraint | description                                                  |
| ----------------------- | -------- | ---------- | ------------------------------------------------------------ |
| » code                  | integer  | none       | Status Code                                                  |
| » message               | string   | none       | Status Information                                           |
| » content               | object   | none       | Data Content                                                 |
| »» total                | integer  | none       | Data Records                                                 |
| »» dataAtoms            | [object] | none       | Metadata information                                         |
| »»» id                  | integer  | none       | DataAtom ID                                                  |
| »»» uid                 | string   | none       | DataAtom UID                                                 |
| »»» name                | string   | none       | Unit name                                                    |
| »»» dataType            | string   | none       | Data type,Value = FILE, TABLE, JSON, PICTURE..               |
| »»» atomType            | string   | none       | Metadata type,Value = LAYER_SERVICE,HTTP,JDBC,MYSQL,POSTGRESQL |
| »»» userId              | string   | none       | Userid                                                       |
| »»» privilege           | string   | none       | AccessPermission,Value= public, private                      |
| »»» status              | string   | none       | Access Status,Value = SETTING,HEALTHY, UNHEALTHY             |
| »»» isOfficial          | integer  | none       | is it Official                                               |
| »»» browseGraph         | string   | none       | Browse Graph                                                 |
| »»» keyword             | string   | none       | Keyword                                                      |
| »»» taskId              | integer  | none       | TaskId                                                       |
| »»» coordinateReference | null     | none       | coordinate Reference                                         |
| »»» projection          | null     | none       | Projection coordinate system                                 |
| »»» space               | object   | none       | Spatial Information                                          |
| »»»» type               | null     | none       | Type                                                         |
| »»»» resolution         | string   | none       | Spatial resolution                                           |
| »»»» elevation          | null     | none       | Elevation                                                    |
| »»»» extent             | object   | none       | extent                                                       |
| »»»»» minX              | integer  | none       | Minimum x                                                    |
| »»»»» maxX              | integer  | none       | Maximum x                                                    |
| »»»»» minY              | integer  | none       | Minimum y                                                    |
| »»»»» maxY              | integer  | none       | Maximum y                                                    |
| »»»» geoIdentifier      | null     | none       | GeoIdentifier                                                |
| »»» temporal            | object   | none       | Time                                                         |
| »»»» geologicTime       | string   | none       | Geologic time，e.g, Quaternary                               |
| »»»» geologicAge        | string   | none       | Geological age，e.g,1，100 to 200.2                          |
| »»»» base               | integer  | none       | The earliest possible time point，e.g,150.3                  |
| »»»» top                | integer  | none       | The latest possible time t，e.g,10.2                         |
| »»»» gtsVersion         | string   | none       | Geological Age version，e.g,INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05 |
| »»» fields              | [object] | none       | Field Information                                            |
| »»»» type               | string   | none       | Field type，Value = INT, FLOAT, DOUBLE, BOOLEAN, COLUMNNAME, GEOMETRY, VARCHAR |
| »»»» fieldName          | string   | none       | Fieldname                                                    |
| »»»» description        | string   | none       | Description                                                  |
| »»» createTime          | integer  | none       | Created                                                      |
| »»» updateTime          | integer  | none       | Update time                                                  |

### POST /v1.0/api/data-central/atom/raster/layer

POST /v1.0/api/data-central/atom/raster/layer

Enter Fields to publish raster data with one click

#### request parameter

| name     | location | type   | necessary | description    |
| -------- | -------- | ------ | --------- | -------------- |
| path     | query    | string | yes       | Data directory |
| atomName | query    | string | no        | Atom name      |
| rzpj     | header   | string | yes       | Certificate    |
| keyword  | query    | string | no        | Keyword        |

> return example

> success

```Plaintext
{
  "code": 200,
  "message": "success",
  "data": {
    "uid": "0ffda1a7-e984-4145-9b1b-981162982162"
  }
}
```

#### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

#### return structure

status code **200**

| name      | type    | constraint | description          |
| --------- | ------- | ---------- | -------------------- |
| » code    | integer | none       | Status Code          |
| » message | string  | none       | Status Information   |
| » data    | object  | none       | DataAtom Information |
| »» uid    | string  | none       | DataAtom UID         |

### POST /v1.0/api/data-central/atom/http

POST /v1.0/api/data-central/atom/http

Enter a field to add an http DataAtom

> Body request parameter

```Plaintext
{
    "name": "Deep Marine Drilling Data",
    "dataType": "JSON",
    "atomType": "HTTP",
    "privilege": "PUBLIC",
    "status": "HEALTHY",
    "description": "Spatital Distribution of International Ocean Drilling Data",
    "browseGraph": "http://ip:port/static/reconstruct-coastlines.png",
    "keyword": "IODP, Drilling, Spatial Distribution",
    "space": {
        "extent": {
            "minX": -180.0,
            "maxX": 180.0,
            "minY": -90.0,
            "maxY": 90.0
        }
    },
    "temporal": {
        "base": 0.0,
        "top": 0.0
    },
    "fields": [
        {
            "fieldName": "time",
            "type": "FLOAT",
            "description": "time"
        },
        {
            "fieldName": "model",
            "type": "VARCHAR",
            "description": "models of reconstruct: ['SCOTESE&WRIGHT2018', 'SETON2012', 'PEHRSSON2015', 'DOMEIER2014', 'MATTHEWS2016_pmag_ref', 'MATTHEWS2016_mantle_ref', 'MATTHEWS2016', 'VH_VDM', 'GOLONKA', 'RODINIA2013', 'PALEOMAP', 'MULLER2016']"
        }
    ],
    "httpDpMeta": {
        "transfer": {
            "protocol": "http",
            "endpoint": [
                "ip/static/holes.json"
            ]
        },
        "security": {
            "useTls": false
        },
        "httpRoute": {
            "contentType": "application/json",
            "method": "GET"
        }
    }
}
```

#### request parameter

| name                    | location | type     | necessary | description                                                  |
| ----------------------- | -------- | -------- | --------- | ------------------------------------------------------------ |
| rzpj                    | header   | string   | yes       | Certificate                                                  |
| body                    | body     | object   | no        | none                                                         |
| » name                  | body     | string   | yes       | Unit name                                                    |
| » dataType              | body     | string   | no        | Data type,Value = FILE, TABLE, JSON, PICTURE..               |
| » atomType              | body     | string   | yes       | Metadata type,Value = LAYER_SERVICE,HTTP,JDBC,MYSQL,POSTGRESQL |
| » userId                | body     | string   | yes       | UserId                                                       |
| » privilege             | body     | string   | yes       | AccessPermission,Value= public, private                      |
| » status                | body     | string   | yes       | Access Status,Value = SETTING,HEALTHY, UNHEALTHY             |
| » browseGraph           | body     | string   | yes       | Browse Graph                                                 |
| » keyword               | body     | string   | yes       | Keyword                                                      |
| » description           | body     | string   | yes       | Description                                                  |
| » taskId                | body     | null     | yes       | TaskId                                                       |
| » boundaryWKT           | body     | null     | yes       | The range of the query space, which is returned in WKT format |
| » coordinateReference   | body     | null     | yes       | Coordinate Reference                                         |
| » projection            | body     | null     | yes       | Projection coordinate system                                 |
| » space                 | body     | object   | yes       | Spatial Information                                          |
| »» type                 | body     | null     | yes       | Type                                                         |
| »» resolution           | body     | string   | yes       | Spatial resolution                                           |
| »» elevation            | body     | null     | yes       | Elevation                                                    |
| »» extent               | body     | object   | yes       | Extent                                                       |
| »»» minX                | body     | integer  | yes       | Minimum x                                                    |
| »»» maxX                | body     | integer  | yes       | Maximum x                                                    |
| »»» minY                | body     | integer  | yes       | Minimum y                                                    |
| »»» maxY                | body     | integer  | yes       | Maximum y                                                    |
| »» geoIdentifier        | body     | null     | yes       | GeoIdentifier                                                |
| » temporal              | body     | object   | yes       | Time                                                         |
| »» geologicTime         | body     | null     | yes       | Geologic time，e.g, Quaternary                               |
| »» geologicAge          | body     | null     | yes       | Geological age，e.g,1，100 to 200.2                          |
| »» base                 | body     | integer  | yes       | The earliest possible time point，e.g,150.3                  |
| »» top                  | body     | integer  | yes       | The latest possible time point，e.g,10.2                     |
| »» gtsVersion           | body     | null     | yes       | Geological Age version，e.g,INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05 |
| » fields                | body     | [object] | yes       | Field Information                                            |
| »» type                 | body     | string   | yes       | Field type，Value = INT, FLOAT, DOUBLE, BOOLEAN, COLUMNNAME, GEOMETRY, VARCHAR |
| »» fieldName            | body     | string   | yes       | Fieldname                                                    |
| »» description          | body     | string   | yes       | Description                                                  |
| » intellectualProp      | body     | null     | yes       | IntellectualProp                                             |
| » license               | body     | null     | yes       | license                                                      |
| » discipline            | body     | string   | yes       | Discipline                                                   |
| » authorName            | body     | null     | yes       | Author name                                                  |
| » authorMail            | body     | null     | yes       | Author email                                                 |
| » doi                   | body     | null     | yes       | The unique identifier of the data object                     |
| » associatedResource    | body     | null     | yes       | Associated resources                                         |
| » associatedResourceUrl | body     | null     | yes       | Link                                                         |
| » createTime            | body     | integer  | yes       | Created                                                      |
| » updateTime            | body     | integer  | yes       | Update Time                                                  |
| » httpDpMeta            | body     | object   | yes       | Data center information                                      |
| »» dpAddress            | body     | string   | yes       | dpAddress                                                    |
| »» security             | body     | object   | yes       | Encrypted information                                        |
| »»» useTls              | body     | boolean  | yes       | TLS encryption                                               |
| »» transfer             | body     | object   | yes       | Transfer information                                         |
| »»» endpoint            | body     | [string] | yes       | Endpoint                                                     |
| »»» protocol            | body     | string   | yes       | Data source protocol                                         |
| »» httpRoute            | body     | object   | yes       | HTTP Route                                                   |
| »»» contentType         | body     | string   | yes       | Content Type                                                 |
| »»» method              | body     | string   | yes       | Request Mode                                                 |

> return example

> success

```Plaintext
{
  "code": 200,
  "message": "success",
  "data": {
    "uid": "c5e58d08-a5cf-4590-b26c-8cc0e1431d4a"
  }
}
```

#### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

#### return structure

status code **200**

| name      | type    | constraint | description          |
| --------- | ------- | ---------- | -------------------- |
| » code    | integer | none       | Status Code          |
| » message | string  | none       | Status Information   |
| » data    | object  | none       | DataAtom Information |
| »» uid    | string  | none       | DataAtom UID         |

### POST /v1.0/api/data-central/atom/layer

POST /v1.0/api/data-central/atom/layer

Enter a field to add layerService DataAtom

> Body request parameter

```Plaintext
{
    "name": "OneSediment Detrital Zicron Data",
    "dataType": "TABLE",
    "atomType": "JDBC",
    "privilege": "PRIVATE",
    "status": "HEALTHY",
    "browseGraph": "dde.jpg",
    "keyword": "Detrital Zicron, Sediment",
    "description": "Detrital Zicron Data From OneSediment",
    "coordinateReference": "WGS84",
    "projection": "Equirectangular",
    "authorName": "DDE",
    "authorMail": "DDE@dde.com",
    "doi": "",
    "associatedResource": "The Global Detrital Zircon Database: Quantifying the Timing and Rate of Crustal Growth",
    "associatedResourceURL": "http://hdl.handle.net/10919/27785",
    "space": {
        "type": "TextTable",
        "resolution": "",
        "extent": {
            "minX": -180,
            "maxX": 180,
            "minY": 90,
            "maxY": -90
        }
    },
    "temporal": {
        "geologicTime": "",
        "geologicAge": "",
        "gtsVersion": "International",
        "base": 750,
        "top": 0
    },
    "fields": [
        {
            "fieldName": "ref_no",
            "type": "VARCHAR",
            "description": "reference number of zicron detrital"
        },
        {
            "fieldName": "lead_author",
            "type": "VARCHAR",
            "description": "lead author of reference paper"
        }
    ],
    "layerServiceInfo": {
        "type": "VECTOR",
        "method": "GEOJSON",
        "sourceLayer": "layer",
        "imageURL": "dde.jpg",
        "coordinateReference": "EPSG:4326",
        "url": "/geoserver/gwc/service/tms/1.0.0/ADMIN:fx_vector_hangzhou7@EPSG:4326@png/{z}/{x}/{reverseY}.png",
        "vectorLayerItem": {
            "geoJsonType": "POLYGON"
        }
    }
}
```

#### request parameter

| name                    | location | type     | necessary | description                                                  |
| ----------------------- | -------- | -------- | --------- | ------------------------------------------------------------ |
| rzpj                    | header   | string   | yes       | Certificate                                                  |
| body                    | body     | object   | no        | none                                                         |
| » name                  | body     | string   | yes       | Unit name                                                    |
| » dataType              | body     | string   | yes       | Data type,Value = FILE, TABLE, JSON, PICTURE.                |
| » atomType              | body     | string   | yes       | Metadata type,Value = LAYER_SERVICE,HTTP,JDBC,MYSQL,POSTGRESQL |
| » userId                | body     | string   | yes       | UserID                                                       |
| » privilege             | body     | string   | yes       | AccessPermission,Value= public, private                      |
| » status                | body     | string   | yes       | Access Status,Value = SETTING,HEALTHY, UNHEALTHY             |
| » isOfficial            | body     | integer  | yes       | Is it official                                               |
| » browseGraph           | body     | null     | yes       | Browse Graph                                                 |
| » keyword               | body     | string   | yes       | Keyword                                                      |
| » description           | body     | null     | yes       | Description                                                  |
| » taskId                | body     | null     | yes       | TaskID                                                       |
| » boundaryWKT           | body     | null     | yes       | The range of the query space, which is returned in WKT format. |
| » coordinateReference   | body     | null     | yes       | coordinate Reference                                         |
| » projection            | body     | null     | yes       | Projection coordinate system                                 |
| » space                 | body     | object   | yes       | Spatial Information                                          |
| »» type                 | body     | null     | yes       | Type                                                         |
| »» resolution           | body     | null     | yes       | Spatial resolution                                           |
| »» elevation            | body     | null     | yes       | Elevation                                                    |
| »» extent               | body     | object   | yes       | extent                                                       |
| »»» minX                | body     | integer  | yes       | Minimum x                                                    |
| »»» maxX                | body     | integer  | yes       | Maximum x                                                    |
| »»» minY                | body     | integer  | yes       | Minimum y                                                    |
| »»» maxY                | body     | integer  | yes       | Maximum y                                                    |
| »» geoIdentifier        | body     | null     | yes       | GeoIdentifier                                                |
| » temporal              | body     | object   | yes       | Time                                                         |
| »» geologicTime         | body     | null     | yes       | Geologic time，e.g, Quaternary                               |
| »» geologicAge          | body     | null     | yes       | Geological age，e.g,1，100 to 200.2                          |
| »» base                 | body     | integer  | yes       | The earliest possible time point，e.g,150.3                  |
| »» top                  | body     | integer  | yes       | The latest possible time point，e.g,10.2                     |
| »» gtsVersion           | body     | string   | yes       | Geological Age version，e.g,INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05 |
| » fields                | body     | [string] | yes       | Field Information                                            |
| » intellectualProp      | body     | null     | yes       | IntellectualProp                                             |
| » license               | body     | null     | yes       | license                                                      |
| » discipline            | body     | string   | yes       | Discipline                                                   |
| » authorName            | body     | null     | yes       | Author name                                                  |
| » authorMail            | body     | null     | yes       | Author email                                                 |
| » doi                   | body     | null     | yes       | The unique identifier of the data object                     |
| » associatedResource    | body     | null     | yes       | Associated resources                                         |
| » associatedResourceUrl | body     | null     | yes       | Link                                                         |
| » createTime            | body     | integer  | yes       | Created                                                      |
| » updateTime            | body     | integer  | yes       | Update Time                                                  |
| » layerServiceInfo      | body     | object   | yes       | Layer Service information                                    |
| »» type                 | body     | string   | yes       | Layer type，Value = VECTOR, TMS, TDTILES, NC, ELASTICSEARCH  |
| »» method               | body     | string   | yes       | Layer Service，Value = COG, WMS, WMTS, ARCGIS, TMS, TDT, AMAP, GEOJSON, TDTILES, NC, PBF |
| »» renderOptions        | body     | null     | yes       | Rendering                                                    |
| »» sourceLayer          | body     | string   | yes       | The real layer name，Default value: name                     |
| »» imageURL             | body     | string   | yes       | BrowseGraph URL                                              |
| »» url                  | body     | string   | yes       | Layer access unified locator                                 |
| »» tmsLegend            | body     | null     | yes       | For tms, you can select this field to record the legend type, color, and name |
| »» coordinateArr        | body     | null     | yes       | none                                                         |
| »» geoJsonType          | body     | null     | yes       | GeoJson Type, e.g, POINT,MULTIPOINT,LINESTRING,MULTILINESTRING,POLYGON,MULTIPOLYGON,GEOMETRYCOLLECTION |
| »» fields               | body     | null     | yes       | Fields                                                       |
| »» valueRange           | body     | null     | yes       | ValueRange                                                   |
| »» offset               | body     | null     | yes       | Offset                                                       |

> return example

> success

```Plaintext
{
  "code": 200,
  "message": "success",
  "data": {
    "uid": "587c669d-5605-4ecb-af82-0ad2e6dcc869"
  }
}
```

#### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

#### return structure

status code **200**

| name      | type    | constraint | description          |
| --------- | ------- | ---------- | -------------------- |
| » code    | integer | none       | Status Code          |
| » message | string  | none       | Status Information   |
| » data    | object  | none       | DataAtom Information |
| »» uid    | string  | none       | DataAtom UID         |

### POST /v1.0/api/data-central/atom/jdbc

POST /v1.0/api/data-central/atom/jdbc

Enter a field to add a JDBC DataAtom

> Body request parameter

```Plaintext
{
  "name": "OneSediment Detrital Zicron Data",
  "dataType": "TABLE",
  "atomType": "JDBC",
  "privilege": "PRIVATE",
  "status": "HEALTHY",
  "browseGraph": "dde.jpg",
  "keyword": "Detrital Zicron, Sediment",
  "description": "Detrital Zicron Data From OneSediment",
  "coordinateReference": "WGS84",
  "projection": "Equirectangular",
  "authorName": "DDE",
  "authorMail": "DDE@dde.com",
  "doi": "",
  "associatedResource": "The Global Detrital Zircon Database: Quantifying the Timing and Rate of Crustal Growth",
  "associatedResourceUrl": "http://hdl.handle.net/10919/27785",
  "space": {
    "type": "TextTable",
    "resolution": "",
    "extent": {
      "minX": -180,
      "maxX": 180,
      "minY": 90,
      "maxY": -90
    }
  },
  "temporal": {
    "geologicTime": "",
    "geologicAge": "",
    "gtsVersion": "International",
    "base": 750,
    "top": 0
  },
  "fields": [
    {
      "fieldName": "ref_no",
      "type": "VARCHAR",
      "description": "reference number of zicron detrital"
    },
    {
      "fieldName": "lead_author",
      "type": "VARCHAR",
      "description": "lead author of reference paper"
    }
  ],
  "jdbcDpMeta": {
    "transfer": {
      "endpoint": [
        "112.124.238.115:25432"
      ],
      "protocol": "database"
    },
    "security": {
      "useTls": false
    },
    "jdbcRoute": {
      "databaseKind": "postgresql",
      "databaseName": "OneSediment",
      "version": "12.0",
      "password": "OneSediment_admin",
      "username": "OneSediment_admin",
      "options": "characterEncoding=utf8&serverTimezone=UTC"
    }
  },
  "tableName": "test"
}
```

#### request parameter

| name                    | location | type     | necessary | description                                                  |
| ----------------------- | -------- | -------- | --------- | ------------------------------------------------------------ |
| rzpj                    | header   | string   | yes       | Certificate                                                  |
| body                    | body     | object   | no        | none                                                         |
| » name                  | body     | string   | yes       | Unit name                                                    |
| » dataType              | body     | string   | yes       | Data type,Value = FILE, TABLE, JSON, PICTURE                 |
| » vectorType            | body     | string   | yes       | Vector type，Value = POINT, MULTIPOINT, LINESTRING, MULTILINESTRING, POLYGON, MULTIPOLYGON, GEOMETRYCOLLECTION |
| » atomType              | body     | string   | yes       | Metadata type,Value = LAYER_SERVICE,HTTP,JDBC,MYSQL,POSTGRESQL |
| » privilege             | body     | string   | yes       | AccessPermission,Value= public, private                      |
| » status                | body     | string   | yes       | Access Status,Value = SETTING,HEALTHY, UNHEALTHY             |
| » isOfficial            | body     | integer  | yes       | Is it official                                               |
| » browseGraph           | body     | string   | yes       | Browse Graph                                                 |
| » keyword               | body     | string   | yes       | Keyword                                                      |
| » description           | body     | string   | yes       | Description                                                  |
| » coordinateReference   | body     | string   | yes       | coordinate Reference                                         |
| » projection            | body     | string   | yes       | Projection coordinate system                                 |
| » authorName            | body     | string   | yes       | Author name                                                  |
| » authorMail            | body     | string   | yes       | Author email                                                 |
| » doi                   | body     | string   | yes       | The unique identifier of the data object                     |
| » associatedResource    | body     | string   | yes       | Associated resources                                         |
| » associatedResourceUrl | body     | string   | yes       | Link                                                         |
| » space                 | body     | object   | yes       | Spatial Information                                          |
| »» type                 | body     | string   | yes       | Type                                                         |
| »» resolution           | body     | string   | yes       | Spatial resolution                                           |
| »» extent               | body     | object   | yes       | extent                                                       |
| »»» minX                | body     | integer  | yes       | Minimum x                                                    |
| »»» maxX                | body     | integer  | yes       | Maximum x                                                    |
| »»» minY                | body     | integer  | yes       | Minimum y                                                    |
| »»» maxY                | body     | integer  | yes       | Maximum y                                                    |
| » temporal              | body     | object   | yes       | Time                                                         |
| »» geologicTime         | body     | string   | yes       | Geologic time，e.g, Quaternary                               |
| »» geologicAge          | body     | string   | yes       | Geological age，e.g,1，100 to 200.2                          |
| »» gtsVersion           | body     | string   | yes       | Geological Age version，e.g,INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05 |
| »» base                 | body     | integer  | yes       | The earliest possible time point，e.g,150.3                  |
| »» top                  | body     | integer  | yes       | The latest possible time point，e.g,10.2                     |
| » fields                | body     | [string] | yes       | Field Information                                            |
| » jdbcDpMeta            | body     | object   | yes       | JDBC protocol meta                                           |
| »» transfer             | body     | object   | yes       | Transfer information                                         |
| »»» endpoint            | body     | [string] | yes       | Endpoint                                                     |
| »»» protocol            | body     | string   | yes       | Data source protocol                                         |
| »» security             | body     | object   | yes       | Encrypted information                                        |
| »»» useTls              | body     | boolean  | yes       | TLS encryption                                               |
| »» jdbcRoute            | body     | object   | yes       | JDBC Route                                                   |
| »»» databaseKind        | body     | string   | yes       | Database type                                                |
| »»» databaseName        | body     | string   | yes       | Database name                                                |
| »»» version             | body     | string   | yes       | Version                                                      |
| »»» password            | body     | string   | yes       | Password                                                     |
| »»» username            | body     | string   | yes       | Username                                                     |
| »»» options             | body     | string   | yes       | Options, character encoding, and database server time zone   |
| » tableName             | body     | string   | yes       | Database table name                                          |

> return example

> success

```Plaintext
{
  "code": 200,
  "message": "success",
  "data": {
    "uid": "2421200a-293e-4146-ad82-c1472cc43d10"
  }
}
```

#### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

#### return structure

status code **200**

| name      | type    | constraint | description          |
| --------- | ------- | ---------- | -------------------- |
| » code    | integer | none       | Status Code          |
| » message | string  | none       | Status Information   |
| » data    | object  | none       | DataAtom Information |
| »» uid    | string  | none       | DataAtom UID         |

### **POST /v1.0/api/data-central/atom/file**

POST /v1.0/api/data-central/atom/file

Fill in the field and add a DataAtom of file type

> Body request parmeter

```JSON
{
  "name": "File OneSediment Detrital Zicron Data",
  "dataType": "TABLE",
  "atomType": "JDBC",
  "privilege": "PRIVATE",
  "status": "HEALTHY",
  "isOfficial": 0,
  "browseGraph": "wlq.jpg",
  "keyword": "Detrital Zicron, Sediment",
  "description": "Detrital Zicron Data From OneSediment",
  "coordinateReference": "WGS84",
  "projection": "Equirectangular",
  "authorName": "Hu Xiumian",
  "authorMail": "huxm@nju.edu.cn",
  "doi": "",
  "associatedResource": "The Global Detrital Zircon Database: Quantifying the Timing and Rate of Crustal Growth",
  "associatedResourceURL": "http://hdl.handle.net/10919/27785",
  "space": {
    "type": "TextTable",
    "resolution": "",
    "extent": {
      "minX": -180,
      "maxX": 180,
      "minY": 90,
      "maxY": -90
    }
  },
  "temporal": {
    "geologicTime": "",
    "geologicAge": "",
    "gtsVersion": "International",
    "base": 750,
    "top": 0
  },
  "fields": [
    {
      "fieldName": "ref_no",
      "type": "VARCHAR",
      "description": "reference number of zicron detrital"
    },
    {
      "fieldName": "lead_author",
      "type": "VARCHAR",
      "description": "lead author of reference paper"
    }
  ],
  "filePath": "/vi/test/file",
  "endpoint": "xafgasdf",
  "accessKey": "2435",
  "secretKey": "987654"
}
```

#### request parameter

| name                    | location | type     | necessary | description                                                  |
| ----------------------- | -------- | -------- | --------- | ------------------------------------------------------------ |
| rzpj                    | header   | string   | Yes       | Certificate                                                  |
| body                    | body     | object   | No        | none                                                         |
| » name                  | body     | string   | Yes       | none                                                         |
| » dataType              | body     | string   | Yes       | Currently there are FILE, TABLE, JSON, PICTURE and other types |
| » privilege             | body     | string   | Yes       | There are currently two types of PUBLIC and PRIVATE          |
| » status                | body     | string   | Yes       | Currently there are SETTING, HEALTHY, UNHEALTHY              |
| » isOfficial            | body     | integer  | Yes       | A value of 1 is official data, 0 is unofficial data          |
| » browseGraph           | body     | string   | No        | none                                                         |
| » keyword               | body     | string   | No        | none                                                         |
| » description           | body     | string   | No        | none                                                         |
| » coordinateReference   | body     | string   | No        | none                                                         |
| » projection            | body     | string   | No        | none                                                         |
| » authorName            | body     | string   | No        | none                                                         |
| » authorMail            | body     | string   | No        | none                                                         |
| » doi                   | body     | string   | No        | none                                                         |
| » associatedResource    | body     | string   | No        | none                                                         |
| » associatedResourceURL | body     | string   | No        | none                                                         |
| » space                 | body     | object   | No        | none                                                         |
| »» type                 | body     | string   | No        | none                                                         |
| »» resolution           | body     | string   | No        | none                                                         |
| »» elevation            | body     | number   | No        | none                                                         |
| »» extent               | body     | object   | Yes       | none                                                         |
| »»» minX                | body     | integer  | Yes       | none                                                         |
| »»» maxX                | body     | integer  | Yes       | none                                                         |
| »»» minY                | body     | integer  | Yes       | none                                                         |
| »»» maxY                | body     | integer  | Yes       | none                                                         |
| »» geoIdentifier        | body     | string   | No        | none                                                         |
| » temporal              | body     | object   | No        | none                                                         |
| »» geologicTime         | body     | string   | No        | Quaternary                                                   |
| »» geologicAge          | body     | string   | No        | 1，100 to 200.2                                              |
| »» base                 | body     | number   | Yes       | Such as 150.3.                                               |
| »» top                  | body     | number   | Yes       | Such as 10.2.                                                |
| »» gtsVersion           | body     | string   | No        | INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05             |
| » fields                | body     | [object] | Yes       | none                                                         |
| »» type                 | body     | string   | No        | INT, FLOAT, DOUBLE, BOOLEAN, COLUMNNAME, GEOMETRY, VARCHAR   |
| »» fieldName            | body     | string   | No        | none                                                         |
| »» description          | body     | string   | No        | none                                                         |
| » license               | body     | string   | No        | none                                                         |
| » intellectualProp      | body     | string   | No        | none                                                         |
| » discipline            | body     | string   | Yes       | none                                                         |
| » filePath              | body     | string   | Yes       | none                                                         |
| » endpoint              | body     | string   | No        | none                                                         |
| » accessKey             | body     | string   | No        | none                                                         |
| » secretKey             | body     | string   | No        | none                                                         |

> return example

> success

```JSON
{
  "code": 200,
  "message": "success",
  "data": {
    "uid": "fac808a0-ec80-4722-81f5-c3d45ce64ff2"
  }
}
```

#### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

#### return structure

status code **200**

| name      | type    | constraint | description    |
| --------- | ------- | ---------- | -------------- |
| » code    | integer | none       | status code    |
| » message | string  | none       | status message |
| » data    | object  | none       | none           |
| »» uid    | string  | none       | User id        |

### **GET /v1.0/api/data-central/atom/jdbc/vector/crs**

GET /v1.0/api/data-central/atom/jdbc/vector/crs

#### **request parameter**

| name | location | type   | necessary | description |
| ---- | -------- | ------ | --------- | ----------- |
| path | query    | string | no        | Data path   |
| rzpj | header   | string | no        | Certificate |

> return example

> success

```Plaintext
{
  "code": 200,
  "message": "success",
  "data": {
    "identifier": null,
    "wkt": "GEOGCS[\"GCS_WGS_1984\", \n  DATUM[\"D_WGS_1984\", \n    SPHEROID[\"WGS_1984\", 6378137.0, 298.257223563]], \n  PRIMEM[\"Greenwich\", 0.0], \n  UNIT[\"degree\", 0.017453292519943295], \n  AXIS[\"Longitude\", EAST], \n  AXIS[\"Latitude\", NORTH]]"
  }
}
```

#### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

#### return structure

status code **200**

| name          | type    | constraint | description         |
| ------------- | ------- | ---------- | ------------------- |
| » code        | integer | none       | Status Code         |
| » message     | string  | none       | Status Information  |
| » data        | object  | none       | Dataset Information |
| »» identifier | null    | none       | none                |
| »» wkt        | string  | none       | none                |

## Dataset

### GET /v1.0/api/data-central/dataset

GET /v1.0/api/data-central/dataset/

Obtain a dataset based on its id or uid

#### request parameter

| name | location | type   | necessary | description                                                  |
| ---- | -------- | ------ | --------- | ------------------------------------------------------------ |
| uid  | query    | string | no        | Dataset uid, which cannot be empty at the same time as the id |
| id   | query    | string | no        | Dataset id, which cannot be empty at the same time as the uid |
| rzpj | header   | string | yea       | Certificate                                                  |

> return example

> success

```Plaintext
{
  "code": 200,
  "message": "success",
  "data": {
    "id": 25,
    "uid": "9c9798c6-c6e1-44d4-8083-8595bc15a0d3",
    "name": "Scotese & Wright 2018Ver.2",
    "type": "RASTER",
    "userId": "7003c445-1f0b-4f23-82ff-72dd345383fc",
    "privilege": "PUBLIC",
    "isOfficial": 0,
    "browseGraph": "dde.jpg",
    "keyword": "Paleogeography,Paleogeographic maps,Scotese & Wright",
    "author": {
      "metaDataStandardName": "None",
      "metaDataIdentifier": "None",
      "createTimestamp": 1426734778313,
      "authorName": "Christopher Scotese, Nicky Wright",
      "authorEmail": "3180101626@zju.edu.cn",
      "responsible": "None",
      "responsibleRegion": "US",
      "responsibleEmail": "3180101626@zju.edu.cn",
      "announcement": "None",
      "dataProtectionPeriod": "0",
      "license": "Creative Commons Attribution 4.0 International"
    },
    "description": {
      "title": "Paleogeographic maps by Scotese & Wright (2018)",
      "alias": "Paleogeographic maps by Scotese & Wright (2018)",
      "edition": "Version 2",
      "language": "English",
      "encoding": "UTF-8",
      "keyword": "Paleogeography,Paleogeographic maps,Scotese & Wright",
      "abstractInfo": "A series of paleogeographic maps ranging from 750 Ma to present",
      "topicCategory": "/Paleogeography",
      "additionalDoc": "Scotese, C. R., & Wright, N. M. (2018). PALEOMAP Paleodigital Elevation Models (PaleoDEMS) for the Phanerozoic [Map]. Zenodo. https://doi.org/10.5281/zenodo.5460860",
      "lineage": "The maps are created and published by Scotese & Wright in 2018 under the Creative Commons licence.",
      "source": "None",
      "date": "2018-08-01",
      "dataUrl": "https://zenodo.org/record/5460860"
    },
    "temporal": {
      "geologicTime": "Neoproterozoic and Phanerozoic",
      "geologicAge": "None",
      "base": 750,
      "top": 0,
      "gtsVersion": "International"
    },
    "space": {
      "type": "None",
      "resolution": "0.1 degree",
      "elevation": "-11000~10500",
      "extent": {
        "minX": -180,
        "maxX": 180,
        "minY": -90,
        "maxY": 90
      },
      "geoIdentifier": "Global"
    },
    "boundaryWKT": null,
    "coordinateReference": "WGS84",
    "projection": "Equirectangular",
    "service": {
      "type": "None",
      "doi": "None",
      "accessPrivilege": "None",
      "usePrivilege": "None",
      "associatedResource": "None",
      "associatedResMeta": "None",
      "coupledResource": "None",
      "distributionFormat": "None",
      "onlineResource": "None",
      "associatedPaperDOI": "None"
    },
    "createTime": 1650369385151,
    "updateTime": 1650369385151
  }
}
```

#### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

#### return structure

status code **200**

| name                     | type    | constraint | description                                                  |
| ------------------------ | ------- | ---------- | ------------------------------------------------------------ |
| » code                   | integer | none       | Status Code                                                  |
| » message                | string  | none       | Status Information                                           |
| » data                   | object  | none       | Dataset Information                                          |
| »» id                    | integer | none       | Dataset ID                                                   |
| »» uid                   | string  | none       | Dataset UID                                                  |
| »» name                  | string  | none       | Unit name                                                    |
| »» type                  | string  | none       | Dataset Type                                                 |
| »» userId                | string  | none       | Userid                                                       |
| »» privilege             | string  | none       | AccessPermission,Value= public, private                      |
| »» isOfficial            | integer | none       | Is it official ?                                             |
| »» browseGraph           | string  | none       | BrowseGraph                                                  |
| »» keyword               | string  | none       | Keyword                                                      |
| »» author                | object  | none       | Author                                                       |
| »»» metaDataStandardName | string  | none       | Standard metadata name                                       |
| »»» metaDataIdentifier   | string  | none       | Metadata definition                                          |
| »»» createTimestamp      | integer | none       | Metadata create timestamp                                    |
| »»» authorName           | string  | none       | Author name                                                  |
| »»» authorEmail          | string  | none       | Author email                                                 |
| »»» responsible          | string  | none       | Responsible                                                  |
| »»» responsibleRegion    | string  | none       | Responsibile region                                          |
| »»» responsibleEmail     | string  | none       | Responsible Email                                            |
| »»» announcement         | string  | none       | Declaration                                                  |
| »»» dataProtectionPeriod | string  | none       | Data protection cycle                                        |
| »»» license              | string  | none       | License                                                      |
| »» description           | object  | none       | Description                                                  |
| »»» title                | string  | none       | Title                                                        |
| »»» alias                | string  | none       | Alias                                                        |
| »»» edition              | string  | none       | Version                                                      |
| »»» language             | string  | none       | Language                                                     |
| »»» encoding             | string  | none       | Encoding                                                     |
| »»» keyword              | string  | none       | Keyword                                                      |
| »»» abstractInfo         | string  | none       | Abstract information                                         |
| »»» topicCategory        | string  | none       | Topic category                                               |
| »»» additionalDoc        | string  | none       | Additional documentation                                     |
| »»» lineage              | string  | none       | Data lineage                                                 |
| »»» source               | string  | none       | Source                                                       |
| »»» date                 | string  | none       | Date                                                         |
| »»» dataUrl              | string  | none       | Data address                                                 |
| »» temporal              | object  | none       | Time                                                         |
| »»» geologicTime         | string  | none       | Geologic time，e.g, Quaternary                               |
| »»» geologicAge          | string  | none       | Geological age，e.g,1，100 to 200.2                          |
| »»» base                 | integer | none       | The earliest possible time point，e.g,150.3                  |
| »»» top                  | integer | none       | The latest possible time point，e.g,10.2                     |
| »»» gtsVersion           | string  | none       | Geological Age version，e.g,INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05 |
| »» space                 | object  | none       | Spatial Information                                          |
| »»» type                 | string  | none       | Type                                                         |
| »»» resolution           | string  | none       | Spatial resolution                                           |
| »»» elevation            | string  | none       | Elevation                                                    |
| »»» extent               | object  | none       | extent                                                       |
| »»»» minX                | integer | none       | Minimum x                                                    |
| »»»» maxX                | integer | none       | Maximum x                                                    |
| »»»» minY                | integer | none       | Minimum y                                                    |
| »»»» maxY                | integer | none       | Maximum y                                                    |
| »»» geoIdentifier        | string  | none       | GeoIdentifier                                                |
| »» boundaryWKT           | null    | none       | The range of the spatial region. The value is returned in wkt format |
| »» coordinateReference   | string  | none       | coordinate Reference                                         |
| »» projection            | string  | none       | Projection coordinate system                                 |
| »» service               | object  | none       | Service                                                      |
| »»» type                 | string  | none       | Dataset type                                                 |
| »»» doi                  | string  | none       | The unique identifier of the data object                     |
| »»» accessPrivilege      | string  | none       | Access permissions                                           |
| »»» usePrivilege         | string  | none       | Permission                                                   |
| »»» associatedResource   | string  | none       | Associated resources                                         |
| »»» associatedResMeta    | string  | none       | Associated resource metadata                                 |
| »»» coupledResource      | string  | none       | Coupling resources                                           |
| »»» distributionFormat   | string  | none       | Format of data distribution                                  |
| »»» onlineResource       | string  | none       | Reference resources online                                   |
| »»» associatedPaperDOI   | string  | none       | Associated paper DOI                                         |
| »» createTime            | integer | none       | Created                                                      |
| »» updateTime            | integer | none       | Update Time                                                  |

### POST /v1.0/api/data-central/dataset

POST /v1.0/api/data-central/dataset/

Add a dataset

> Body request parameter

```Plaintext
{
  "name": "Scotese & Wright 2018Ver.2",
  "type": "RASTER",
  "privilege": "0",
  "browseGraph": "dde.jpg",
  "keyword": "Paleogeography,Paleogeographic maps,Scotese & Wright",
  "author": {
    "createTimestamp": 1426734778313,
    "authorName": "Christopher Scotese, Nicky Wright",
    "authorEmail": "cscotese@gmail.com",
    "responsible": "None",
    "responsibleRegion": "US",
    "responsibleEmail": "None",
    "license": "Creative Commons Attribution 4.0 International",
    "dataProtectionPeriod": "0",
    "announcement": "None",
    "metaDataIdentifier": "None",
    "metaDataStandardName": "None"
  },
  "description": {
    "edition": "Version 2",
    "language": "English",
    "encoding": "UTF-8",
    "abstractInfo": "A series of paleogeographic maps ranging from 750 Ma to present",
    "topicCategory": "/Paleogeography",
    "alias": "Paleogeographic maps by Scotese & Wright (2018)",
    "date": "2018-08-01",
    "dataUrl": "https://zenodo.org/record/5460860",
    "title": "Paleogeographic maps by Scotese & Wright (2018)",
    "lineage": "The maps are created and published by Scotese & Wright in 2018 under the Creative Commons licence.",
    "keyword": "Paleogeography,Paleogeographic maps,Scotese & Wright",
    "source": "None",
    "additionalDoc": "Scotese, C. R., & Wright, N. M. (2018). PALEOMAP Paleodigital Elevation Models (PaleoDEMS) for the Phanerozoic [Map]. Zenodo. https://doi.org/10.5281/zenodo.5460860"
  },
  "temporal": {
    "geologicTime": "Neoproterozoic and Phanerozoic",
    "base": 750,
    "top": 0,
    "gtsVersion": "International",
    "geologicAge": "None"
  },
  "space": {
    "resolution": "0.1 degree",
    "extent": {
      "minX": -180,
      "maxX": 180,
      "minY": -90,
      "maxY": 90
    },
    "elevation": "-11000~10500",
    "geoIdentifier": "Global",
    "type": "None"
  },
  "coordinateReference": "WGS84",
  "projection": "Equirectangular",
  "service": {
    "associatedResource": "None",
    "associatedPaperDOI": "None",
    "doi": "None",
    "distributionFormat": "None",
    "onlineResource": "None",
    "usePrivilege": "None",
    "associatedResMeta": "None",
    "coupledResource": "None",
    "type": "None",
    "accessPrivilege": "None"
  }
}
```

#### request parameter

| name                    | location | type    | necessary | description                                                  |
| ----------------------- | -------- | ------- | --------- | ------------------------------------------------------------ |
| rzpj                    | header   | string  | yes       | Certificate                                                  |
| body                    | body     | object  | no        | none                                                         |
| » name                  | body     | string  | yes       | Dataset name                                                 |
| » type                  | body     | string  | yes       | Dataset type                                                 |
| » privilege             | body     | string  | yes       | AccessPermission,Value= public, private                      |
| » isOfficial            | body     | integer | yes       | Is it official ?                                             |
| » browseGraph           | body     | string  | yes       | BrowseGraph                                                  |
| » keyword               | body     | string  | yes       | Keyword                                                      |
| » author                | body     | object  | yes       | Author                                                       |
| »» createTimestamp      | body     | integer | yes       | Metadata create timestamp                                    |
| »» authorName           | body     | string  | yes       | Author name                                                  |
| »» authorEmail          | body     | string  | yes       | Author email                                                 |
| »» responsible          | body     | string  | yes       | Responsible                                                  |
| »» responsibleRegion    | body     | string  | yes       | Responsibile region                                          |
| »» responsibleEmail     | body     | string  | yes       | Responsible Email                                            |
| »» license              | body     | string  | yes       | License                                                      |
| »» dataProtectionPeriod | body     | string  | yes       | Data protection cycle                                        |
| »» announcement         | body     | string  | yes       | Announcement                                                 |
| »» metaDataIdentifier   | body     | string  | yes       | Metadata definition                                          |
| »» metaDataStandardName | body     | string  | yes       | Standard metadata name                                       |
| » description           | body     | object  | yes       | Description                                                  |
| »» edition              | body     | string  | yes       | Version                                                      |
| »» language             | body     | string  | yes       | Language                                                     |
| »» encoding             | body     | string  | yes       | Encoding                                                     |
| »» abstractInfo         | body     | string  | yes       | Abstract information                                         |
| »» topicCategory        | body     | string  | yes       | Topic category                                               |
| »» alias                | body     | string  | yes       | Alias                                                        |
| »» date                 | body     | string  | yes       | Date                                                         |
| »» dataUrl              | body     | string  | yes       | Data address                                                 |
| »» title                | body     | string  | yes       | Title                                                        |
| »» lineage              | body     | string  | yes       | Data lineage                                                 |
| »» keyword              | body     | string  | yes       | Keyword                                                      |
| »» source               | body     | string  | yes       | Source                                                       |
| »» additionalDoc        | body     | string  | yes       | Additional documentation                                     |
| » temporal              | body     | object  | yes       | Time                                                         |
| »» geologicTime         | body     | string  | yes       | Geologic time，e.g, Quaternary                               |
| »» base                 | body     | integer | yes       | The earliest possible time point，e.g,150.3                  |
| »» top                  | body     | integer | yes       | The latest possible time point，e.g,10.2                     |
| »» gtsVersion           | body     | string  | yes       | Geological Age version，e.g,INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05 |
| »» geologicAge          | body     | string  | yes       | Geological age，e.g,1，100 to 200.2                          |
| » space                 | body     | object  | yes       | Spatial Information                                          |
| »» resolution           | body     | string  | yes       | Spatial resolution                                           |
| »» extent               | body     | object  | yes       | extent                                                       |
| »»» minX                | body     | integer | yes       | Minimum x                                                    |
| »»» maxX                | body     | integer | yes       | Maximum x                                                    |
| »»» minY                | body     | integer | yes       | Minimum y                                                    |
| »»» maxY                | body     | integer | yes       | Maximum y                                                    |
| »» elevation            | body     | string  | yes       | Elevation                                                    |
| »» geoIdentifier        | body     | string  | yes       | GeoIdentifier                                                |
| »» type                 | body     | string  | yes       | Type                                                         |
| » coordinateReference   | body     | string  | yes       | coordinate Reference                                         |
| » projection            | body     | string  | yes       | Projection coordinate system                                 |
| » service               | body     | object  | yes       | Service                                                      |
| »» associatedResource   | body     | string  | yes       | Associated resources                                         |
| »» associatedPaperDOI   | body     | string  | yes       | Associated paper DOI                                         |
| »» doi                  | body     | string  | yes       | The unique identifier of the data object                     |
| »» distributionFormat   | body     | string  | yes       | Format of data distribution                                  |
| »» onlineResource       | body     | string  | yes       | Reference resources online                                   |
| »» usePrivilege         | body     | string  | yes       | Permission                                                   |
| »» associatedResMeta    | body     | string  | yes       | Associated resource metadata                                 |
| »» coupledResource      | body     | string  | yes       | Coupling resources                                           |
| »» type                 | body     | string  | yes       | Dataset type                                                 |
| »» accessPrivilege      | body     | string  | yes       | Access permissions                                           |

> return example

> success

```Plaintext
{
  "code": 200,
  "message": "success",
  "data": {
    "uid": "9c9798c6-c6e1-44d4-8083-8595bc15a0d3"
  }
}
```

#### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

#### return structure

status code **200**

| name      | type    | constraint | description         |
| --------- | ------- | ---------- | ------------------- |
| » code    | integer | none       | Status Code         |
| » message | string  | none       | Status Message      |
| » data    | object  | none       | Dataset information |
| »» uid    | string  | none       | Dataset UID         |

### GET /v1.0/api/data-central/dataset/{datasetName}

GET /v1.0/api/data-central/dataset/{datasetName}

Obtain a dataset based on its name

#### request parameter

| name        | location | type   | necessary | description  |
| ----------- | -------- | ------ | --------- | ------------ |
| datasetName | path     | string | yes       | Dataset Name |
| rzpj        | header   | string | yes       | Certificate  |

> return example

> success

```Plaintext
{
    "code": 200,
    "message": "success",
    "data": {
        "id": 25,
        "uid": "9c9798c6-c6e1-44d4-8083-8595bc15a0d3",
        "name": "Scotese & Wright 2018Ver.2",
        "type": "RASTER",
        "userId": "7003c445-1f0b-4f23-82ff-72dd345383fc",
        "privilege": "PUBLIC",
        "isOfficial": 0,
        "browseGraph": "wlq.jpg",
        "keyword": "Paleogeography,Paleogeographic maps,Scotese & Wright",
        "author": {
            "metaDataStandardName": "None",
            "metaDataIdentifier": "None",
            "createTimestamp": 1426734778313,
            "authorName": "Christopher Scotese, Nicky Wright",
            "authorEmail": "3180101626@zju.edu.cn",
            "responsible": "None",
            "responsibleRegion": "US",
            "responsibleEmail": "3180101626@zju.edu.cn",
            "announcement": "None",
            "dataProtectionPeriod": "0",
            "license": "Creative Commons Attribution 4.0 International"
        },
        "description": {
            "title": "Paleogeographic maps by Scotese & Wright (2018)",
            "alias": "Paleogeographic maps by Scotese & Wright (2018)",
            "edition": "Version 2",
            "language": "English",
            "encoding": "UTF-8",
            "keyword": "Paleogeography,Paleogeographic maps,Scotese & Wright",
            "abstractInfo": "A series of paleogeographic maps ranging from 750 Ma to present",
            "topicCategory": "/Paleogeography",
            "additionalDoc": "Scotese, C. R., & Wright, N. M. (2018). PALEOMAP Paleodigital Elevation Models (PaleoDEMS) for the Phanerozoic [Map]. Zenodo. https://doi.org/10.5281/zenodo.5460860",
            "lineage": "The maps are created and published by Scotese & Wright in 2018 under the Creative Commons licence.",
            "source": "None",
            "date": "2018-08-01",
            "dataUrl": "https://zenodo.org/record/5460860"
        },
        "temporal": {
            "geologicTime": "Neoproterozoic and Phanerozoic",
            "geologicAge": "None",
            "base": 750,
            "top": 0,
            "gtsVersion": "International"
        },
        "space": {
            "type": "None",
            "resolution": "0.1 degree",
            "elevation": "-11000~10500",
            "extent": {
                "minX": -180,
                "maxX": 180,
                "minY": -90,
                "maxY": 90
            },
            "geoIdentifier": "Global"
        },
        "boundaryWKT": null,
        "coordinateReference": "WGS84",
        "projection": "Equirectangular",
        "service": {
            "type": "None",
            "doi": "None",
            "accessPrivilege": "None",
            "usePrivilege": "None",
            "associatedResource": "None",
            "associatedResMeta": "None",
            "coupledResource": "None",
            "distributionFormat": "None",
            "onlineResource": "None",
            "associatedPaperDOI": "None"
        },
        "createTime": 1650369385151,
        "updateTime": 1650369385151
    }
}
```

#### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

#### return structure

status code **200**

| name                     | type    | constraint | description                                                  |
| ------------------------ | ------- | ---------- | ------------------------------------------------------------ |
| » code                   | integer | none       | Status Code                                                  |
| » message                | string  | none       | Status Information                                           |
| » data                   | object  | none       | Dataset Information                                          |
| »» id                    | integer | none       | Dataset ID                                                   |
| »» uid                   | string  | none       | Dataset UID                                                  |
| »» name                  | string  | none       | Unit name                                                    |
| »» type                  | string  | none       | Dataset Type                                                 |
| »» userId                | string  | none       | Userid                                                       |
| »» privilege             | string  | none       | AccessPermission,Value= public, private                      |
| »» isOfficial            | integer | none       | Is it official ?                                             |
| »» browseGraph           | string  | none       | BrowseGraph                                                  |
| »» keyword               | string  | none       | Keyword                                                      |
| »» author                | object  | none       | Author                                                       |
| »»» metaDataStandardName | string  | none       | Standard metadata name                                       |
| »»» metaDataIdentifier   | string  | none       | Metadata definition                                          |
| »»» createTimestamp      | integer | none       | Metadata create timestamp                                    |
| »»» authorName           | string  | none       | Author name                                                  |
| »»» authorEmail          | string  | none       | Author email                                                 |
| »»» responsible          | string  | none       | Responsible                                                  |
| »»» responsibleRegion    | string  | none       | Responsibile region                                          |
| »»» responsibleEmail     | string  | none       | Responsible Email                                            |
| »»» announcement         | string  | none       | Declaration                                                  |
| »»» dataProtectionPeriod | string  | none       | Data protection cycle                                        |
| »»» license              | string  | none       | License                                                      |
| »» description           | object  | none       | Description                                                  |
| »»» title                | string  | none       | Title                                                        |
| »»» alias                | string  | none       | Alias                                                        |
| »»» edition              | string  | none       | Version                                                      |
| »»» language             | string  | none       | Language                                                     |
| »»» encoding             | string  | none       | Encoding                                                     |
| »»» keyword              | string  | none       | Keyword                                                      |
| »»» abstractInfo         | string  | none       | Abstract information                                         |
| »»» topicCategory        | string  | none       | Topic category                                               |
| »»» additionalDoc        | string  | none       | Additional documentation                                     |
| »»» lineage              | string  | none       | Data lineage                                                 |
| »»» source               | string  | none       | Source                                                       |
| »»» date                 | string  | none       | Date                                                         |
| »»» dataUrl              | string  | none       | Data address                                                 |
| »» temporal              | object  | none       | Time                                                         |
| »»» geologicTime         | string  | none       | Geologic time，e.g, Quaternary                               |
| »»» geologicAge          | string  | none       | Geological age，e.g,1，100 to 200.2                          |
| »»» base                 | integer | none       | The earliest possible time point，e.g,150.3                  |
| »»» top                  | integer | none       | The latest possible time point，e.g,10.2                     |
| »»» gtsVersion           | string  | none       | Geological Age version，e.g,INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05 |
| »» space                 | object  | none       | Spatial Information                                          |
| »»» type                 | string  | none       | Type                                                         |
| »»» resolution           | string  | none       | Spatial resolution                                           |
| »»» elevation            | string  | none       | Elevation                                                    |
| »»» extent               | object  | none       | extent                                                       |
| »»»» minX                | integer | none       | Minimum x                                                    |
| »»»» maxX                | integer | none       | Maximum x                                                    |
| »»»» minY                | integer | none       | Minimum y                                                    |
| »»»» maxY                | integer | none       | Maximum y                                                    |
| »»» geoIdentifier        | string  | none       | GeoIdentifier                                                |
| »» boundaryWKT           | null    | none       | The range of the spatial region. The value is returned in wkt format |
| »» coordinateReference   | string  | none       | coordinate Reference                                         |
| »» projection            | string  | none       | Projection coordinate system                                 |
| »» service               | object  | none       | Service                                                      |
| »»» type                 | string  | none       | Dataset type                                                 |
| »»» doi                  | string  | none       | The unique identifier of the data object                     |
| »»» accessPrivilege      | string  | none       | Access permissions                                           |
| »»» usePrivilege         | string  | none       | Permission                                                   |
| »»» associatedResource   | string  | none       | Associated resources                                         |
| »»» associatedResMeta    | string  | none       | Associated resource metadata                                 |
| »»» coupledResource      | string  | none       | Coupling resources                                           |
| »»» distributionFormat   | string  | none       | Format of data distribution                                  |
| »»» onlineResource       | string  | none       | Reference resources online                                   |
| »»» associatedPaperDOI   | string  | none       | Associated paper DOI                                         |
| »» createTime            | integer | none       | Created                                                      |
| »» updateTime            | integer | none       | Update Time                                                  |

### POST /v1.0/api/data-central/dataset/{datasetId}/atoms/uid

POST /v1.0/api/data-central/dataset/{datasetUid}/atoms/uid

Add an atom to a dataset

#### request parameter

| name       | location | type   | necessary | description              |
| ---------- | -------- | ------ | --------- | ------------------------ |
| datasetUid | path     | string | yes       | Dataset UID              |
| atomUids   | query    | string | yes       | The Uid set of data atom |
| rzpj       | header   | string | yes       | Certificate              |

> return example

> success

```Plaintext
{
    "code": 200,
    "message": "success",
    "data": {
        "id": 25,
        "uid": "9c9798c6-c6e1-44d4-8083-8595bc15a0d3",
        "name": "Scotese & Wright 2018Ver.2",
        "type": "RASTER",
        "userId": "7003c445-1f0b-4f23-82ff-72dd345383fc",
        "privilege": "PUBLIC",
        "isOfficial": 0,
        "browseGraph": "dde.jpg",
        "keyword": "Paleogeography,Paleogeographic maps,Scotese & Wright",
        "author": {
            "metaDataStandardName": "None",
            "metaDataIdentifier": "None",
            "createTimestamp": 1426734778313,
            "authorName": "Christopher Scotese, Nicky Wright",
            "authorEmail": "3180101626@zju.edu.cn",
            "responsible": "None",
            "responsibleRegion": "US",
            "responsibleEmail": "3180101626@zju.edu.cn",
            "announcement": "None",
            "dataProtectionPeriod": "0",
            "license": "Creative Commons Attribution 4.0 International"
        },
        "description": {
            "title": "Paleogeographic maps by Scotese & Wright (2018)",
            "alias": "Paleogeographic maps by Scotese & Wright (2018)",
            "edition": "Version 2",
            "language": "English",
            "encoding": "UTF-8",
            "keyword": "Paleogeography,Paleogeographic maps,Scotese & Wright",
            "abstractInfo": "A series of paleogeographic maps ranging from 750 Ma to present",
            "topicCategory": "/Paleogeography",
            "additionalDoc": "Scotese, C. R., & Wright, N. M. (2018). PALEOMAP Paleodigital Elevation Models (PaleoDEMS) for the Phanerozoic [Map]. Zenodo. https://doi.org/10.5281/zenodo.5460860",
            "lineage": "The maps are created and published by Scotese & Wright in 2018 under the Creative Commons licence.",
            "source": "None",
            "date": "2018-08-01",
            "dataUrl": "https://zenodo.org/record/5460860"
        },
        "temporal": {
            "geologicTime": "Neoproterozoic and Phanerozoic",
            "geologicAge": "None",
            "base": 750,
            "top": 0,
            "gtsVersion": "International"
        },
        "space": {
            "type": "None",
            "resolution": "0.1 degree",
            "elevation": "-11000~10500",
            "extent": {
                "minX": -180,
                "maxX": 180,
                "minY": -90,
                "maxY": 90
            },
            "geoIdentifier": "Global"
        },
        "boundaryWKT": null,
        "coordinateReference": "WGS84",
        "projection": "Equirectangular",
        "service": {
            "type": "None",
            "doi": "None",
            "accessPrivilege": "None",
            "usePrivilege": "None",
            "associatedResource": "None",
            "associatedResMeta": "None",
            "coupledResource": "None",
            "distributionFormat": "None",
            "onlineResource": "None",
            "associatedPaperDOI": "None"
        },
        "createTime": 1650369385151,
        "updateTime": 1650369385151
    }
}
```

#### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

#### return structure

status code **200**

| name                     | type    | constraint | description                                                  |
| ------------------------ | ------- | ---------- | ------------------------------------------------------------ |
| » code                   | integer | none       | Status Code                                                  |
| » message                | string  | none       | Status Information                                           |
| » data                   | object  | none       | Dataset Information                                          |
| »» id                    | integer | none       | Dataset ID                                                   |
| »» uid                   | string  | none       | Dataset UID                                                  |
| »» name                  | string  | none       | Unit name                                                    |
| »» type                  | string  | none       | Dataset Type                                                 |
| »» userId                | string  | none       | Userid                                                       |
| »» privilege             | string  | none       | AccessPermission,Value= public, private                      |
| »» isOfficial            | integer | none       | Is it official ?                                             |
| »» browseGraph           | string  | none       | BrowseGraph                                                  |
| »» keyword               | string  | none       | Keyword                                                      |
| »» author                | object  | none       | Author                                                       |
| »»» metaDataStandardName | string  | none       | Standard metadata name                                       |
| »»» metaDataIdentifier   | string  | none       | Metadata definition                                          |
| »»» createTimestamp      | integer | none       | Metadata create timestamp                                    |
| »»» authorName           | string  | none       | Author name                                                  |
| »»» authorEmail          | string  | none       | Author email                                                 |
| »»» responsible          | string  | none       | Responsible                                                  |
| »»» responsibleRegion    | string  | none       | Responsibile region                                          |
| »»» responsibleEmail     | string  | none       | Responsible Email                                            |
| »»» announcement         | string  | none       | Declaration                                                  |
| »»» dataProtectionPeriod | string  | none       | Data protection cycle                                        |
| »»» license              | string  | none       | License                                                      |
| »» description           | object  | none       | Description                                                  |
| »»» title                | string  | none       | Title                                                        |
| »»» alias                | string  | none       | Alias                                                        |
| »»» edition              | string  | none       | Version                                                      |
| »»» language             | string  | none       | Language                                                     |
| »»» encoding             | string  | none       | Encoding                                                     |
| »»» keyword              | string  | none       | Keyword                                                      |
| »»» abstractInfo         | string  | none       | Abstract information                                         |
| »»» topicCategory        | string  | none       | Topic category                                               |
| »»» additionalDoc        | string  | none       | Additional documentation                                     |
| »»» lineage              | string  | none       | Data lineage                                                 |
| »»» source               | string  | none       | Source                                                       |
| »»» date                 | string  | none       | Date                                                         |
| »»» dataUrl              | string  | none       | Data address                                                 |
| »» temporal              | object  | none       | Time                                                         |
| »»» geologicTime         | string  | none       | Geologic time，e.g, Quaternary                               |
| »»» geologicAge          | string  | none       | Geological age，e.g,1，100 to 200.2                          |
| »»» base                 | integer | none       | The earliest possible time point，e.g,150.3                  |
| »»» top                  | integer | none       | The latest possible time point，e.g,10.2                     |
| »»» gtsVersion           | string  | none       | Geological Age version，e.g,INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05 |
| »» space                 | object  | none       | Spatial Information                                          |
| »»» type                 | string  | none       | Type                                                         |
| »»» resolution           | string  | none       | Spatial resolution                                           |
| »»» elevation            | string  | none       | Elevation                                                    |
| »»» extent               | object  | none       | extent                                                       |
| »»»» minX                | integer | none       | Minimum x                                                    |
| »»»» maxX                | integer | none       | Maximum x                                                    |
| »»»» minY                | integer | none       | Minimum y                                                    |
| »»»» maxY                | integer | none       | Maximum y                                                    |
| »»» geoIdentifier        | string  | none       | GeoIdentifier                                                |
| »» boundaryWKT           | null    | none       | The range of the spatial region. The value is returned in wkt format |
| »» coordinateReference   | string  | none       | coordinate Reference                                         |
| »» projection            | string  | none       | Projection coordinate system                                 |
| »» service               | object  | none       | Service                                                      |
| »»» type                 | string  | none       | Dataset type                                                 |
| »»» doi                  | string  | none       | The unique identifier of the data object                     |
| »»» accessPrivilege      | string  | none       | Access permissions                                           |
| »»» usePrivilege         | string  | none       | Permission                                                   |
| »»» associatedResource   | string  | none       | Associated resources                                         |
| »»» associatedResMeta    | string  | none       | Associated resource metadata                                 |
| »»» coupledResource      | string  | none       | Coupling resources                                           |
| »»» distributionFormat   | string  | none       | Format of data distribution                                  |
| »»» onlineResource       | string  | none       | Reference resources online                                   |
| »»» associatedPaperDOI   | string  | none       | Associated paper DOI                                         |
| »» createTime            | integer | none       | Created                                                      |
| »» updateTime            | integer | none       | Update Time                                                  |

### GET /v1.0/api/data-central/dataset/list/user

GET /v1.0/api/data-central/dataset/list/user

Obtain the list of DataSet belonging to the user

#### request parameter

| name           | location | type   | necessary | description                                                  |
| -------------- | -------- | ------ | --------- | ------------------------------------------------------------ |
| page           | query    | string | no        | In the previous page, if you want to display the first page, use 0 |
| pageSize       | query    | string | no        | Number of Entries displayed per page                         |
| spatialWkt     | query    | string | no        | Enter wkt as the spatial query and return the boundaryWKT. If you do not specify this parameter, you will not be added to the spatial query. |
| top            | query    | string | no        | Maximum time range for querying data                         |
| base           | query    | string | no        | Minimum time range for querying data                         |
| keyword        | query    | string | no        | Keyword                                                      |
| startTimestamp | query    | string | no        | Start time                                                   |
| endTimestamp   | query    | string | no        | End time                                                     |
| rzpj           | header   | string | yes       | Certificate                                                  |

> return example

> success

```Plaintext
{
    "code": 200,
    "message": "success",
    "data": {
        "total": 2,
        "list": [
            {
                "id": 24,
                "uid": "5fd7fd2c-8140-42d5-b5bd-55f2061b3c3b",
                "name": "Paleogeographic maps by Scotese & Wright (2018)",
                "type": "RASTER",
                "userId": "ADMIN",
                "privilege": "PUBLIC",
                "isOfficial": 1,
                "browseGraph": null,
                "keyword": "Paleogeography,Paleogeographic maps,Scotese & Wright",
                "author": {
                    "metaDataStandardName": null,
                    "metaDataIdentifier": null,
                    "createTimestamp": 0,
                    "authorName": "Christopher Scotese, Nicky Wright",
                    "authorEmail": "cscotese@gmail.com",
                    "responsible": null,
                    "responsibleRegion": "US",
                    "responsibleEmail": null,
                    "announcement": null,
                    "dataProtectionPeriod": null,
                    "license": "Creative Commons Attribution 4.0 International"
                },
                "description": {
                    "title": "Paleogeographic maps by Scotese & Wright (2018)",
                    "alias": "Paleogeographic maps by Scotese & Wright (2018)",
                    "edition": "Version 2",
                    "language": "English",
                    "encoding": "UTF-8",
                    "keyword": "Paleogeography,Paleogeographic maps,Scotese & Wright",
                    "abstractInfo": "A series of paleogeographic maps ranging from 750 Ma to present",
                    "topicCategory": "/Paleogeography",
                    "additionalDoc": "Scotese, C. R., & Wright, N. M. (2018). PALEOMAP Paleodigital Elevation Models (PaleoDEMS) for the Phanerozoic [Map]. Zenodo. https://doi.org/10.5281/zenodo.5460860",
                    "lineage": "The maps are created and published by Scotese & Wright in 2018 under the Creative Commons licence.",
                    "source": null,
                    "date": "2018-08-01",
                    "dataUrl": "https://zenodo.org/record/5460860"
                },
                "temporal": {
                    "geologicTime": "Neoproterozoic and Phanerozoic",
                    "geologicAge": null,
                    "base": 750,
                    "top": 0,
                    "gtsVersion": "International"
                },
                "space": {
                    "type": null,
                    "resolution": "0.1 degree",
                    "elevation": "-11000~10500",
                    "extent": {
                        "minX": -180,
                        "maxX": 180,
                        "minY": -90,
                        "maxY": 90
                    },
                    "geoIdentifier": "Global"
                },
                "boundaryWKT": "POLYGON((-180 -90,-180 90,180 90,180 -90,-180 -90))",
                "coordinateReference": "WGS 84",
                "projection": "Equirectangular",
                "service": null,
                "createTime": 1648455648429,
                "updateTime": 1648455648429
            },
            {
                "id": 23,
                "uid": "bd215cf0-6d65-4b42-829d-3fdcacb55191",
                "name": "Hu et al. (2021) paleo-precipitation modeling",
                "type": "RASTER",
                "userId": "ADMIN",
                "privilege": "PUBLIC",
                "isOfficial": 1,
                "browseGraph": null,
                "keyword": "paleoclimate modeling, Phanerozoic, precipitation",
                "author": {
                    "metaDataStandardName": null,
                    "metaDataIdentifier": null,
                    "createTimestamp": 0,
                    "authorName": "Yongyun Hu",
                    "authorEmail": "yyhu@pku.edu.cn",
                    "responsible": "Yongyun Hu",
                    "responsibleRegion": "CN",
                    "responsibleEmail": "yyhu@pku.edu.cn",
                    "announcement": null,
                    "dataProtectionPeriod": null,
                    "license": null
                },
                "description": {
                    "title": "A high-resolution climate simulation dataset for the past 540 million years",
                    "alias": "A high-resolution climate simulation dataset for the past 540 million years",
                    "edition": "Version1.0 2022/4/30",
                    "language": "English",
                    "encoding": "UTF-8",
                    "keyword": null,
                    "abstractInfo": "Here we perform 55 snapshot simulations for the past 540 million years, with a 10-million-year interval, using the Community Earth System Model version 1.2.2 (CESM1.2.2). The climate simulation dataset includes global distributions of monthly surface temperatures and precipitation, with a nominal 1° horizontal resolution of 0.9375° × 1.25° in latitude and longitude. This open access climate dataset is useful for multidisciplinary research, such as paleoclimate, geology, geochemistry, and paleontology.",
                    "topicCategory": "/Surficial Geochemistry/Paleoclimate",
                    "additionalDoc": "Li, X., Y. Hu*, et al., 2022: A high-resolution climate simulation dataset for the past 540 million years, in review",
                    "lineage": null,
                    "source": null,
                    "date": null,
                    "dataUrl": null
                },
                "temporal": {
                    "geologicTime": "Phanerozoic",
                    "geologicAge": null,
                    "base": 540,
                    "top": 0,
                    "gtsVersion": "INTERNATIONAL"
                },
                "space": {
                    "type": null,
                    "resolution": "0.9375° × 1.25° in latitude and longitude",
                    "elevation": null,
                    "extent": {
                        "minX": -180,
                        "maxX": 180,
                        "minY": -90,
                        "maxY": 90
                    },
                    "geoIdentifier": "Global"
                },
                "boundaryWKT": "POLYGON((-180 -90,-180 90,180 90,180 -90,-180 -90))",
                "coordinateReference": "WGS 84",
                "projection": "Equirectangular",
                "service": {
                    "type": null,
                    "doi": null,
                    "accessPrivilege": null,
                    "usePrivilege": null,
                    "associatedResource": null,
                    "associatedResMeta": null,
                    "coupledResource": null,
                    "distributionFormat": null,
                    "onlineResource": null,
                    "associatedPaperDOI": null
                },
                "createTime": 1648452964288,
                "updateTime": 1648452964288
            }
        ]
    }
}
```

#### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

#### return structure

status code **200**

| name                      | type        | constraint | description                                                  |
| ------------------------- | ----------- | ---------- | ------------------------------------------------------------ |
| » code                    | integer     | none       | Status Code                                                  |
| » message                 | string      | none       | Status Information                                           |
| » data                    | object      | none       | Dataset Information                                          |
| »» total                  | integer     | none       | The number of data records                                   |
| »» list                   | [object]    | none       | Dataset list                                                 |
| »»» id                    | integer     | none       | Dataset ID                                                   |
| »»» uid                   | string      | none       | Dataset UID                                                  |
| »»» name                  | string      | none       | Unit name                                                    |
| »»» type                  | string      | none       | Dataset Type                                                 |
| »»» userId                | string      | none       | Userid                                                       |
| »»» privilege             | string      | none       | AccessPermission,Value= public, private                      |
| »»» isOfficial            | integer     | none       | Is it official ?                                             |
| »»» browseGraph           | null        | none       | BrowseGraph                                                  |
| »»» keyword               | string      | none       | Keyword                                                      |
| »»» author                | object      | none       | Author                                                       |
| »»»» metaDataStandardName | null        | none       | Standard metadata name                                       |
| »»»» metaDataIdentifier   | null        | none       | Metadata definition                                          |
| »»»» createTimestamp      | integer     | none       | Metadata create timestamp                                    |
| »»»» authorName           | string      | none       | Author name                                                  |
| »»»» authorEmail          | string      | none       | Author email                                                 |
| »»»» responsible          | null        | none       | Responsible                                                  |
| »»»» responsibleRegion    | string      | none       | Responsibile region                                          |
| »»»» responsibleEmail     | null        | none       | Responsible Email                                            |
| »»»» announcement         | null        | none       | Declaration                                                  |
| »»»» dataProtectionPeriod | null        | none       | Data protection cycle                                        |
| »»»» license              | string¦null | none       | License                                                      |
| »»» description           | object      | none       | Description                                                  |
| »»»» title                | string      | none       | Title                                                        |
| »»»» alias                | string      | none       | Alias                                                        |
| »»»» edition              | string      | none       | Version                                                      |
| »»»» language             | string      | none       | Language                                                     |
| »»»» encoding             | string      | none       | Encoding                                                     |
| »»»» keyword              | string¦null | none       | Keyword                                                      |
| »»»» abstractInfo         | string      | none       | Abstract information                                         |
| »»»» topicCategory        | string      | none       | Topic category                                               |
| »»»» additionalDoc        | string      | none       | Additional documentation                                     |
| »»»» lineage              | string¦null | none       | Data lineage                                                 |
| »»»» source               | null        | none       | Source                                                       |
| »»»» date                 | string¦null | none       | Date                                                         |
| »»»» dataUrl              | string¦null | none       | Data address                                                 |
| »»» temporal              | object      | none       | Time                                                         |
| »»»» geologicTime         | string      | none       | Geologic time，e.g, Quaternary                               |
| »»»» geologicAge          | null        | none       | Geological age，e.g,1，100 to 200.2                          |
| »»»» base                 | integer     | none       | The earliest possible time point，e.g,150.3                  |
| »»»» top                  | integer     | none       | The latest possible time point，e.g,10.2                     |
| »»»» gtsVersion           | string      | none       | Geological Age version，e.g,INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05 |
| »»» space                 | object      | none       | Spatial Information                                          |
| »»»» type                 | null        | none       | Type                                                         |
| »»»» resolution           | string      | none       | Spatial resolution                                           |
| »»»» elevation            | string¦null | none       | Elevation                                                    |
| »»»» extent               | object      | none       | extent                                                       |
| »»»»» minX                | integer     | none       | Minimum x                                                    |
| »»»»» maxX                | integer     | none       | Maximum x                                                    |
| »»»»» minY                | integer     | none       | Minimum y                                                    |
| »»»»» maxY                | integer     | none       | Maximum y                                                    |
| »»»» geoIdentifier        | string      | none       | GeoIdentifier                                                |
| »»» boundaryWKT           | string      | none       | The range of the spatial region. The value is returned in wkt format |
| »»» coordinateReference   | string      | none       | coordinate Reference                                         |
| »»» projection            | string      | none       | Projection coordinate system                                 |
| »»» service               | object      | none       | Service                                                      |
| »»»» type                 | null        | none       | Dataset type                                                 |
| »»»» doi                  | null        | none       | The unique identifier of the data object                     |
| »»»» accessPrivilege      | null        | none       | Access permissions                                           |
| »»»» usePrivilege         | null        | none       | Permission                                                   |
| »»»» associatedResource   | null        | none       | Associated resources                                         |
| »»»» associatedResMeta    | null        | none       | Associated resource metadata                                 |
| »»»» coupledResource      | null        | none       | Coupling resources                                           |
| »»»» distributionFormat   | null        | none       | Format of data distribution                                  |
| »»»» onlineResource       | null        | none       | Reference resources online                                   |
| »»»» associatedPaperDOI   | null        | none       | Associated paper DOI                                         |
| »»» createTime            | integer     | none       | Created                                                      |
| »»» updateTime            | integer     | none       | Update Time                                                  |

### GET /v1.0/api/data-central/dataset/list/public

GET /v1.0/api/data-central/dataset/list/public

Obtains a list of public DataAtom

#### request parameter

| name       | location | type   | necessary | description                                                  |
| ---------- | -------- | ------ | --------- | ------------------------------------------------------------ |
| page       | query    | string | no        | In the previous page, if you want to display the first page, use 0 |
| pageSize   | query    | string | no        | Number of Entries displayed per page                         |
| official   | query    | string | no        | Is it official                                               |
| spatialWkt | query    | string | no        | Enter wkt as the spatial query and return the boundaryWKT. If you do not specify this parameter, you will not be added to the spatial query. |
| top        | query    | string | no        | Maximum time range for querying data                         |
| base       | query    | string | no        | Minimum time range for querying data                         |
| keyword    | query    | string | no        | Keyword                                                      |

> return example

> success

```Plaintext
{
    "code": 200,
    "message": "success",
    "data": {
        "total": 2,
        "list": [
            {
                "id": 24,
                "uid": "5fd7fd2c-8140-42d5-b5bd-55f2061b3c3b",
                "name": "Paleogeographic maps by Scotese & Wright (2018)",
                "type": "RASTER",
                "userId": "ADMIN",
                "privilege": "PUBLIC",
                "isOfficial": 1,
                "browseGraph": null,
                "keyword": "Paleogeography,Paleogeographic maps,Scotese & Wright",
                "author": {
                    "metaDataStandardName": null,
                    "metaDataIdentifier": null,
                    "createTimestamp": 0,
                    "authorName": "Christopher Scotese, Nicky Wright",
                    "authorEmail": "cscotese@gmail.com",
                    "responsible": null,
                    "responsibleRegion": "US",
                    "responsibleEmail": null,
                    "announcement": null,
                    "dataProtectionPeriod": null,
                    "license": "Creative Commons Attribution 4.0 International"
                },
                "description": {
                    "title": "Paleogeographic maps by Scotese & Wright (2018)",
                    "alias": "Paleogeographic maps by Scotese & Wright (2018)",
                    "edition": "Version 2",
                    "language": "English",
                    "encoding": "UTF-8",
                    "keyword": "Paleogeography,Paleogeographic maps,Scotese & Wright",
                    "abstractInfo": "A series of paleogeographic maps ranging from 750 Ma to present",
                    "topicCategory": "/Paleogeography",
                    "additionalDoc": "Scotese, C. R., & Wright, N. M. (2018). PALEOMAP Paleodigital Elevation Models (PaleoDEMS) for the Phanerozoic [Map]. Zenodo. https://doi.org/10.5281/zenodo.5460860",
                    "lineage": "The maps are created and published by Scotese & Wright in 2018 under the Creative Commons licence.",
                    "source": null,
                    "date": "2018-08-01",
                    "dataUrl": "https://zenodo.org/record/5460860"
                },
                "temporal": {
                    "geologicTime": "Neoproterozoic and Phanerozoic",
                    "geologicAge": null,
                    "base": 750,
                    "top": 0,
                    "gtsVersion": "International"
                },
                "space": {
                    "type": null,
                    "resolution": "0.1 degree",
                    "elevation": "-11000~10500",
                    "extent": {
                        "minX": -180,
                        "maxX": 180,
                        "minY": -90,
                        "maxY": 90
                    },
                    "geoIdentifier": "Global"
                },
                "boundaryWKT": "POLYGON((-180 -90,-180 90,180 90,180 -90,-180 -90))",
                "coordinateReference": "WGS 84",
                "projection": "Equirectangular",
                "service": null,
                "createTime": 1648455648429,
                "updateTime": 1648455648429
            },
            {
                "id": 23,
                "uid": "bd215cf0-6d65-4b42-829d-3fdcacb55191",
                "name": "Hu et al. (2021) paleo-precipitation modeling",
                "type": "RASTER",
                "userId": "ADMIN",
                "privilege": "PUBLIC",
                "isOfficial": 1,
                "browseGraph": null,
                "keyword": "paleoclimate modeling, Phanerozoic, precipitation",
                "author": {
                    "metaDataStandardName": null,
                    "metaDataIdentifier": null,
                    "createTimestamp": 0,
                    "authorName": "author",
                    "authorEmail": "dde@dde.com",
                    "responsible": "dde",
                    "responsibleRegion": "CN",
                    "responsibleEmail": "dde@dde.com",
                    "announcement": null,
                    "dataProtectionPeriod": null,
                    "license": null
                },
                "description": {
                    "title": "A high-resolution climate simulation dataset for the past 540 million years",
                    "alias": "A high-resolution climate simulation dataset for the past 540 million years",
                    "edition": "Version1.0 2022/4/30",
                    "language": "English",
                    "encoding": "UTF-8",
                    "keyword": null,
                    "abstractInfo": "Here we perform 55 snapshot simulations for the past 540 million years, with a 10-million-year interval, using the Community Earth System Model version 1.2.2 (CESM1.2.2). The climate simulation dataset includes global distributions of monthly surface temperatures and precipitation, with a nominal 1° horizontal resolution of 0.9375° × 1.25° in latitude and longitude. This open access climate dataset is useful for multidisciplinary research, such as paleoclimate, geology, geochemistry, and paleontology.",
                    "topicCategory": "/Surficial Geochemistry/Paleoclimate",
                    "additionalDoc": "Li, X., Y. Hu*, et al., 2022: A high-resolution climate simulation dataset for the past 540 million years, in review",
                    "lineage": null,
                    "source": null,
                    "date": null,
                    "dataUrl": null
                },
                "temporal": {
                    "geologicTime": "Phanerozoic",
                    "geologicAge": null,
                    "base": 540,
                    "top": 0,
                    "gtsVersion": "INTERNATIONAL"
                },
                "space": {
                    "type": null,
                    "resolution": "0.9375° × 1.25° in latitude and longitude",
                    "elevation": null,
                    "extent": {
                        "minX": -180,
                        "maxX": 180,
                        "minY": -90,
                        "maxY": 90
                    },
                    "geoIdentifier": "Global"
                },
                "boundaryWKT": "POLYGON((-180 -90,-180 90,180 90,180 -90,-180 -90))",
                "coordinateReference": "WGS 84",
                "projection": "Equirectangular",
                "service": {
                    "type": null,
                    "doi": null,
                    "accessPrivilege": null,
                    "usePrivilege": null,
                    "associatedResource": null,
                    "associatedResMeta": null,
                    "coupledResource": null,
                    "distributionFormat": null,
                    "onlineResource": null,
                    "associatedPaperDOI": null
                },
                "createTime": 1648452964288,
                "updateTime": 1648452964288
            }
        ]
    }
}
```

#### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

#### return structure

status code **200**

| name                      | type        | constraint | description                                                  |
| ------------------------- | ----------- | ---------- | ------------------------------------------------------------ |
| » code                    | integer     | none       | Status Code                                                  |
| » message                 | string      | none       | Status Information                                           |
| » data                    | object      | none       | Dataset Information                                          |
| »» total                  | integer     | none       | The number of data records                                   |
| »» list                   | [object]    | none       | Dataset list                                                 |
| »»» id                    | integer     | none       | Dataset ID                                                   |
| »»» uid                   | string      | none       | Dataset UID                                                  |
| »»» name                  | string      | none       | Unit name                                                    |
| »»» type                  | string      | none       | Dataset Type                                                 |
| »»» userId                | string      | none       | Userid                                                       |
| »»» privilege             | string      | none       | AccessPermission,Value= public, private                      |
| »»» isOfficial            | integer     | none       | Is it official                                               |
| »»» browseGraph           | null        | none       | BrowseGraph                                                  |
| »»» keyword               | string      | none       | Keyword                                                      |
| »»» author                | object      | none       | Author                                                       |
| »»»» metaDataStandardName | null        | none       | Standard metadata name                                       |
| »»»» metaDataIdentifier   | null        | none       | Metadata definition                                          |
| »»»» createTimestamp      | integer     | none       | Metadata create timestamp                                    |
| »»»» authorName           | string      | none       | Author name                                                  |
| »»»» authorEmail          | string      | none       | Author email                                                 |
| »»»» responsible          | null        | none       | Responsible                                                  |
| »»»» responsibleRegion    | string      | none       | Responsibile region                                          |
| »»»» responsibleEmail     | null        | none       | Responsible Email                                            |
| »»»» announcement         | null        | none       | Declaration                                                  |
| »»»» dataProtectionPeriod | null        | none       | Data protection cycle                                        |
| »»»» license              | string¦null | none       | License                                                      |
| »»» description           | object      | none       | Description                                                  |
| »»»» title                | string      | none       | Title                                                        |
| »»»» alias                | string      | none       | Alias                                                        |
| »»»» edition              | string      | none       | Version                                                      |
| »»»» language             | string      | none       | Language                                                     |
| »»»» encoding             | string      | none       | Encoding                                                     |
| »»»» keyword              | string¦null | none       | Keyword                                                      |
| »»»» abstractInfo         | string      | none       | Abstract information                                         |
| »»»» topicCategory        | string      | none       | Topic category                                               |
| »»»» additionalDoc        | string      | none       | Additional documentation                                     |
| »»»» lineage              | string¦null | none       | Data lineage                                                 |
| »»»» source               | null        | none       | Source                                                       |
| »»»» date                 | string¦null | none       | Date                                                         |
| »»»» dataUrl              | string¦null | none       | Data address                                                 |
| »»» temporal              | object      | none       | Time                                                         |
| »»»» geologicTime         | string      | none       | Geologic time，e.g, Quaternary                               |
| »»»» geologicAge          | null        | none       | Geological age，e.g,1，100 to 200.2                          |
| »»»» base                 | integer     | none       | The earliest possible time point，e.g,150.3                  |
| »»»» top                  | integer     | none       | The latest possible time point，e.g,10.2                     |
| »»»» gtsVersion           | string      | none       | Geological Age version，e.g,INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05 |
| »»» space                 | object      | none       | Spatial Information                                          |
| »»»» type                 | null        | none       | Type                                                         |
| »»»» resolution           | string      | none       | Spatial resolution                                           |
| »»»» elevation            | string¦null | none       | Elevation                                                    |
| »»»» extent               | object      | none       | extent                                                       |
| »»»»» minX                | integer     | none       | Minimum x                                                    |
| »»»»» maxX                | integer     | none       | Maximum x                                                    |
| »»»»» minY                | integer     | none       | Minimum y                                                    |
| »»»»» maxY                | integer     | none       | Maximum y                                                    |
| »»»» geoIdentifier        | string      | none       | GeoIdentifier                                                |
| »»» boundaryWKT           | string      | none       | The range of the spatial region. The value is returned in wkt format |
| »»» coordinateReference   | string      | none       | coordinate Reference                                         |
| »»» projection            | string      | none       | Projection coordinate system                                 |
| »»» service               | object      | none       | Service                                                      |
| »»»» type                 | null        | none       | Dataset type                                                 |
| »»»» doi                  | null        | none       | The unique identifier of the data object                     |
| »»»» accessPrivilege      | null        | none       | Access permissions                                           |
| »»»» usePrivilege         | null        | none       | Permission                                                   |
| »»»» associatedResource   | null        | none       | Associated resources                                         |
| »»»» associatedResMeta    | null        | none       | Associated resource metadata                                 |
| »»»» coupledResource      | null        | none       | Coupling resources                                           |
| »»»» distributionFormat   | null        | none       | Format of data distribution                                  |
| »»»» onlineResource       | null        | none       | Reference resources online                                   |
| »»»» associatedPaperDOI   | null        | none       | Associated paper DOI                                         |
| »»» createTime            | integer     | none       | Created                                                      |
| »»» updateTime            | integer     | none       | Update Time                                                  |

## Data Query

### **POST /v1.0/api/data-central/query/data/http**

POST /v1.0/api/data-central/query/data/htt

http api request

> Body request parmeter

```JSON
{
  "uid": "a221f383-4a33-4936-ab8b-76e001283ac4",
  "queryParams": [
    {
      "name": "time",
      "value": 140
    },
    {
      "name": "model",
      "value": "SETON2012"
    }
  ]
}
```

#### request parameter

| name          | location | type     | necessary | description |
| ------------- | -------- | -------- | --------- | ----------- |
| userId        | header   | string   | 否        | none        |
| body          | body     | object   | 否        | none        |
| » uid         | body     | string   | 是        | none        |
| » queryParams | body     | [object] | 是        | none        |
| »» name       | body     | string   | 是        | none        |
| »» value      | body     | integer  | 是        | none        |

> return example

> success

```JSON
{
  "uid": "c68f5672-7e41-4503-b969-dc5c91a665b4",
  "queryParams": [
    {
      "name": "time",
      "value": 140
    },
    {
      "name": "points",
      "value": "95,54,142,-33"
    },
    {
      "name": "model",
      "value": "SETON2012"
    }
  ]
}
```

#### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

#### return structure

status code **200**

| name          | type     | constraint | description |
| ------------- | -------- | ---------- | ----------- |
| » uid         | string   | none       |             |
| » queryParams | [object] | none       |             |
| »» name       | string   | none       |             |
| »» value      | integer  | none       |             |

# Computation Hub API v0.7.8

## Workflow Job

### POST /v1.0/api/job

POST /v1.0/api/job Create a job

> Body

```Plaintext
{
  "jobName": "New Interface Test - Task",
  "description": "New Interface Test - Task",
  "task": [
    {
      "taskId": "t0",
      "taskName": "fuxi-polygon feature to point",
      "toolId": "06be3ead-1f65-4765-b6ea-73fac365baaa",
      "args": [
        {
          "paramName": "polyShapefile",
          "value": "fuxi://shapefile/USA_states_adm1.shp"
        },
        {
          "paramName": "pointShapefile",
          "value": "fuxi://shapefile/USA_states_adm1_topoint.shp"
        }
      ],
      "upstream": []
    }
  ]
}
```

#### request parameter

| name      | location | type   | necessary | description |
| --------- | -------- | ------ | --------- | ----------- |
| AccessKey | header   | string | no        | AccessKey   |
| SecretKey | header   | string | no        | SecretKey   |
| UserID    | header   | string | no        | UserID      |
| rzpj      | header   | string | no        | Certificate |
| body      | body     | object | no        | none        |

> return example

#### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

#### return structure

status code **200**

### **DELETE /v1.0/job/{jobld}**

DELETE /v1.0/job/{toolId}

#### request parameter

| name  | location | type   | necessary | description |
| ----- | -------- | ------ | --------- | ----------- |
| jobld | path     | string | yes       | none        |
| rzpj  | header   | string | no        | none        |

> return example

> success

```undefined
{
  "success": true
}
```

#### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

#### return structure

status code **200**

### **GET /v1.0/job/{jobld}**

GET /v1.0/job/{toolId}

#### request parameter

| name  | location | type   | necessary | description |
| ----- | -------- | ------ | --------- | ----------- |
| jobld | path     | string | yes       | none        |
| rzpj  | header   | string | yes       | none        |

> return example

> success

```undefined
{
  "jobId": "db38561f-c28e-4da4-af11-ef1dc8d71d5b",
  "jobName": "crust_0-23Ma-job03",
  "description": "",
  "owner": "99bca0f1-4fea-4cdc-bbc4-f14d4813fb9a",
  "status": "success",
  "tasks": [
    {
      "taskId": "t0",
      "taskName": "Inverse Distance Weighting Interpolation",
      "toolId": "399c4616-5436-47c1-9f3f-a418bb7c35d8",
      "args": [
        {
          "paramName": "path_data_points",
          "value": "DDE://crust/thickness/0_23Ma.csv",
          "attributes": {
            "isOutputParam": false,
            "fileType": "FILE",
            "multiple": false
          }
        },
        {
          "paramName": "x_field_id",
          "value": 2,
          "paramAttributes": {
            "name": "x_field_id",
            "dataType": "NUMBER",
            "description": "X坐标列在输入文件中的列号索引",
            "engDescription": "Index of x coordinate",
            "required": false,
            "in": 0,
            "default": "0"
          }
        },
        {
          "paramName": "y_field_id",
          "value": "1",
          "paramAttributes": {
            "name": "y_field_id",
            "dataType": "NUMBER",
            "description": "Y坐标列在输入文件中的列号索引",
            "engDescription": "Index of y coordinate",
            "required": false,
            "in": 0,
            "default": "1"
          }
        },
        {
          "paramName": "z_value_id",
          "value": 0,
          "paramAttributes": {
            "name": "z_value_id",
            "dataType": "NUMBER",
            "description": "待插值属性列在输入文件中的列号索引",
            "engDescription": "Index of z-value coordinate",
            "required": true,
            "in": 0,
            "default": "2"
          }
        },
        {
          "paramName": "radius",
          "value": "",
          "paramAttributes": {
            "name": "radius",
            "dataType": "NUMBER",
            "description": "在该半径范围内进行插值，默认为全局，填写示例：-r 100",
            "engDescription": "Search radius in given range, default to be global, example: -r 100",
            "required": false,
            "in": 0,
            "default": ""
          }
        },
        {
          "paramName": "max_neighbors",
          "value": "12",
          "paramAttributes": {
            "name": "max_neighbors",
            "dataType": "NUMBER",
            "description": "插值时中心像元搜索到最多点数",
            "engDescription": "Maximum Number of neighbor points",
            "required": false,
            "in": 0,
            "default": "12"
          }
        },
        {
          "paramName": "x_cell_size",
          "value": 0.1,
          "paramAttributes": {
            "name": "x_cell_size",
            "dataType": "NUMBER",
            "description": "栅格X轴大小",
            "engDescription": "x-axis cell size",
            "required": true,
            "in": 0,
            "default": ""
          }
        },
        {
          "paramName": "y_cell_size",
          "value": 0.1,
          "paramAttributes": {
            "name": "y_cell_size",
            "dataType": "NUMBER",
            "description": "栅格Y轴大小",
            "engDescription": "y-axis cell size",
            "required": true,
            "in": 0,
            "default": ""
          }
        },
        {
          "paramName": "extent",
          "value": "80,92,29,32",
          "paramAttributes": {
            "name": "extent",
            "dataType": "STRING",
            "description": "可以指定输出范围，默认是输入shp的范围。填写示例：xmin, xmax, ymin, ymax",
            "engDescription": "Spatial extent of output results, default to be the extent of input shapefile, example: xmin, xmax, ymin, ymax",
            "required": false,
            "in": 0,
            "default": ""
          }
        },
        {
          "paramName": "path_result",
          "value": "DDE://crust/thickness/0_23Ma.tif",
          "attributes": {
            "isOutputParam": true,
            "fileType": "FILE",
            "multiple": false
          }
        }
      ],
      "upstream": [],
      "x": 392.1307,
      "y": 262
    }
  ],
  "startDate": "2022-06-29 19:00:14.290424-08",
  "endDate": "2022-06-29 19:00:29.592692-08"
}
```

#### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

#### return structure

status code **200**

| name                | type     | constraint | description |
| ------------------- | -------- | ---------- | ----------- |
| » jobId             | string   | none       |             |
| » jobName           | string   | none       |             |
| » description       | string   | none       |             |
| » owner             | string   | none       |             |
| » status            | string   | none       |             |
| » tasks             | [object] | none       |             |
| »» taskId           | string   | none       |             |
| »» taskName         | string   | none       |             |
| »» toolId           | string   | none       |             |
| »» args             | [object] | none       |             |
| »»» paramName       | string   | none       |             |
| »»» value           | string   | none       |             |
| »»» attributes      | object   | none       |             |
| »»»» isOutputParam  | boolean  | none       |             |
| »»»» fileType       | string   | none       |             |
| »»»» multiple       | boolean  | none       |             |
| »»» paramAttributes | object   | none       |             |
| »»»» name           | string   | none       |             |
| »»»» dataType       | string   | none       |             |
| »»»» description    | string   | none       |             |
| »»»» engDescription | string   | none       |             |
| »»»» required       | boolean  | none       |             |
| »»»» in             | integer  | none       |             |
| »»»» default        | string   | none       |             |
| »» upstream         | [string] | none       |             |
| »» x                | number   | none       |             |
| »» y                | integer  | none       |             |
| » startDate         | string   | none       |             |
| » endDate           | string   | none       |             |

### **GET /v1.0/job**

GET /v1.0/job

#### request parameter

| name     | location | type   | necessary | description |
| -------- | -------- | ------ | --------- | ----------- |
| page     | query    | string | yes       | none        |
| pageSize | query    | string | yes       | none        |
| rzpj     | header   | string | yes       | none        |

> return example

> success

```Plain
{
  "jobCount": 3,
  "jobs": [
    {
      "jobId": "db38561f-c28e-4da4-af11-ef1dc8d71d5b",
      "jobName": "crust_0-23Ma-job03",
      "description": "",
      "startTime": 1656557873531,
      "owner": "99bca0f1-4fea-4cdc-bbc4-f14d4813fb9a",
      "jobDetail": "{}",
      "status": "success",
      "jobExpiredDelete": false,
      "startDate": "2022-06-29 19:00:14.290424-08",
      "endDate": "2022-06-29 19:00:29.592692-08"
    },
    {
      "jobId": "20860c3e-ecba-47a4-b0d0-2de48aae5561",
      "jobName": "crust_0-23Ma-job02 ",
      "description": "",
      "startTime": 1656508437475,
      "owner": "99bca0f1-4fea-4cdc-bbc4-f14d4813fb9a",
      "jobDetail": "{}",
      "status": "failed",
      "jobExpiredDelete": false,
      "startDate": "2022-06-29 05:14:26.549899-08",
      "endDate": "2022-06-29 05:19:55.907718-08"
    },
    {
      "jobId": "7642d78d-8968-41fa-bf51-03c1db6422bf",
      "jobName": "crust_0-23Ma",
      "description": "",
      "startTime": 1656507611172,
      "owner": "99bca0f1-4fea-4cdc-bbc4-f14d4813fb9a",
      "jobDetail": "{}",
      "status": "failed",
      "jobExpiredDelete": false,
      "startDate": "2022-06-29 05:04:26.223108-08",
      "endDate": "2022-06-29 05:09:59.446602-08"
    }
  ]
}
```

#### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

#### return structure

status code **200**

| name                | type     | constraint | description |
| ------------------- | -------- | ---------- | ----------- |
| » jobCount          | integer  | none       |             |
| » jobs              | [object] | none       |             |
| »» jobId            | string   | none       |             |
| »» jobName          | string   | none       |             |
| »» description      | string   | none       |             |
| »» startTime        | integer  | none       |             |
| »» owner            | string   | none       |             |
| »» jobDetail        | string   | none       |             |
| »» status           | string   | none       |             |
| »» jobExpiredDelete | boolean  | none       |             |
| »» startDate        | string   | none       |             |
| »» endDate          | string   | none       |             |

## Workflow Tool

### **GET /v1.0/toolsv2/{id}**

GET /v1.0/toolsv2/{toolId}

#### request parameter

| name   | location | type   | necessary | description |
| ------ | -------- | ------ | --------- | ----------- |
| toolId | path     | string | yes       | none        |
| rzpj   | header   | string | yes       | Certificate |

> return example

> success

```Plaintext
{
  "id": "351a8f1a-3c30-477c-a583-c490d055e6a3",
  "engName": "smoothing",
  "name": "矢量简化与平滑",
  "usage": "smoothing-对矢量数据进行简化和平滑锐角",
  "engUsage": "Simplify and smooth sharp angles on vector data.",
  "details": "按照某种规则在保证矢量整体形状的情况下删减部分图形节点，并圆滑边界的棱角和节点",
  "engDetails": "According to some rules to ensure the overall shape of the vector to delete part of the graphics nodes, and round the edges and nodes of the boundary.",
  "frameworkType": "docker",
  "imageName": "zjugis-fuxi/gvs:v0.1",
  "reference": "https://www.osgeo.cn/gdal/programs/vector_common_options.html#vector-common-options | https://gis.stackexchange.com/questions/122736/making-buffer-from-line-using-gdal-and-python",
  "className": "/Scene/Paleogeographic reconstruction/Vectorization/Smoothing",
  "date": null,
  "versionId": "0.1",
  "groupId": "SWJTU",
  "authorId": "Zhilin Li",
  "email": null,
  "tagNames": [
    "Vectorization"
  ],
  "tags": [
    {
      "tagName": "Vectorization",
      "tagType": "TOOL"
    }
  ],
  "inputData": [
    {
      "name": "path_data_vec",
      "fileStored": "obs",
      "fileType": "FILE",
      "suffix": [
        "shp"
      ],
      "description": "矢量岩相板块数据",
      "engDescription": "Vector petrographic plate data",
      "displayType": "FILE",
      "multiple": false
    }
  ],
  "outputData": [
    {
      "name": "vec_smooth_result",
      "fileStored": "obs",
      "fileType": "FILE",
      "suffix": [
        "shp"
      ],
      "description": "简化与平滑后矢量数据",
      "engDescription": "Vector data after simplification and smoothing",
      "displayType": "FILE",
      "multiple": false
    }
  ],
  "parameters": [
    {
      "name": "bdistance",
      "dataType": "NUMBER",
      "description": "可以根据影像分辨率设定，不能低于影像分辨率",
      "engDescription": "Can be set according to the image resolution, not lower than the image resolution",
      "required": true,
      "in": 0,
      "default": "0.3"
    }
  ],
  "test": [
    {
      "in": [
        {
          "name": "path_data_vec",
          "value": "vec_test.shp",
          "desc": ""
        }
      ],
      "out": [],
      "cmdLine": "python smoothing.py -p ${path_data_vec} -o ${vec_smooth_result} -b ${bdistance}"
    }
  ],
  "updateTime": 1656494036490,
  "publishTime": 1656494036490,
  "privilege": "PUBLIC",
  "mdPath": "https://deepengine.oss-cn-hangzhou.aliyuncs.com/workspace/ADMIN/share/markdown/smoothing.md",
  "atomType": null,
  "official": "OFFICIAL",
  "isGPUSupport": false
}
```

#### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

#### return structure

status code **200**

| name              | type     | constraint | description          |
| ----------------- | -------- | ---------- | -------------------- |
| » id              | string   | none       | none                 |
| » engName         | string   | none       | Model describe in en |
| » name            | string   | none       | Name                 |
| » usage           | string   | none       | Usage                |
| » engUsage        | string   | none       | Usage describe in en |
| » details         | string   | none       | none                 |
| » engDetails      | string   | none       | none                 |
| » frameworkType   | string   | none       | Framework used       |
| » imageName       | string   | none       | none                 |
| » reference       | string   | none       | none                 |
| » className       | string   | none       | none                 |
| » date            | null     | none       | none                 |
| » versionId       | string   | none       | none                 |
| » groupId         | string   | none       | none                 |
| » authorId        | string   | none       | none                 |
| » email           | null     | none       | none                 |
| » tagNames        | [string] | none       | none                 |
| » tags            | [object] | none       | none                 |
| »» tagName        | string   | none       | none                 |
| »» tagType        | string   | none       | none                 |
| » inputData       | [object] | none       | none                 |
| »» name           | string   | none       | none                 |
| »» fileStored     | string   | none       | none                 |
| »» fileType       | string   | none       | none                 |
| »» suffix         | [string] | none       | none                 |
| »» description    | string   | none       | none                 |
| »» engDescription | string   | none       | none                 |
| »» displayType    | string   | none       | none                 |
| »» multiple       | boolean  | none       | none                 |
| » outputData      | [object] | none       | none                 |
| »» name           | string   | none       | none                 |
| »» fileStored     | string   | none       | none                 |
| »» fileType       | string   | none       | none                 |
| »» suffix         | [string] | none       | none                 |
| »» description    | string   | none       | none                 |
| »» engDescription | string   | none       | none                 |
| »» displayType    | string   | none       | none                 |
| »» multiple       | boolean  | none       | none                 |
| » parameters      | [object] | none       | none                 |
| »» name           | string   | none       | none                 |
| »» dataType       | string   | none       | none                 |
| »» description    | string   | none       | none                 |
| »» engDescription | string   | none       | none                 |
| »» required       | boolean  | none       | none                 |
| »» in             | integer  | none       | none                 |
| »» default        | string   | none       | none                 |
| » test            | [object] | none       | none                 |
| »» in             | [object] | none       | none                 |
| »»» name          | string   | none       | none                 |
| »»» value         | string   | none       | none                 |
| »»» desc          | string   | none       | none                 |
| »» out            | [string] | none       | none                 |
| »» cmdLine        | string   | none       | none                 |
| » updateTime      | integer  | none       | none                 |
| » publishTime     | integer  | none       | none                 |
| » privilege       | string   | none       | none                 |
| » mdPath          | string   | none       | none                 |
| » atomType        | null     | none       | none                 |
| » official        | string   | none       | Is it official       |
| » isGPUSupport    | boolean  | none       | none                 |

### **GET /v1.0/toolsv2/getTools**

GET /v1.0/toolsv2/getTools

#### request parameter

| name    | location | type   | necessary | description |
| ------- | -------- | ------ | --------- | ----------- |
| algebra | query    | string | yes       | none        |
| start   | query    | string | yes       | none        |
| length  | query    | string | yes       | none        |
| path    | query    | string | no        | toolpath    |
| keyword | query    | string | no        | keyword     |
| rzpj    | header   | string | no        | Certificate |

> return example

> success

```Plaintext
{
  "totalCount": 2,
  "tools": [
    {
      "id": "e218a423-6239-4e6b-9fe4-6f732ccf67bf",
      "engName": "Select Time",
      "name": "筛选时间范围",
      "usage": "筛选指定时间范围的数据",
      "engUsage": "Filter data for a specified time range.",
      "details": "根据起始时间对指定字段进行筛选",
      "engDetails": "Filter the specified fields based on the start and end date.",
      "frameworkType": "docker",
      "imageName": "zjugis-fuxi/pydde:0.2",
      "reference": null,
      "className": "/Data Management/Filter/Select Time",
      "date": null,
      "versionId": "0.1",
      "groupId": "Central South University",
      "authorId": "Minghui Li",
      "email": null,
      "tagNames": [
        "Filter"
      ],
      "tags": [
        {
          "tagName": "Filter",
          "tagType": "TOOL"
        }
      ],
      "inputData": [
        {
          "name": "input",
          "fileStored": "obs",
          "fileType": "FILE",
          "suffix": [
            "csv",
            "shp",
            "xls",
            "xlsx"
          ],
          "description": "被筛选数据",
          "engDescription": "Filtered data",
          "displayType": "FILE",
          "multiple": false
        }
      ],
      "outputData": [
        {
          "name": "output",
          "fileStored": "obs",
          "fileType": "FILE",
          "suffix": [
            "csv",
            "shp",
            "xls",
            "xlsx"
          ],
          "description": "筛选时间范围结果",
          "engDescription": "Filter results.",
          "displayType": "FILE",
          "multiple": false
        }
      ],
      "parameters": [
        {
          "name": "fields",
          "dataType": "STRING",
          "description": "被筛选的字段名"",
          "engDescription": "Filtered field name",
          "required": true,
          "in": 0,
          "default": ""
        },
        {
          "name": "start_date",
          "dataType": "STRING",
          "description": "时间范围开始时间",
          "engDescription": "Time range start time",
          "required": true,
          "in": 0,
          "default": ""
        },
        {
          "name": "end_date",
          "dataType": "STRING",
          "description": "时间范围结束时间",
          "engDescription": "Time range end time",
          "required": true,
          "in": 0,
          "default": ""
        },
        {
          "name": "greater_or_equal",
          "dataType": "STRING",
          "description": "是否大于等于。默认为否，如需大于等于则填写\"--goe\"",
          "engDescription": "Whether it is greater than or equal to. The default value is No. if it needs to be greater than or equal to, fill in \"--goe\"",
          "required": false,
          "in": 0,
          "default": ""
        },
        {
          "name": "lesser_or_equal",
          "dataType": "STRING",
          "description": "是否小于等于。默认为是，如否则填写\"--loe\"",
          "engDescription": "Whether it is less than or equal to. The default value is yes. Otherwise, fill in \"--loe\"",
          "required": false,
          "in": 0,
          "default": ""
        },
        {
          "name": "fields_dateformat",
          "dataType": "STRING",
          "description": "被筛选的字段时间格式",
          "engDescription": "Filtered field time format",
          "required": true,
          "in": 0,
          "default": ""
        },
        {
          "name": "express_dateformat",
          "dataType": "STRING",
          "description": "开始/结束时间格式",
          "engDescription": "Start / end time format",
          "required": true,
          "in": 0,
          "default": "%Y-%m-%d %H:%M:%S"
        }
      ],
      "test": [
        {
          "in": [
            {
              "name": "input",
              "value": "theftcrime2019.shp, theftcrime2019.csv, theftcrime2019.xls, theftcrime2019.xlsx",
              "desc": ""
            }
          ],
          "out": [],
          "cmdLine": "python demo-tmp_sel_time.py --input ${input} --fields ${fields} --startdate ${start_date} --enddate ${end_date} ${greater_or_equal} ${lesser_or_equal} --fieldsdateformat ${fields_dateformat} --expressdateformat ${express_dateformat} --output ${output}"
        }
      ],
      "updateTime": 1652442840887,
      "publishTime": 1651304266466,
      "privilege": "PUBLIC",
      "mdPath": "https://deepengine.oss-cn-hangzhou.aliyuncs.com/workspace/ADMIN/share/markdown/Select_Time.md",
      "atomType": null,
      "official": "OFFICIAL",
      "isGPUSupport": false
    },
    {
      "id": "aa3181e8-b1cf-4e40-bcb0-6208c0e61768",
      "engName": "Time Series Probability Plot",
      "name": "Time Series Probability Plot",
      "usage": "时间序列概率分布图",
      "engUsage": "Conduct Detrital Zircons age analysis based on the time series probability plot. ",
      "details": "时间序列概率分布图",
      "engDetails": "The model uses matplotlib to render data and set styles.",
      "frameworkType": "docker",
      "imageName": "zjugis-fuxi/detritalpy:0.8",
      "reference": "Sharman, G. R., Sharman, J. P., & Sylvester, Z. (2018). detritalPy: A Pythonâbased toolset for visualizing and analysing detrital geoâthermochronologic data. The Depositional Record, 4(2), 202-215.",
      "className": "/Scene/Geological Analysis/Zircon Analysis/Time Series Probability Plot",
      "date": "",
      "versionId": "0.4",
      "groupId": "Zhejiang University",
      "authorId": "Zhenhong Du",
      "email": "",
      "tagNames": [
        "Onesediment"
      ],
      "tags": [],
      "inputData": [
        {
          "name": "input",
          "fileStored": "obs",
          "fileType": "FILE",
          "suffix": [
            "xlsx"
          ],
          "description": "输入表格数据",
          "engDescription": "input table data",
          "properties": [],
          "multiple": false
        }
      ],
      "outputData": [
        {
          "name": "output",
          "fileStored": "obs",
          "fileType": "FILE",
          "suffix": [
            "pdf"
          ],
          "description": "输出图像",
          "engDescription": "result plot",
          "properties": [],
          "displayType": "FILE",
          "multiple": false
        }
      ],
      "parameters": [
        {
          "name": "agg_field",
          "dataType": "STRING",
          "description": "聚合作图的字段名",
          "engDescription": "the field to aggregate",
          "required": true,
          "in": 0,
          "enums": [],
          "default": ""
        },
        {
          "name": "time_range",
          "dataType": "STRING",
          "description": "时间序列分析时间段（Ma）；[0,3000]",
          "engDescription": "time range for time series (Ma), e.g.: [0, 3000]",
          "required": true,
          "in": 0,
          "enums": [
            "1"
          ],
          "default": ""
        },
        {
          "name": "if_subplot",
          "dataType": "STRING",
          "description": "是否分为子图；yes, no",
          "engDescription": "if to seperate as subplots, e.g.: yes, no",
          "required": true,
          "in": 0,
          "enums": [
            "1"
          ],
          "default": ""
        },
        {
          "name": "plot_type",
          "dataType": "STRING",
          "description": "绘图类型；KDE, PDP",
          "engDescription": "plot type, e.g.: KDE, PDP",
          "required": true,
          "in": 0,
          "enums": [
            "1"
          ],
          "default": ""
        },
        {
          "name": "if_CI",
          "dataType": "STRING",
          "description": "是否画置信区间；yes, no",
          "engDescription": "if plot confidential interval, e.g.: yes, no",
          "required": true,
          "in": 0,
          "enums": [
            "1"
          ],
          "default": ""
        },
        {
          "name": "if_hist",
          "dataType": "STRING",
          "description": "是否画直方图；yes, no",
          "engDescription": "if plot histogram, e.g.: yes, no",
          "required": true,
          "in": 0,
          "enums": [
            "1"
          ],
          "default": ""
        },
        {
          "name": "in_agebins",
          "dataType": "STRING",
          "description": "年龄划分子区间；",
          "engDescription": "age bins for coloring",
          "required": true,
          "in": 0,
          "enums": [
            "1"
          ],
          "default": ""
        },
        {
          "name": "in_agebinsc",
          "dataType": "STRING",
          "description": "年龄划分子区间对应的颜色；",
          "engDescription": "colors for age bins",
          "required": true,
          "in": 0,
          "enums": [
            "1"
          ],
          "default": ""
        },
        {
          "name": "plot_size",
          "dataType": "STRING",
          "description": "图片大小，宽高1高2；[10,4,5]",
          "engDescription": "size of figures, e.g.: [width, height1, height2]",
          "required": true,
          "in": 0,
          "enums": [
            "1"
          ],
          "default": ""
        }
      ],
      "test": [
        {
          "in": [],
          "out": [],
          "cmdLine": "python /home/plotAll.py ${input} ${agg_field} ${time_range} ${if_subplot} ${plot_type} ${if_CI} ${if_hist} ${in_agebins} ${in_agebinsc} ${plot_size} ${output}"
        }
      ],
      "updateTime": 1642930000000,
      "publishTime": 1641490000000,
      "privilege": "PUBLIC",
      "mdPath": "https://deepengine.oss-cn-hangzhou.aliyuncs.com/workspace/ADMIN/share/markdown/Time_Series_Probability_Plot.md",
      "atomType": null,
      "official": "OFFICIAL",
      "isGPUSupport": false
    }
  ]
}
```

#### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

#### return structure

status code **200**

| name               | type        | constraint | description     |
| ------------------ | ----------- | ---------- | --------------- |
| » totalCount       | integer     | none       | Number of tools |
| » tools            | [object]    | none       | none            |
| »» id              | string      | none       | none            |
| »» engName         | string      | none       | none            |
| »» name            | string      | none       | none            |
| »» usage           | string      | none       | none            |
| »» engUsage        | string      | none       | none            |
| »» details         | string      | none       | none            |
| »» engDetails      | string      | none       | none            |
| »» frameworkType   | string      | none       | none            |
| »» imageName       | string      | none       | none            |
| »» reference       | string¦null | none       | none            |
| »» className       | string      | none       | none            |
| »» date            | string¦null | none       | none            |
| »» versionId       | string      | none       | none            |
| »» groupId         | string      | none       | none            |
| »» authorId        | string      | none       | none            |
| »» email           | string¦null | none       | none            |
| »» tagNames        | [string]    | none       | none            |
| »» tags            | [object]    | none       | none            |
| »»» tagName        | string      | none       | none            |
| »»» tagType        | string      | none       | none            |
| »» inputData       | [object]    | none       | none            |
| »»» name           | string      | none       | none            |
| »»» fileStored     | string      | none       | none            |
| »»» fileType       | string      | none       | none            |
| »»» suffix         | [string]    | none       | none            |
| »»» description    | string      | none       | none            |
| »»» engDescription | string      | none       | none            |
| »»» displayType    | string      | none       | none            |
| »»» multiple       | boolean     | none       | none            |
| »»» properties     | [string]    | none       | none            |
| »» outputData      | [object]    | none       | none            |
| »»» name           | string      | none       | none            |
| »»» fileStored     | string      | none       | none            |
| »»» fileType       | string      | none       | none            |
| »»» suffix         | [string]    | none       | none            |
| »»» description    | string      | none       | none            |
| »»» engDescription | string      | none       | none            |
| »»» displayType    | string      | none       | none            |
| »»» multiple       | boolean     | none       | none            |
| »»» properties     | [string]    | none       | none            |
| »» parameters      | [object]    | none       | none            |
| »»» name           | string      | none       | none            |
| »»» dataType       | string      | none       | none            |
| »»» description    | string      | none       | none            |
| »»» engDescription | string      | none       | none            |
| »»» required       | boolean     | none       | none            |
| »»» in             | integer     | none       | none            |
| »»» default        | string      | none       | none            |
| »»» enums          | [string]    | none       | none            |
| »» test            | [object]    | none       | none            |
| »»» in             | [object]    | none       | none            |
| »»»» name          | string      | none       | none            |
| »»»» value         | string      | none       | none            |
| »»»» desc          | string      | none       | none            |
| »»» out            | [string]    | none       | none            |
| »»» cmdLine        | string      | none       | none            |
| »» updateTime      | integer     | none       | none            |
| »» publishTime     | integer     | none       | none            |
| »» privilege       | string      | none       | none            |
| »» mdPath          | string      | none       | none            |
| »» atomType        | null        | none       | none            |
| »» official        | string      | none       | Is it official  |
| »» isGPUSupport    | boolean     | none       | none            |

## Workflow Monitor

### **GET /v1.0/atlas/sls/getSlsLogs**

GET /v1.0/atlas/sls/getSlsLogs

#### request parameter

| name   | location | type   | necessary | description |
| ------ | -------- | ------ | --------- | ----------- |
| taskId | query    | string | yes       | none        |
| jobId  | query    | string | yes       | none        |
| rzpj   | header   | string | no        | Certificate |

> return example

> success

```Plain
{
  "msg": "query was successful",
  "code": 200,
  "data": [
    "[2022-06-30 03:00:14,735] {logging_mixin.py:109} INFO - Running <TaskInstance: db38561f-c28e-4da4-af11-ef1dc8d71d5b.t0 2022-06-29T19:00:11.748858+00:00 [running]> on host dde-airflow-scheduler-0.dde-airflow-scheduler.airflow.svc.cluster.local",
    "AIRFLOW_CTX_DAG_EMAIL=airflow@example.com",
    "AIRFLOW_CTX_DAG_ID=db38561f-c28e-4da4-af11-ef1dc8d71d5b",
    "AIRFLOW_CTX_EXECUTION_DATE=2022-06-29T19:00:11.748858+00:00",
    "[2022-06-30 03:00:14,857] {kubernetes_pod.py:366} INFO - creating pod with labels {'dag_id': 'db38561f-c28e-4da4-af11-ef1dc8d71d5b', 'task_id': 't0', 'execution_date': '2022-06-29T190011.7488580000-e9f114728', 'try_number': '1'} and launcher <airflow.providers.cncf.kubernetes.utils.pod_launcher.PodLauncher object at 0x7f8e7760ef10>",
    "[2022-06-30 03:00:14,895] {pod_launcher.py:128} WARNING - Pod not yet started: t0.a3c254bf66814d448041a6c87bb0bc8c",
    "[2022-06-30 03:00:27,190] {pod_launcher.py:149} INFO -   warnings.warn(",
    "[2022-06-30 03:00:27,191] {pod_launcher.py:149} INFO - Namespace(extent='80,92,29,32', n=12, output='/volume/workspace/99bca0f1-4fea-4cdc-bbc4-f14d4813fb9a/userData/crust/thickness/0_23Ma.tif', point='/volume/workspace/99bca0f1-4fea-4cdc-bbc4-f14d4813fb9a/userData/crust/thickness/0_23Ma.csv', r=None, xid=2, xstep=0.1, yid=1, ystep=0.1, zid=0)",
    "[2022-06-30 03:00:27,191] {pod_launcher.py:149} INFO - inverse distance weighting interpolation finished.",
    "[2022-06-30 03:00:29,361] {local_task_job.py:151} INFO - Task exited with return code 0",
    "[2022-06-30 03:00:14,599] {taskinstance.py:903} INFO - Dependencies all met for <TaskInstance: db38561f-c28e-4da4-af11-ef1dc8d71d5b.t0 2022-06-29T19:00:11.748858+00:00 [queued]>",
    "[2022-06-30 03:00:14,621] {taskinstance.py:1095} INFO - ",
    "[2022-06-30 03:00:14,621] {taskinstance.py:1096} INFO - Starting attempt 1 of 2",
    "--------------------------------------------------------------------------------",
    "[2022-06-30 03:00:14,633] {standard_task_runner.py:52} INFO - Started process 24256 to run task",
    "[2022-06-30 03:00:14,639] {standard_task_runner.py:77} INFO - Job 360: Subtask t0"
  ]
}
```

#### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

#### return structure

status code **200**

| name   | type     | constraint | description |
| ------ | -------- | ---------- | ----------- |
| » msg  | string   | none       | Status msg  |
| » code | integer  | none       | Status code |
| » data | [string] | none       | none        |

### **GET** **/v1.0/atlas/task/getTaskIdByState**

GET /v1.0/atlas/task/getTaskIdByState

dag_id return the corresponding task_id and state.

#### request parameter

| name         | location | type   | necessary | description |
| ------------ | -------- | ------ | --------- | ----------- |
| dagId        | query    | string | yes       | none        |
| rzpj         | header   | string | yes       | Certificate |
| Content-Type | header   | string | yes       | none        |

> return example

> success

```Plain
[
  {
    "taskId": "t1",
    "state": "failed"
  },
  {
    "taskId": "t2",
    "state": "failed"
  },
  {
    "taskId": "t0",
    "state": "upstream_failed"
  }
]
```

#### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

#### return structure

status code **200**

| name     | type   | constraint | description |
| -------- | ------ | ---------- | ----------- |
| » taskId | string | none       | none        |
| » state  | string | none       | none        |

# Knowledge Hub API v0.7.8

## GET /geoopenkg/api/search/compound

Search based on specified search criteria

### request parameter

| name            | location | type   | necessary | description                                                  |
| --------------- | -------- | ------ | --------- | ------------------------------------------------------------ |
| keyword         | query    | string | no        | Search keywords                                              |
| isPrecise       | query    | string | no        | Is it an exact query                                         |
| containInstance | query    | string | no        | Whether the instance is included                             |
| source          | query    | string | no        | SOURCE，Value = BO4GK、GAKG、GPKG，Separate multiple values with commas (,) |
| discipline      | query    | string | no        | discipline，Separate different disciplines with commas (,)   |
| pageNum         | query    | string | no        | The number of pages. Default value: 1                        |
| pageSize        | query    | string | no        | The number of entries to return on each page. Default value: 10 |

> return example

```Plaintext
{
    "code": 200,
    "message": "success",
    "data": {
        "total": 99,
        "GPKG": {
            "total": 77,
            "rows": [
                {
                    "name": "Spatial Scale",
                    "description": "The spatial scale depends on the cause of the chemostratigraphic index/marker being local, regional, basinal, and global, based on which, the chemozone recognized could be correlated at an appropriate scale.",
                    "source": "GPKG",
                    "id": 1262,
                    "discipline": 1,
                    "label": "Class",
                    "uri": "Spatial Scale"
                },
                {
                    "name": "Spatial resolution_1",
                    "description": "The beam size of focused primary beam.",
                    "source": "GPKG",
                    "id": 28911,
                    "discipline": 3,
                    "label": "Class",
                    "uri": "Spatial resolution_1"
                },
                {
                    "name": "Caprock spatial area",
                    "description": "The spatial area of caprock.Cover distribution range",
                    "source": "GPKG",
                    "id": 31958,
                    "discipline": 16,
                    "label": "Class",
                    "uri": "Caprock spatial area"
                },
                {
                    "name": "Spatial filters",
                    "description": "The spatial filtering is a method of image filtering by convolution operation based on the spatial relationship between pixels and surrounding neighborhood pixels.",
                    "source": "GPKG",
                    "id": 32283,
                    "discipline": 12,
                    "label": "Class",
                    "uri": "Spatial filters"
                },
                {
                    "name": "Gravity spatial variation",
                    "description": " The gravity varies from the equator to the poles of rotation by about 0.5%, changing by slightly more than 5 Gal from approximately 978 Gal at the equator to 983 Gal at the poles. First, one more important factor which accounts for more than 3 of the 5 Gal, is the change in the centrifugal force over the Earth’s surface caused by the Earth’s rotation around its axis. The second factor of the planetary change in gravity (about 6Gal) over the Earth’ s surface is the variation in the radius from the equator to the poles. Finally, the subsurface mass with density contrast will cause several hundred mGal.",
                    "source": "GPKG",
                    "id": 32351,
                    "discipline": 12,
                    "label": "Class",
                    "uri": "Gravity spatial variation"
                },
                {
                    "name": "Classified by spatial distribution characteristics",
                    "description": "According to the characteristics of spatial distribution, map symbols are divided into point symbols, linear symbols and Planar symbols.",
                    "source": "GPKG",
                    "id": 39544,
                    "discipline": 13,
                    "label": "Class",
                    "uri": "Classified by spatial distribution characteristics"
                },
                {
                    "name": "Spatial oblique Mercator projection",
                    "description": "An oblique pseudo-cylindrical projection in which the central axis of a cylinder is perpendicular to the plane of the satellite orbit. It is suitable for cartography of narrow areas extending along the direction of satellite orbit.",
                    "source": "GPKG",
                    "id": 39664,
                    "discipline": 13,
                    "label": "Class",
                    "uri": "Spatial oblique Mercator projection"
                },
                {
                    "name": "Spatial data reference information",
                    "description": "Spatial Reference Information -- the description of the reference frame for, and the means to encode, coordinates in the data set.",
                    "source": "GPKG",
                    "id": 40091,
                    "discipline": 13,
                    "label": "Class",
                    "uri": "Spatial data reference information"
                },
                {
                    "name": "Spatial database",
                    "description": "A spatial database is a database that is optimized for storing and querying data that represents objects defined in a geometric space. ",
                    "source": "GPKG",
                    "id": 40117,
                    "discipline": 13,
                    "label": "Class",
                    "uri": "Spatial database"
                },
                {
                    "name": "Spatial data type",
                    "description": "The most general shape is represented by the geometry described by the spatial representation system, which is a coordinate system similar to longitude and latitude or other accepted frames.",
                    "source": "GPKG",
                    "id": 40118,
                    "discipline": 13,
                    "label": "Class",
                    "uri": "Spatial data type"
                }
            ]
        },
        "GAKG": {
            "total": 3,
            "rows": [
                {
                    "name": "paper",
                    "lable": "Class",
                    "description": "Papers are often used to refer to articles that conduct research in various academic fields and describe academic research results.",
                    "id": "1",
                    "source": "GAKG",
                    "discipline": "GeoScience",
                    "uri": "https://www.acekg.cn/concept#paper"
                },
                {
                    "name": "journal",
                    "lable": "ObjectProperty",
                    "description": "A relationship between the paper and the author.",
                    "id": "3",
                    "source": "GAKG",
                    "discipline": "GeoScience",
                    "uri": "https://www.acekg.cn/relation#is_written_by"
                },
                {
                    "lable": "Class",
                    "description": "A peer-reviewed journal in which articles published in academic journals usually involve specific disciplines.",
                    "source": "GAKG",
                    "discipline": "GeoScience",
                    "uri": "https://www.acekg.cn/concept#journal"
                }
            ]
        },
        "time": 175,
        "BO4GK": {
            "total": 22,
            "rows": [
                {
                    "id": "graph3_16440",
                    "source": "BO4GK",
                    "label": "ObjectProperty",
                    "uri": "http://bo4gk.org/uso#geometry_op",
                    "name": "geometry_op",
                    "description": "object properties for geometry of spatial objects",
                    "discipline": "Spatial Ontology"
                },
                {
                    "id": "graph3_16448",
                    "source": "BO4GK",
                    "label": "Class",
                    "uri": "http://bo4gk.org/uso#geometry_type",
                    "name": "geometry_type",
                    "description": "describing the geometry type of spatial object",
                    "discipline": "Spatial Ontology"
                },
                {
                    "id": "graph3_28736",
                    "source": "BO4GK",
                    "label": "Class",
                    "uri": "http://bo4gk.org/uso#location",
                    "name": "location",
                    "description": "class showing where is a spatial object.",
                    "discipline": "Spatial Ontology"
                },
                {
                    "id": "graph3_4224",
                    "source": "BO4GK",
                    "label": "ObjectProperty",
                    "uri": "http://bo4gk.org/uso#geometry_dp",
                    "name": "geometry_dp",
                    "description": "data properties for geometry of spatial objects",
                    "discipline": "Spatial Ontology"
                },
                {
                    "id": "graph5_45168",
                    "source": "BO4GK",
                    "label": "Class",
                    "uri": "http://bo4gk.org/crs#extent",
                    "name": "extent",
                    "description": "applicable spatial extent of a coordinate reference system",
                    "discipline": "Spatial Ontology"
                },
                {
                    "id": "graph3_8248",
                    "source": "BO4GK",
                    "label": "ObjectProperty",
                    "uri": "http://bo4gk.org/uso#has_geometry_form",
                    "name": "has_geometry_form",
                    "description": "form of representing the geometry of spatial objects",
                    "discipline": "Spatial Ontology"
                },
                {
                    "id": "graph3_20536",
                    "source": "BO4GK",
                    "label": "ObjectProperty",
                    "uri": "http://bo4gk.org/uso#has_geometry_members",
                    "name": "has_geometry_members",
                    "description": "members of the combine geometry of spatial objects",
                    "discipline": "Spatial Ontology"
                },
                {
                    "id": "graph3_24640",
                    "source": "BO4GK",
                    "label": "ObjectProperty",
                    "uri": "http://bo4gk.org/uso#has_geometry_type",
                    "name": "has_geometry_type",
                    "description": "describing type of geometric representations of spatial objects.",
                    "discipline": "Spatial Ontology"
                },
                {
                    "id": "graph3_8352",
                    "source": "BO4GK",
                    "label": "Class",
                    "uri": "http://bo4gk.org/uso#location_type",
                    "name": "location_type",
                    "description": "the type showing the location of spatial ojects",
                    "discipline": "Spatial Ontology"
                },
                {
                    "id": "graph3_20640",
                    "source": "BO4GK",
                    "label": "ObjectProperty",
                    "uri": "http://bo4gk.org/uso#has_location_value",
                    "name": "has_location_value",
                    "description": "the value of location of a spatial object",
                    "discipline": "Spatial Ontology"
                }
            ]
        }
    }
}
```

### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

### return structure

| name      | type     | constraint | description    |
| --------- | -------- | ---------- | -------------- |
| » code    | integer  | none       | Status code    |
| » message | string   | none       | Status message |
| » data    | [string] | none       | Data           |

## Jupyter

### GET /v1.0/api/jupyter/user

GET /v1.0/api/jupyter/user

#### request parameter

| name     | location | type   | necessary | description                                                  |
| -------- | -------- | ------ | --------- | ------------------------------------------------------------ |
| page     | query    | string | yes       | In the previous page, if you want to display the first page, use 0 |
| pageSize | query    | string | yes       | Number of Entries displayed per page                         |
| rzpj     | header   | string | yes       | Certificate                                                  |

> return example

> success

```Plaintext
{
    "jupyters": [
        {
            "userId": "DDE",
            "notebookName": "notebook1",
            "imageName": "zjugis/jupyterlab:0.31",
            "deploymentName": "notebook1",
            "serviceName": "jupyterlab-da36d413-d35e-4bfc-9562-33f2d69f54c8",
            "port": 30018,
            "resourceCPU": 600,
            "kernelCPU": 0.6,
            "resourceGPU": 600,
            "kernelGPU": 0.6,
            "resourceMemory": 1262,
            "startTime": 1649680748007,
            "endTime": 1649695148007,
            "status": "PAUSE",
            "url": "http://47.98.212.54:30018/notebook/lab"
        },
        {
            "userId": "DDE",
            "notebookName": "notebook1",
            "imageName": "zjugis/jupyterlab:0.31",
            "deploymentName": "notebook2",
            "serviceName": "jupyterlab-da36d413-d35e-4bfc-9562-33f2d69f54c8",
            "port": 30018,
            "resourceCPU": 600,
            "kernelCPU": 0.6,
            "resourceGPU": 600,
            "kernelGPU": 0.6,
            "resourceMemory": 1262,
            "startTime": 1649680748007,
            "endTime": 1649695148007,
            "status": "PAUSE",
            "url": "http://47.98.212.54:30018/notebook/lab"
        }
    ],
    "totalCount": 2
}
```

#### return result

| status code | status code message                                     | description | data mode |
| ----------- | ------------------------------------------------------- | ----------- | --------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success     | Inline    |

#### return structure

status code **200**

| name              | type     | constraint | description         |
| ----------------- | -------- | ---------- | ------------------- |
| » jupyters        | [object] | none       | Jupyter information |
| »» userId         | string   | none       | Userid              |
| »» notebookName   | string   | none       | Notebook name       |
| »» imageName      | string   | none       | Image name          |
| »» deploymentName | string   | none       | Deployment name     |
| »» serviceName    | string   | none       | Service name        |
| »» port           | integer  | none       | Port                |
| »» resourceCPU    | integer  | none       | Resource CPU        |
| »» kernelCPU      | number   | none       | Kernel CPU          |
| »» resourceGPU    | integer  | none       | Resource GPU        |
| »» kernelGPU      | number   | none       | Kernel GPU          |
| »» resourceMemory | integer  | none       | Resource memory     |
| »» startTime      | integer  | none       | Start time          |
| »» endTime        | integer  | none       | End time            |
| »» status         | string   | none       | Status              |
| »» url            | string   | none       | URL                 |
| » field1          | string   | none       | Field               |
| » totalCount      | integer  | none       | Number of Users     |

# Earth Explorer SDK v0.7.8

## iframe代码

### 在html中添加iframe

```html
<iframe id="mapView" src="http://dev.deeptime-engine.com/map/#/showcase" />
```

### 添加通信事件

```typescript
document.getElementById('mapView').contentWindow.postMessage({
  type: EventType,
  body: EventBody
}: IframeEvents, '*');

type IframeEvents = AddLayerEvent | RemoveLayerEvent | MoveLayerByIdEvent | AddPointEvent | RemovePointEvent | ComponentConfigEvent | MapConfigEvent | CartographyEvent | OpenToolEvent;
```

### 示例代码

```javascript
// 添加一个点
document.getElementById('mapView').contentWindow.postMessage({
    type: 'addPoint',
    body: {
      id: 'old',
      position:[120, 30] ,
      style: {
        color: '#f47920',
        pixelSize: 10,
        outlineColor: '#5f3c23',
        outlineWidth: 3
      }
    }
  }, '*');
```

## iframe国际化

### 语言列表

```json
// 简体中文
zh-CN
// 德语
de-DE
// 法语
fr-FR
// 西班牙语
es-ES
// 俄语
ru-RU
// 阿拉伯语
ar-EG
// 繁体中文
zh-TW
```

### URL方式

```html
<iframe id="mapView" src="http://dev.deeptime-engine.com/map/#/showcase?locale=en-US" />
```

### LocalStorage方式

```typescript
// 切换到英语环境
localStorage.setItem('locale', 'en-US');
// 切换到中文环境
localStorage.setItem('locale', 'zh-CN');
```

## 图层管理接口

### addAtom

添加拥有layerServiceInfo字段的dataAtom

#### 数据格式

```typescript
type AddAtomEvent = {
  type: 'addAtom',
  body: {
    atom: Atom;
    options?: { // 默认都为true
      show?: boolean; // 添加后是否显示
      showMessage?: boolean; // 是否显示添加成功/失败信息
      zoom?: boolean; // 添加完成后是否缩放到地图范围，
                      // 栅格方式加载需设置boundary或viewPort属性，否则缩放到默认范围
      topLayerId?: string; // 添加到某个id图层下方
    };
  }
}

type LayerMethod = 'COG' | 'WMS' | 'WMTS' | 'ARCGIS' | 'TMS' | 'TDT' | 'AMAP' | 'GEOJSON' | 'TDTILES' | 'NC' | 'PBF';
type LayerType = 'VECTOR' | 'TMS' | 'TDTILES' | 'NC' | 'RASTER';

type LayerStandard = 'WMTS' | 'TMS' | 'WMS' | 'COG_TIF' | 'TILES_3D' | 'PIC';
type LayerFormat = "MAPBOX_VECTOR_TILE" | "UTFGRID" | "PNG" | "JPEG" | "GEOJSON" | "TOPOJSON" | "GIF" | "b3dm" | "i3dm" | "pnts" | "cmpt";

type LayerInfo = {
  type: LayerType; // 以后会去掉
  method: LayerMethod; // 以后会去掉
  standard: LayerStandard;
  format: LayerFormat;
  renderOptions?: any;
  url: string;
  sourceLayer: string;
  imageURL?: string;
  srs?: string;
  proLegends?: string[];
  tmsLegend?: {
    type: 'polygon' | 'line' | 'point';
    color: string;
    name: string;
  }[];
  geoJsonType?: 'point' | 'line' | 'polygon';
  // nc专用
  fields?: { // fields默认为 { lon: 'lon', lat: 'lat', U: 'U', V: 'V'}
    lon?: string;
    lat?: string;
    U?: string;
    V?: string;
  }
  valueRange?: { // valueRange默认为{ min: -100, max: 100},即UV纬度值的范围
    min?: number;
    max?: number;
  }
  offset?: { // 经纬度偏移值,默认为{ lon: 0, lat: 0, lev: 0 };
    lon?: number;
    lat?: number;
    lev?: number;
  }
}

type Atom = {
    id: number;
    uid: string;
    name: string;
    dataType: string;
    atomType: 'LAYER_SERVICE' | 'JDBC' | 'HTTP';
    userId: string;
    privilege: string;
    status: string;
    isOfficial: 0 | 1;
    browseGraph: string;
    keyword: string;
    taskId?: string;
    boundaryWKT: string;
    coordinateReference?: string;
    projection?: string;
    space: {
        type?: string;
        resolution: string;
        elevation?: string;
        extent: {
            minX: number;
            maxX: number;
            minY: number;
            maxY: number;
        };
        geoIdentifier?: string;
    };
    temporal: {
      geologicTime: string;
      geologicAge: string;
      base: number;
      top: number;
      gtsVersion: string;
    };
    fields: {
        type: string;
        fieldName: string;
        description: string;
    }[];
    intellectualProp?: string;
    license?: string;
    createTime: number;
    updateTime: number;
    layerServiceInfo: LayerInfo;
  }
```

### addLayer

添加图层，添加图层皆为异步方法，与图层相关的操作请在图层添加完毕之后进行操作

#### 数据格式

```typescript
type AddLayerEvent = {
  type: 'addLayer',
  body: {
    layer: LayerItem;
    options?: { // 默认都为true
      show?: boolean; // 添加后是否显示
      showMessage?: boolean; // 是否显示添加成功/失败信息
      zoom?: boolean; // 添加完成后是否缩放到地图范围，
                      // 栅格方式加载需设置boundary或viewPort属性，否则缩放到默认范围
      topLayerId?: string; // 添加到某个id图层下方
    };
  }
}

type LayerItem = RasterLayerItem | TMSLayerItem | TMSVectorLayerItem | VectorLayerItem | PbfLayerItem | COGLayerItem | NCLayerItem | TDTileLayerItem;

/**
 * 图层元数据基类，单纯的BasicLayer无法上图，缺少加载方式(method)，需使用具体的LayerItem
 */
type BasicLayer = {
  layerName: string;
  id: string; // 对应dataAtom uid
  url: string; // 图层url, geojson加载方式传入geojson
  headers?: Record<string, any>; // 请求头
  queryParameters?: Record<string, any>; // 可以传自定义url参数，如token等
  boundary?: string; // 地图边界，例：
                     // POLYGON((-167.1072 32.0969,-167.1072 69.834,-104.1519 69.834,-104.1519 32.0969,-167.1072 32.0969))
  viewPort?: number[]; // 地图缩放的范围，如果没有viewPort，从boundary中计算
                       // 默认为[110.60396458865515, 34.54408834959379, 15000000]
  sourceLayer?: string; // 真实图层名，wms、cog、pbf等加载方式需要此字段，不填则取layerName，两者可能不一致
  proLegends?: string[]; // 用于存放专业图例的字段，从atom的layerserviceInfo中获取
}
```

#### 几种图层类型

##### 栅格图层

wms/wmts/tms 服务，天地图(tdt)/高德地图(amap)/arcgis 服务，图片(根据boundary添加)

```typescript
/**
 * 栅格图层元数据格式
 */
type RasterLayerItem = {
  method: 'wms' | 'wmts' | 'tms' | 'tdt' | 'amap' | 'arcgis' | 'pic';
  addTgt?: boolean; // 是否在header中添加鉴权rzpj
  legend?: TMSLegend; // TMS图层图例
  loaderinfo?: LoaderInfo;
  renderOptions?: RasterOptions;
} & BasicLayer;

type LoaderInfo = {
  srs?: string; // 'EPSG: 4326' | 'EPSG: 3857'，默认为3857
  minimumLevel?: number,
  maximumLevel?: number,
}

type TMSLegend = {
  type: 'polygon' | 'line' | 'point';
  color: string;
  name: string;
}[];

type RasterOptions = {
  alpha?: number;
  brightness?: number;
  hue?: number;
  saturation?: number;
  gamma?: number;
  contrast?: number;
};

const DeaultRasterOptions = {
  brightness: 1,
  alpha: 1,
  gamma: 1,
  saturation: 1,
  contrast: 1,
  hue: 0,
}
```

pic案例

```json
{
  id: 'pic-1',
  layerName: 'pic-test',
  boundary: "POLYGON((-180 0,0 90,180 0,0 -90,-180 0))",
  url:"https://deepengine.oss-cn-hangzhou.aliyuncs.com/workspace/ADMIN/share/tif/000_v21144.bmp",
  method: 'pic',
}
```

wms案例

```json
{
  id: 'wms-test',
  layerName: 'Geotectonic Map of China',
  url:"https://igss.cgs.gov.cn:6160/igs/rest/ogc/doc/MAPGIS16_20200228_ZSZ1Olqo/WMSServer",
  method: 'wms',
  queryParameters: {
    tk: 'eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiJlZWNmM2Q2Mi03MjJjLTRiNzItYTMyNi01ZWU1MjEyNzAzMjkifQ.q1e0-idNxcszilHs8k1-OJ1MrtL_CvB_Skx_kTRbnP4',
  },
  sourceLayer: 'MAPGIS16_20200228_ZSZ1Olqo',
}
```

##### 栅格图层(COG)

```typescript
/**
 * 以cog方式加载的栅格图层元数据格式
 */
type COGLayerItem = {
  method: 'cog';
  renderOptions?: COGOptions
  minMax?: number[]; // 用于存放cog影像的数值范围
  addTgt?: boolean;
} & BasicLayer;

type COGRenderStyle = 'jet' | 'magma' | 'inferno' | 'plasma' | 'viridis' | 'RdBu_r' | 'Greens' | 'YlOrBr' | 'RdYlBu_r';

type COGOptions = {
  renderMethod?: 'SingleBand' | 'ThreeBand';
  R?: number; // 单波段渲染时取R值
  G?: number;
  B?: number;
  /**
   * 表示渲染的样式名(可选)，默认值根据layerName参数从数据库fuxi_layer_colormap_map表中获取，也可传入系统默认colormap的名称，或用户自定义colormap的id,若无默认渲染样式&用户未传入样式，默认使用jet渲染方式
   */
  renderStyle?: 'jet' | 'magma' | 'inferno' | 'plasma' | 'viridis' | 'RdBu_r' | 'Greens' | 'YlOrBr' | 'RdYlBu_r' | string;
  /**
   * 自定义的当前cog样式，如果不为空，则renderStyle属性失效
   */
  newRender?: {
    colors: [number, string][];
    max: number;
    min: number;
    type: "discrete" | 'continuous';
  }
  /**
   * 渲染值的范围0 - 1
   */
  valueRange?: {
    min: number;
    max: number;
  }
} & RasterOptions;

const DefaultCOGOptions = {
  renderMethod: 'ThreeBand',
  R: 1,
  G: 1,
  B: 1,
  renderStyle: 'jet',
  brightness: 1,
  alpha: 1,
  gamma: 1,
  saturation: 1,
  contrast: 1,
  hue: 0,
}
```

##### 矢量图层(TMS/png)

```typescript
 /**
 * 以tms方式加载的矢量图层元数据格式
 */
type TMSVectorLayerItem = {
  method: 'tms';
  layerType: 'vector';
  renderOptions?: RasterOptions;
  loaderinfo?: LoaderInfo;
} & BasicLayer;
```

案例

```json
{
  layerName: 'tms-test',
  id: 'tms-test',
  url: "https://zjufuxi-public.oss-cn-shanghai.aliyuncs.com/tms/esac/{z}/{x}/{reverseY}.png",
  addTgt: true,
  method: "TMS",
  legend: [{ "name": "Tree cover", "type": "polygon", "color": "006400" }, { "name": "Shrubland", "type": "polygon", "color": "FFBB22" }, { "name": "Grassland", "type": "polygon", "color": "FFFF4C" }, { "name": "Cropland", "type": "polygon", "color": "F096FF" }, { "name": "Built-up", "type": "polygon", "color": "FA0000" }, { "name": "Bare / sparse vegetation", "type": "polygon", "color": "B4B4B4" }, { "name": "Snow and ice", "type": "polygon", "color": "F0F0F0" }, { "name": "Permanent water bodies", "type": "polygon", "color": "0064C8" }, { "name": "Herbaceous wetland", "type": "polygon", "color": "0064A0" }, { "name": "Mangroves", "type": "polygon", "color": "00CF75" }, { "name": "Moss and lichen", "type": "polygon", "color": "FAE6A0" }]
}
```

##### 矢量图层(GeoJson)

```typescript
 /**
 * 以geojosn方式加载的矢量图层元数据格式
 */
type GeoJsonLayerItem = {
  url: string | GeoJSON.GeoJSON; // geojson链接或对象
  method: 'geojson' | 'primitive'; // primitive方式加载时不支持点cluster聚合
  layerType?: 'vector';
} & GeoJsonOptions & Omit<BasicLayer, 'url'>;

/**
 * geojson分类型的渲染配置, 类型较多, 程序内有默认样式
 */
type GeoJsonOptions = {
  geoJsonType?: 'point',
  renderOptions?: GeoJsonCommonStyle & GeoJsonPointStyle
} | {
  geoJsonType?: 'line',
  renderOptions?: GeoJsonCommonStyle & GeoJsonLineStyle
} | {
  geoJsonType?: 'polygon',
  renderOptions?: GeoJsonCommonStyle & GeoJsonPolygonStyle
}

type RGBColor = {
    a?: number | undefined;
    b: number;
    g: number;
    r: number;
}
type GeoJsonCommonStyle = {
  symbol?: SymbolStyle; // 标签
}

type GeoJsonColor = RGBColor | string

/**
 * geojson渲染方案
 */
type GeoJsonStyle = GeoJsonCommonStyle & (GeoJsonPointStyle | GeoJsonLineStyle | GeoJsonPolygonStyle)

/**
 * 标签渲染条件
 */
type SymbolStyle = {
  "text-field"?: string;
  "text-font"?: string;
  "text-size"?: number;
  'text-color'?: GeoJsonColor;
  'text-halo-color'?: GeoJsonColor;
  'text-halo-width'?: number;
}

/**
 * 分段和单值渲染的用户自定义样式
 */
type CustomStyle = {
  /**
   * 自定义区间/值
   */
  label: string | number | [number, number];
  /**
   * css颜色
   */
  value: string;
 }[]


/**
 * 点渲染方案, 共计五种
 */
type GeoJsonPointStyle = (PointSingleStyle | PointSectionStyle | PointValueStyle | PointBubbleStyle) & {
  cluster?: ClusterOptions
} | PointHeightStyle

/**
 * 点通用渲染条件
 */
type PointCommonOptions = {
  custom?: CustomStyle;
  'circle-stroke-color'?: GeoJsonColor | undefined;
  'circle-stroke-width'?: number | undefined;
  opacity?: number;
}

/**
 * 点聚类渲染条件
 */
type ClusterOptions = {
  enable?: boolean
  pixelRange?: number
  minimumClusterSize?: number
}

type PointSingleStyle = {
  type: 'single',
  // 精灵图
  sprite?: {
    url: string;
    params?: Record<string, any>
  }
  config: {
    'label-type'?: 'vector' | 'icon';
    color?: GeoJsonColor;
    'icon-image'?: string;
    'label-size'?: number;
    'icon-size'?: number;
  } & PointCommonOptions
}

type PointSectionStyle = {
  type: 'section',
  config: {
    field?: string;
    'section-type'?: 'natural' | 'average';
    color?: string[];
    'label-size'?: number;
  } & PointCommonOptions
}

type PointValueStyle = {
  type: 'value',
  config: {
    field?: string;
    color?: string[];
    'label-size'?: number;
  } & PointCommonOptions
}

type PointBubbleStyle = {
  type: 'bubble',
  config: {
    field?: string;
    'section-type': 'natural' | 'average';
    'section-num': number;
    'label-size': number[];
    'fill-type': 'single' | 'multi';
    color?: GeoJsonColor;
    colors?: string[];
  } & PointCommonOptions
}

type PointHeightStyle = {
  type: 'height',
  config: {
    field?: string;
    'section-type'?: 'natural' | 'average';
    color?: string[];
    'radius-size'?: number;
    'height-range': [number, number];
  } & PointCommonOptions
}

/**
 * 线渲染方案, 共计三种
 */
type GeoJsonLineStyle = (LineSingleStyle | LineSectionStyle | LineValueStyle)

/**
 * 线通用渲染条件
 */
type LineCommonOptions = {
  custom?: CustomStyle;
  'line-width'?: number;
  opacity?: number;
}

type LineSingleStyle = {
  type: 'single',
  config: {
    color?: GeoJsonColor;
  } & LineCommonOptions
}

type LineSectionStyle = {
  type: 'section',
  config: {
    field?: string;
    'section-type'?: 'natural' | 'average';
    color?: string[];
  } & LineCommonOptions
}

type LineValueStyle = {
  type: 'value',
  config: {
    field?: string;
    color?: string[];
  } & LineCommonOptions
}

/**
 * 面渲染方案, 共计三种
 */
type GeoJsonPolygonStyle = (PolygonSingleStyle | PolygonSectionStyle | PolygonValueStyle | PolygonHeightStyle)

/**
 * 面通用渲染条件
 */
type PolygonCommonOptions = {
  custom?: CustomStyle;
  opacity?: number;
  'outline-color'?: GeoJsonColor;
  'outline-width'?: number;
}

type PolygonSingleStyle = {
  type: 'single',
  config: {
    color?: GeoJsonColor;
  } & PolygonCommonOptions
}

type PolygonSectionStyle = {
  type: 'section',
  config: {
    field?: string;
    'section-type'?: 'natural' | 'average';
    color?: string[];
  } & PolygonCommonOptions
}

type PolygonValueStyle = {
  type: 'value',
  config: {
    field?: string;
    color?: string[];
  } & PolygonCommonOptions
}

type PolygonHeightStyle = {
  type: 'height',
  config: {
    field?: string;
    'section-type'?: 'natural' | 'average';
    color?: string[]
    'height-range': [number, number];
  } & PolygonCommonOptions
}

```

点geojson

```json
{
  id: 'geojson-point',
  layerName: 'holes',
  url:"http://121.196.210.228/static/holes.json",
  method: 'geojson',
  renderOptions: {
    'label-type': 'vector',
    'color': {r: 0, g: 255, b: 255, a: 1},
    'label-size': 5,
    'icon-size': 1,
    'circle-stroke-color': {r: 255, g: 255, b: 255, a: 1},
    'circle-stroke-width': 1,
    opacity: 1,
  }
}
```

面geojson

```json
{
  layerName: 'primitive-polygon-heat',
  id: 'primitive-polygon-heat',
  url: 'https://resource.deep-time.org/resource/testdem/California_heat.geojson',
  method: 'primitive',
  renderOptions: {
    'color': { r: 0, g: 255, b: 255, a: 1 },
    'outline-color': { r: 255, g: 255, b: 255, a: 0.8 },
    'outline-width': 2,
    opacity: 1
  }
}
```

##### 栅格图层(GeoJson/heatmap)

通过点geojson创建热力图

```typescript
/**
 * 热力图图层元数据格式
 */
type HeatLayerItem = {
  url: string | GeoJSON.GeoJSON; // 点geojson链接或对象
  method: 'heat';
  renderOptions?: HeatOptions;
} & Omit<BasicLayer, 'url'>;

type HeatOptions = {
  field?: string
  config?: {
    /**
      * The blur factor that will be applied to all datapoints. The higher the
      * blur factor is, the smoother the gradients will be
      * Default value: 0.85
      */
    blur?: number | undefined;

    /**
      * An object that represents the gradient.
      * Syntax: {[key: number in range [0,1]]: color}
      */
    gradient?: string[];

    /**
      * The maximal opacity the highest value in the heatmap will have. (will be
      * overridden if opacity set)
      * Default value: 0.6
      */
    maxOpacity?: number | undefined;

    /**
      * The minimum opacity the lowest value in the heatmap will have (will be
      * overridden if opacity set)
      */
    minOpacity?: number | undefined;

    /**
      * A global opacity for the whole heatmap. This overrides maxOpacity and
      * minOpacity if set
      * Default value: 0.6
      */
    opacity?: number | undefined;

    /**
      * The radius each datapoint will have (if not specified on the datapoint
      * itself)
      */
    radius?: number | undefined;
  },
  autoRadius?: boolean
}
```

案例

```json
{
  id: 'heatmap',
  layerName: 'earthquakes-heat',
  url:"https://docs.mapbox.com/mapbox-gl-js/assets/earthquakes.geojson",
  method: 'heat',
  renderOptions: {
    blur: 0.85,
    maxOpacity: 0.8,
    minOpacity: 0,
    opacity: 0.8,
    radius: 10,
    gradient: [
      '#313695',
      '#4575b4',
      '#74add1',
      '#abd9e9',
      '#e0f3f8',
      '#ffffbf',
      '#fee090',
      '#fdae61',
      '#f46d43',
      '#d73027',
      '#a50026'
    ],
  }
}
```

##### 栅格图层(GeoJson/mapv)

通过geojson创建mapv图层

```typescript
type MapVLayerItem = {
  url: string | GeoJSON.GeoJSON; // 点geojson链接或对象
  method: 'mapv';
  renderOptions?: MapVOptions;
} & Omit<BasicLayer, 'url'>;
/** MapV配置 */

type MapVOptions = MapVCommonOptions & (MapVBubbleOptions | MapVCategoryOptions | MapVChoroplethOptions | MapVClusterOptions | MapVGridOptions | MapVHeatmapOptions | MapVHoneycombOptions | MapVIntensityOptions | MapVSimpleOptions | MapVTextOptions | MapVIconOptions)

type MapVCommonOptions = {
  /** 层级 */
  zIndex?: number;
  /** 大小值 */
  size?: number;
  /** 'px': 以像素为单位绘制,默认值。'm': 以米制为单位绘制，会跟随地图比例放大缩小 */
  unit?: 'px' | 'm';
  /** 不同图层之间的叠加模式，参考[https://developer.mozilla.org/en-US/docs/Web/CSS/mix-blend-mode](https://developer.mozilla.org/en-US/docs/Web/CSS/mix-blend-mode) */
  mixBlendMode?: string;
  /** 填充颜色 */
  fillStyle?: string;
  /** 描边颜色 */
  strokeStyle?: string;
  /** 描边宽度 */
  lineWidth?: number;
  /** 透明度 */
  globalAlpha?: number;
  /** 颜色叠加方式, 默认'source-over' */
  globalCompositeOperation?: 'lighter' | 'source-over';
  /** 可选百度墨卡托坐标类型bd09mc和百度经纬度坐标类型bd09ll(默认) */
  coordType?: 'bd09mc' | 'bd09ll';
  /** 投影颜色 */
  shadowColor?: string;
  /** 投影模糊级数 */
  shadowBlur?: number;
  /** 重绘回调函数，如果是时间动画、返回当前帧的时间 */
  updateCallback?: (time?: number) => void;
  shadowOffsetX?: number;
  shadowOffsetY?: number;
  /** 可选2d和webgl，webgl目前只支持画simple模式的点和线 */
  context?: '2d' | 'webgl';
  lineCap?: 'butt';
  lineJoin?: 'miter';
  miterLimit?: number;
  /** 一些事件回调函数 */
  methods?: {
    /** 点击事件，返回对应点击元素的对象值 */
    click?: (item?: any) => void;
    /**  鼠标移动事件，对应鼠标经过的元素对象值 */
    mousemove?: (item?: any) => void;
    /** 只针对移动端,点击事件 */
    tap?: (item?: any) => void;
  };
  animation?: {
    /** 按时间展示动画 */
    type: 'time';
    /** 动画时间范围,time字段中值 */
    stepsRange?: {
      start?: number;
      end?: number;
    };
    /** 时间动画的拖尾大小 */
    trails?: number;
    /** 单个动画的时间，单位秒 */
    duration?: number;
  };
}

type GradientColor = Record<number, string>

type MapVLabelOptions = {
  show: boolean;
  fillStyle?: string;
  shadowColor?: string;
  font?: string;
  shadowBlur?: number;
}

/** 普通绘制方式 */
type MapVSimpleOptions = {
  draw: 'simple';
}

/** 蜂窝状聚类图配置 */
type MapVHoneycombOptions = {
  draw: 'honeycomb';
  size?: number;
  /** 网格中显示累加的值总和 */
  label?: MapVLabelOptions
  gradient?: GradientColor
}

/** 聚类图配置 */
type MapVClusterOptions = {
  draw: 'cluster';
  label?: MapVLabelOptions;
}

/** 气泡图配置 */
type MapVBubbleOptions = {
  draw: 'bubble';
  /** 显示的圆最大半径大小 */
  maxsize?: number;
  /** 数值最大值范围 */
  max?: number;
}

/** 热力图配置 */
type MapVHeatmapOptions = {
  draw: 'heatmap';
  /** 每个热力点半径大小 */
  size?: number;
  /** 热力图渐变色 */
  gradient?: GradientColor;
  /** 最大权重值 */
  max?: number;
}

/** 网格聚类图配置 */
type MapVGridOptions = {
  draw: 'grid';
  size?: number;
  gradient?: GradientColor;
  /** 网格中显示累加的值总和 */
  label?: MapVLabelOptions
}

/** 颜色渐变图配置 */
type MapVIntensityOptions = {
  draw: 'intensity';
  /** 最小阈值 */
  min?: number;
  /** 最大阈值 */
  max?: number;
  gradient?: GradientColor;
}

/** 颜色分类图配置 */
type MapVCategoryOptions = {
  draw: 'category';
  splitList?: {
    other: string;
    [key: string | number]: string;
  }
}

/** 值区间分类图配置 */
type MapVChoroplethOptions = {
  draw: 'choropleth';
  /** 按数值区间来展示不同颜色的点 */
  splitList?: {
    start: number;
    end: number;
    color: string;
  }[]
}

/** 文本配置 */
type MapVTextOptions = {
  draw: 'text';
  fillStyle?: string;
  textAlign?: 'center';
  /** 开启文本标注避让 */
  avoid?: boolean;
  textBaseline?: 'middle';
  /** 文本偏移值 */
  offset?: {
      x?: number;
      y?: number;
  };
}

type MapVIconOptions = {
  draw: 'icon';
  /** 图片旋转角度 */
  rotate?: string;
  /** 规定图像的宽度 */
  width?: number;
  /** 规定图像的高度 */
  height?: number;
  /** 添加点击事件时候可以用来设置点击范围 */
  size?: number;
  /** 开始剪切的 x 坐标位置 */
  sx?: number;
  /** 开始剪切的 y 坐标位置 */
  sy?: number;
  /** 被剪切图像的宽度 */
  swidth?: number;
  /** 被剪切图像的高度 */
  sheight?: number;
}
```

案例

```json
{
  id: 'honeycomb',
  layerName: 'earthquakes-honeycomb',
  url:"https://docs.mapbox.com/mapbox-gl-js/assets/earthquakes.geojson",
  method: 'mapv',
  renderOptions: {
    draw: 'honeycomb',
    shadowColor: 'black',
    shadowBlur: 10,
    size: 50,
    gradient: [
      '#313695',
      '#4575b4',
      '#74add1',
      '#abd9e9',
      '#e0f3f8',
      '#ffffbf',
      '#fee090',
      '#fdae61',
      '#f46d43',
      '#d73027',
      '#a50026'
    ],
    globalAlpha: 0.8,
    label: {
      show: true,
      fillStyle: 'white',
    }
  }
}
```

##### 矢量图层(TMS/pbf)

```typescript
 /**
 * 以pbf方式加载的矢量图层元数据格式
 */
type PbfLayerItem = {
  url: string | Object; // 支持传入mapbox样式地址.json、mapbox样式对象、pbf瓦片地址
                        // geojson类型支持传入geojson地址、geojson对象
  method: 'pbf';
  originMethod?: 'pbf' | 'geojson'; // url类型，如果是geojson则必填
  geoJsonType?: 'point' | 'line' | 'polygon';
  renderOptions?: PbfOptions;
  columns?: {
    column_name: string;
    data_type: "string" | "number";
  }[]; // 列字段信息
} & Omit<BasicLayer, 'url'>;

type PbfOptions = {
  type?: 'single' | 'section' | 'value' | 'bubble'; // 单色、分段、单值、气泡
  config?: Record<string, any>; // 渲染配置, 不同geoJsonType和不同渲染模式需求的字段不同
                                // 共计10种方案，类似geojson渲染方案, 不详述
  symbol?: { // 标签设置
    "text-field"?: string;
    "text-size"?: number;
    'text-color'?: string;
    'text-anchor'?: string;
  };
} & RasterOptions;
```

案例

```json
{
  layerName: 'pbf',
  id: 'pbf',
  method: 'pbf',
  url: 'https://vstyles.mapplus.cn/v1.0/styles/bj_500_dz/style.json',
  viewPort: [116.3, 39.9, 1000000]
}
```

##### NC图层

```typescript
/**
 * nc图层元数据格式
 */
type NCLayerItem = {
  method: 'nc';
  renderOptions?: NCOptions;
  fields?: { // fields默认为 { lon: 'lon', lat: 'lat', U: 'U', V: 'V'}
    lon?: string;
    lat?: string;
    U?: string;
    V?: string;
  }
  valueRange?: { // valueRange默认为{ min: -100, max: 100},即UV纬度值的范围
    min?: number;
    max?: number;
  }
  offset?: { // 经纬度偏移值,默认为{ lon: 0, lat: 0, lev: 0 };
    lon?: number;
    lat?: number;
    lev?: number;
  }
} & BasicLayer;

type NCOptions = {
  colorBar?: string[];
  maxParticles?: number;
  particleHeight?: number;
  fadeOpacity?: number;
  dropRate?: number;
  dropRateBump?: number;
  speedFactor?: number;
  lineWidth?: number;
  dynamic?: boolean;
  valueRange?: {
    min: number;
    max: number;
  }
};

const DefaultNCOptions = {
  maxParticles: 64 * 64,
  particleHeight: 1000.0,
  fadeOpacity: 0.950,
  dropRate: 0.003,
  dropRateBump: 0.01,
  speedFactor: 0.5,
  lineWidth: 4.0,
  dynamic: true
}
```

##### 3DTiles图层

```typescript
/**
 * 3dtiles图层元数据格式
 */
type TDTileLayerItem = {
  method: 'tdtiles';
  renderOptions?: TDTileOptions
} & BasicLayer;

type TDTileOptions = {
  defaultColor: string;
  conditions?: {
    height: number;
    color: string;
  }[];
  showHeight?: number;
};

const DefaultTDTileOptions = {
  defaultColor: 'rgba(0, 247, 255, 1)',
  showHeight: 0,
}
```

##### KML图层

```typescript
/**
 * kml图层元数据格式
 */
type KMLLayerItem = {
  method: 'kml';
  layerType?: 'kml';
  renderOptions?: KMLOptions;
} & BasicLayer;

type KMLOptions = {
  labelColor?: string[];
}
```

#### 示例

```javascript
// 添加一个栅格图层(tms)
{
  type: 'addLayer',
  body: {
    {
      layer: {
        layerName: "1:500",
        url: "http://202.107.245.52:5160/v1.0/yanjiangyan?z={z}&x={x}&y={y}",
        method: "tms",
        id: "2ff6ae2d-aa3a-4255-ab0b-b33aae289300",
      }
    }
  }
}
```

### removeLayer

根据图层id移除图层

#### 数据格式

```typescript
type RemoveLayerEvent = {
  type: 'removeLayer',
  body: {
    id: string;
    options?: { // 默认都为true
      showMessage?: boolean; // 是否显示移除成功/失败信息
    };
  }
}
```

#### 示例

```javascript
{
  type: 'removeLayer',
  body: {
    id: '2ff6ae2d-aa3a-4255-ab0b-b33aae289300'
  }
}
```

### moveLayerById

根据id移动图层，将原图层移动到目标图层所在的位置

#### 数据格式

```typescript
type MoveLayerByIdEvent = {
  type: 'moveLayerById',
  body: {
    sourceId: string;
    targetId: string;
  }
}
```

#### 示例

```javascript
{
  type: 'moveLayerById',
  body: {
    sourceId: '123',
    targetId: '234',
  }
}
```

## 数据集管理接口

### addDataSet

添加数据集

#### 数据格式

```typescript
type AddDataSetEvent = {
  type: 'addDataSet',
  body: {
    name: string;
    id: string;
  }
}
```

#### 示例

```javascript
{
  type: 'addDataSet',
  body: {
    name: 'testDataSet',
    id: '12345'
  }
}
```

### removeDataSet

根据id移除数据集

#### 数据格式

```typescript
type RemoveDataSetEvent = {
  type: 'removeDataSet',
  body: {
    id: string;
  }
}
```

#### 示例

```javascript
{
  type: 'removeDataSet',
  body: {
    id: '12345'
  }
}
```

## 图元管理接口

### addPoints

#### 数据格式

添加多个点

```typescript
type AddPointsEvent = {
  type: 'addPoints',
  body: {
    id: string; // 如果重复,会被覆盖
    positions: number[][]; // 经纬度
    style?: {
      color?: string; // 点颜色
      pixelSize?: number; // 点大小
      outlineColor?: string;
      outlineWidth?: number
    }
    properties?: Record<string, any> // 属性
  }
}

// 默认的style样式
const DefaultPointsStyle = {
  color: '#f47920',
  pixelSize: 3
}
```

#### 示例

```javascript
{
  type: 'addPoints',
  body: {
    id: 'test',
    positions: [[120, 30], [100, 40]],
    style: {
      color: 'red'
    },
    properties: {
      'key': 'value'
    }
  }
}
```

### removePoints

移除对应id的多点图层

#### 数据格式

```typescript
type RemovePointsEvent = {
  type: 'removePoints',
  body: {
    id: string;
  }
}
```

#### 示例

```javascript
{
  type: 'removePoints',
  body: {
    id: 'test',
  }
}
```

## 地图设置接口

### componentConfig

控制图层管理、图例组件的显示隐藏

#### 数据格式

```typescript
type ComponentConfigEvent = {
  type: 'componentConfig',
  body: {
    layerManage?: {
      datasetManage?: {
        disableRemove?: boolean;
        hideLayerPlayer?: boolean;
      }
    };
    showLegend?: boolean;
  }
}

// 默认配置
const DefaultComponentConfig = {
  layerManage: {
    datasetManage: {
      disableRemove: true,
      hideLayerPlayer: true
    }
  },
  showLegend: true
}
```

#### 示例

```javascript
// 隐藏图层管理、图例
{
  type: 'componentConfig'
  body: {}
}

// 隐藏图层管理，显示图例
{
  type: 'componentConfig'
  body: {
  	showLegend: true,
  }
} 
{
  showLegend: true,
}

// 显示图层管理，但隐藏数据集管理
{
  type: 'componentConfig'
  body: {
    layerManage: {}
  }
}
```

### mapConfig

地图设置，包括导航经纬度控件显示隐藏、地图二三维切换、底图注记地形更改等

#### 数据格式

```typescript
type MapConfigEvent = {
  type: 'mapConfig',
  body: {
    navigator?: boolean; // 是否显示导航控件
    mapStatusBar?: boolean; // 是否显示右下地图信息条
    viewerModeSwitch?: boolean; // 是否显示二三维切换按钮
    measureTool?: boolean; // 是否显示量算按钮
    cameraController?: boolean; // 是否显示摄像机控制按钮
    displayMode?: 1 | 2 | 3; // 2为二维, 3为三维, 1为2.5D
    skyAtmosphere?: boolean; // 是否显示大气
    fogDensity?: number; // 水汽含量
    baseMap?: LayerItem; // 底图
    annotationMap?: LayerItem; // 注记
    terrain?: TerrainLayer; // 地形
    ajaxBar?: boolean; // 是否显示地图请求进度条
    performance?: number; // 显示效果,与性能有关,数值0-1,越大越精细
    terrainExaggeration?: number; // 地形拉伸系数
    graticules?: boolean; // 是否显示经纬网
    antiAliasing?: boolean; // 是否开启FXAA抗锯齿
  }
}

type TerrainLayer = {
  layerName: string;
  id: string;
  url?: string | null; // null时为Cesium在线地形，无此字段则不加载地形
  headers?: Record<string, any>; // 请求头
  queryParameters?: Record<string, any>; // 可以传自定义url参数，如token等
  imageURL?: string;
  options?: {
    requestWaterMask?: boolean; // 水面效果
    requestVertexNormals?: boolean; // Needed to visualize slope
  };
};

// 默认地图配置
const DefaultMapConfig = {
  navigator: true,
  displayMode: 1,
  skyAtmosphere: true,
  fogDensity: 0.0001,
  baseMap: {
    layerName: '高德影像底图',
    id: '底图-高德影像底图',
    method: 'amap',
    url: 'http://webst02.is.autonavi.com/appmaptile?style=6&x={x}&y={y}&z={z}',
    imageURL: 'http://lbs.tianditu.gov.cn/images/img_c.png',
  },
  annotationMap: {
    layerName: '高德注记',
    id: '注记-高德注记',
    method: 'amap',
    url: 'http://webst02.is.autonavi.com/appmaptile?style=8&x={x}&y={y}&z={z}',
    imageURL: 'http://lbs.tianditu.gov.cn/images/cva_c.png',
  },
  terrain: {
    layerName: '不加载地形',
    id: '地形-不加载地形',
    imageURL:
      'https://sandcastle.cesium.com/CesiumUnminified/Widgets/Images/TerrainProviders/Ellipsoid.png',
  },
  mapStatusBar: true,
  viewerModeSwitch: true,
  measureTool: true,
  cameraController: true,
  ajaxBar: true,
  performance: 1.0,
  terrainExaggeration: 1.0,
  graticules: false,
  antiAliasing: false	
};
```

#### 示例

```javascript
// 切换为2维地图
{
  type: 'mapConfig',
  body: {
    displayMode: 2,
  }
}

// 更改底图为ESRI全球底图
{
  type: 'mapConfig',
  body: {
    baseMap: {
      layerName: 'ESRI全球底图',
      id: '底图-ESRI全球底图',
      method: 'arcgis',
      url: 'http://services.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer',
      imageURL:
        'https://sandcastle.cesium.com/CesiumUnminified/Widgets/Images/ImageryProviders/esriWorldImagery.png',
    }
  }
}

// 更改地形为Cesium在线地形
{
  type: 'mapConfig',
  body: {
    terrain: {
      layerName: 'Cesium在线地形',
      id: '地形-Cesium在线地形',
      url: null,
      options: {
        requestWaterMask: false,
      },
      imageURL:
        'https://sandcastle.cesium.com/CesiumUnminified/Widgets/Images/TerrainProviders/CesiumWorldTerrain.png',
    }
  }
}

```

### cartography

进入/退出制图模式

#### 数据格式

```typescript
type CartographyEvent = {
  type: 'cartography',
  body: {
    show: boolean;
  }
}
```

#### 示例

```javascript
// 进入制图模式
{
  type: 'cartography',
  body: {
    show: true,
  }
}
```

### openTool

打开工具，面板自带退出工具按钮

#### 数据格式

```typescript
type OpenToolEvent = {
  type: 'openTool',
  body: {
    tool: 'geoReconstruct' | 'layerSplit' | 'layerVideo' | 'project'
    show?: boolean; // 默认为true,打开工具
    style?: { // 工具面板的定位, 默认定位到左上角
      right?: number;
      left?: number;
      top?: number;
      bottom?: number;
    };
    bounds?: { // 工具面板拖拽限制
      right?: number;
      left?: number;
      top?: number;
      bottom?: number;
    };
  }
}
```

#### 示例

```javascript
// 打开古地理重建工具
{
  type: 'openTool',
  body: {
    tool: 'geoReconstruct',
  }
}

// 打开古地理重建工具, 并定位到右上角, 且限制拖拽区域
{
  type: 'openTool',
  body: {
    tool: 'geoReconstruct',
    style: {
      right: 10,
      top: 10
    },
    bounds: {
      right: -10,
      top: -10
    }
  }
}

// 打开项目工具
{
  type: 'openTool',
  body: {
    tool: 'project',
  }
}
// 项目保存时监听保存成功时返回的项目id
// 接收iframe发来的信息
window.addEventListener('message', function(e) {
  const { type, body } = e.data;
  switch (type) {
    case 'openTool':
      // 输出创建成功的项目id
      console.log(body.id);
      break;
  }
});
```

### renderLayer

渲染一个已经加载的图层

#### 数据格式

```typescript
type RenderLayerEvent = {
  type: 'renderLayer',
  body: {
    id: string;
    options: RenderOptions; // 图层的渲染配置，详情见addLayer接口中每个图层的renderOption
    forceMethod?: LayerMethod; // 强制以某种方式进行渲染
  }
}
```

#### 示例

```typescript
// 调整栅格图层透明度
{
	type: 'openTool',
	body: {
		id: '1234',
		options: {
			alpha: 0.5;
		}
	}
}
```

### spatialQuery

开启或关闭某个矢量图层的空间查询功能

#### 数据格式

```typescript
type SpatialQueryEvent = {
  type: 'spatialQuery',
  body: {
    id: string; // 矢量图层的id, 每次只能开启一个图层的查询，填写''即为关闭空间查询
  }
}
```

#### 示例

```typescript
// 开启矢量图层的空间查询
{
	type: 'spatialQuery',
	body: {
		id: '1234'
	}
}
```

### cogQuery

开启或关闭某个COG图层的点击查询功能，可同时开启多个

#### 数据格式

```typescript
type CogQueryEvent = {
  type: 'cogQuery',
  body: {
    id: string; // cog图层的id
    enable: boolean; // 是否开启查询
  }
}
```

#### 示例

```typescript
// 开启COG图层的空间查询
{
	type: 'cogQuery',
	body: {
		id: '1234',
		enable: true
	}
}
```

