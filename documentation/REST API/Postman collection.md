Postman collection JSON
=======================


Copy the JSON below to add the OpenAQ openapi definition to [Postman](https://www.postman.com/)


JSON
```
{
    "openapi": "3.1.0",
    "info": {
        "title": "OpenAQ",
        "description": "OpenAQ API - https://docs.openaq.org",
        "version": "2.0.0"
    },
    "servers": [
        {
            "url": "https://api.openaq.org"
        }
    ],
    "paths": {
        "/v2/averages": {
            "get": {
                "tags": [
                    "v2"
                ],
                "summary": "Get averaged values",
                "operationId": "averages_v2_get_v2_averages_get",
                "parameters": [
                    {
                        "required": false,
                        "schema": {
                            "title": "Date From",
                            "anyOf": [
                                {
                                    "type": "string",
                                    "format": "date-time"
                                },
                                {
                                    "type": "string",
                                    "format": "date"
                                }
                            ],
                            "default": "2000-01-01T00:00:00+00:00"
                        },
                        "name": "date_from",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Date To",
                            "anyOf": [
                                {
                                    "type": "string",
                                    "format": "date-time"
                                },
                                {
                                    "type": "string",
                                    "format": "date"
                                }
                            ],
                            "default": "2022-06-16T22:51:00+00:00"
                        },
                        "name": "date_to",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements",
                        "required": false,
                        "schema": {
                            "title": "Parameter Id",
                            "type": "integer",
                            "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements"
                        },
                        "name": "parameter_id",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10",
                        "required": false,
                        "schema": {
                            "title": "Parameter",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "maximum": 2147483647.0,
                                        "exclusiveMinimum": true,
                                        "minimum": 0.0,
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            },
                            "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10"
                        },
                        "name": "parameter",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Unit",
                            "type": "array",
                            "items": {
                                "type": "string"
                            }
                        },
                        "name": "unit",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Project Id",
                            "type": "integer"
                        },
                        "name": "project_id",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Project",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "maximum": 2147483647.0,
                                        "exclusiveMinimum": true,
                                        "minimum": 0.0,
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            }
                        },
                        "name": "project",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. /US)",
                        "required": false,
                        "schema": {
                            "title": "Country Id",
                            "maxLength": 2,
                            "minLength": 2,
                            "pattern": "[a-zA-Z][a-zA-Z]",
                            "type": "string",
                            "description": "Limit results by a certain country using two letter country code. (e.g. /US)"
                        },
                        "name": "country_id",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)",
                        "required": false,
                        "schema": {
                            "title": "Country",
                            "type": "array",
                            "items": {
                                "maxLength": 2,
                                "minLength": 2,
                                "pattern": "[a-zA-Z][a-zA-Z]",
                                "type": "string"
                            },
                            "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)"
                        },
                        "name": "country",
                        "in": "query"
                    },
                    {
                        "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                        "required": false,
                        "schema": {
                            "title": "Limit",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                            "default": 100
                        },
                        "name": "limit",
                        "in": "query"
                    },
                    {
                        "description": "Paginate through results. e.g. page=1 will return first page of results",
                        "required": false,
                        "schema": {
                            "title": "Page",
                            "maximum": 6000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Paginate through results. e.g. page=1 will return first page of results",
                            "default": 1
                        },
                        "name": "page",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Offset",
                            "maximum": 10000.0,
                            "minimum": 0.0,
                            "type": "integer",
                            "default": 0
                        },
                        "name": "offset",
                        "in": "query"
                    },
                    {
                        "description": "Define sort order.",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/Sort"
                                }
                            ],
                            "description": "Define sort order.",
                            "default": "desc"
                        },
                        "name": "sort",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "$ref": "#/components/schemas/Spatial"
                        },
                        "name": "spatial",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "$ref": "#/components/schemas/Temporal"
                        },
                        "name": "temporal",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Location",
                            "type": "array",
                            "items": {
                                "type": "string"
                            }
                        },
                        "name": "location",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Group",
                            "type": "boolean",
                            "default": false
                        },
                        "name": "group",
                        "in": "query"
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/AveragesResponse"
                                }
                            }
                        }
                    },
                    "422": {
                        "description": "Validation Error",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/HTTPValidationError"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v2/cities": {
            "get": {
                "tags": [
                    "v2"
                ],
                "summary": "Get cities",
                "description": "Provides a list of cities supported by the platform",
                "operationId": "cities_get_v2_cities_get",
                "parameters": [
                    {
                        "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                        "required": false,
                        "schema": {
                            "title": "Limit",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                            "default": 100
                        },
                        "name": "limit",
                        "in": "query"
                    },
                    {
                        "description": "Paginate through results. e.g. page=1 will return first page of results",
                        "required": false,
                        "schema": {
                            "title": "Page",
                            "maximum": 6000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Paginate through results. e.g. page=1 will return first page of results",
                            "default": 1
                        },
                        "name": "page",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Offset",
                            "maximum": 10000.0,
                            "minimum": 0.0,
                            "type": "integer",
                            "default": 0
                        },
                        "name": "offset",
                        "in": "query"
                    },
                    {
                        "description": "Define sort order.",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/Sort"
                                }
                            ],
                            "description": "Define sort order.",
                            "default": "asc"
                        },
                        "name": "sort",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. /US)",
                        "required": false,
                        "schema": {
                            "title": "Country Id",
                            "maxLength": 2,
                            "minLength": 2,
                            "pattern": "[a-zA-Z][a-zA-Z]",
                            "type": "string",
                            "description": "Limit results by a certain country using two letter country code. (e.g. /US)"
                        },
                        "name": "country_id",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)",
                        "required": false,
                        "schema": {
                            "title": "Country",
                            "type": "array",
                            "items": {
                                "maxLength": 2,
                                "minLength": 2,
                                "pattern": "[a-zA-Z][a-zA-Z]",
                                "type": "string"
                            },
                            "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)"
                        },
                        "name": "country",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain city or cities. (e.g. ?city=Chicago or ?city=Chicago&city=Boston)",
                        "required": false,
                        "schema": {
                            "title": "City",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Limit results by a certain city or cities. (e.g. ?city=Chicago or ?city=Chicago&city=Boston)"
                        },
                        "name": "city",
                        "in": "query"
                    },
                    {
                        "description": "Order by a field",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/CitiesOrder"
                                }
                            ],
                            "description": "Order by a field",
                            "default": "city"
                        },
                        "name": "order_by",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Entity",
                            "type": "string"
                        },
                        "name": "entity",
                        "in": "query"
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/CitiesResponse"
                                }
                            }
                        }
                    },
                    "422": {
                        "description": "Validation Error",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/HTTPValidationError"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v1/cities": {
            "get": {
                "tags": [
                    "v1"
                ],
                "summary": "Get cities",
                "description": "Provides a list of cities supported by the platform",
                "operationId": "cities_getv1_v1_cities_get",
                "parameters": [
                    {
                        "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                        "required": false,
                        "schema": {
                            "title": "Limit",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                            "default": 100
                        },
                        "name": "limit",
                        "in": "query"
                    },
                    {
                        "description": "Paginate through results. e.g. page=1 will return first page of results",
                        "required": false,
                        "schema": {
                            "title": "Page",
                            "maximum": 6000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Paginate through results. e.g. page=1 will return first page of results",
                            "default": 1
                        },
                        "name": "page",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Offset",
                            "maximum": 10000.0,
                            "minimum": 0.0,
                            "type": "integer",
                            "default": 0
                        },
                        "name": "offset",
                        "in": "query"
                    },
                    {
                        "description": "Define sort order.",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/Sort"
                                }
                            ],
                            "description": "Define sort order.",
                            "default": "asc"
                        },
                        "name": "sort",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. /US)",
                        "required": false,
                        "schema": {
                            "title": "Country Id",
                            "maxLength": 2,
                            "minLength": 2,
                            "pattern": "[a-zA-Z][a-zA-Z]",
                            "type": "string",
                            "description": "Limit results by a certain country using two letter country code. (e.g. /US)"
                        },
                        "name": "country_id",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)",
                        "required": false,
                        "schema": {
                            "title": "Country",
                            "type": "array",
                            "items": {
                                "maxLength": 2,
                                "minLength": 2,
                                "pattern": "[a-zA-Z][a-zA-Z]",
                                "type": "string"
                            },
                            "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)"
                        },
                        "name": "country",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain city or cities. (e.g. ?city=Chicago or ?city=Chicago&city=Boston)",
                        "required": false,
                        "schema": {
                            "title": "City",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Limit results by a certain city or cities. (e.g. ?city=Chicago or ?city=Chicago&city=Boston)"
                        },
                        "name": "city",
                        "in": "query"
                    },
                    {
                        "description": "Order by a field",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/CitiesOrder"
                                }
                            ],
                            "description": "Order by a field",
                            "default": "city"
                        },
                        "name": "order_by",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Entity",
                            "type": "string"
                        },
                        "name": "entity",
                        "in": "query"
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/CitiesResponse"
                                }
                            }
                        }
                    },
                    "422": {
                        "description": "Validation Error",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/HTTPValidationError"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v2/countries": {
            "get": {
                "tags": [
                    "v2"
                ],
                "summary": "Get countries",
                "description": "Providecs a list of countries",
                "operationId": "countries_get_v2_countries_get",
                "parameters": [
                    {
                        "required": false,
                        "schema": {
                            "title": "Limit",
                            "type": "integer",
                            "default": 200
                        },
                        "name": "limit",
                        "in": "query"
                    },
                    {
                        "description": "Paginate through results. e.g. page=1 will return first page of results",
                        "required": false,
                        "schema": {
                            "title": "Page",
                            "maximum": 6000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Paginate through results. e.g. page=1 will return first page of results",
                            "default": 1
                        },
                        "name": "page",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Offset",
                            "maximum": 10000.0,
                            "minimum": 0.0,
                            "type": "integer",
                            "default": 0
                        },
                        "name": "offset",
                        "in": "query"
                    },
                    {
                        "description": "Define sort order.",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/Sort"
                                }
                            ],
                            "description": "Define sort order.",
                            "default": "asc"
                        },
                        "name": "sort",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. /US)",
                        "required": false,
                        "schema": {
                            "title": "Country Id",
                            "maxLength": 2,
                            "minLength": 2,
                            "pattern": "[a-zA-Z][a-zA-Z]",
                            "type": "string",
                            "description": "Limit results by a certain country using two letter country code. (e.g. /US)"
                        },
                        "name": "country_id",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)",
                        "required": false,
                        "schema": {
                            "title": "Country",
                            "type": "array",
                            "items": {
                                "maxLength": 2,
                                "minLength": 2,
                                "pattern": "[a-zA-Z][a-zA-Z]",
                                "type": "string"
                            },
                            "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)"
                        },
                        "name": "country",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/CountriesOrder"
                                }
                            ],
                            "default": "country"
                        },
                        "name": "order_by",
                        "in": "query"
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/CountriesResponse"
                                }
                            }
                        }
                    },
                    "422": {
                        "description": "Validation Error",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/HTTPValidationError"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v2/countries/{country_id}": {
            "get": {
                "tags": [
                    "v2"
                ],
                "summary": "Get country by ID",
                "description": "Provides a single country by country ID",
                "operationId": "countries_get_v2_countries__country_id__get",
                "parameters": [
                    {
                        "required": true,
                        "schema": {
                            "title": "Country Id",
                            "maxLength": 2,
                            "minLength": 2,
                            "pattern": "[a-zA-Z][a-zA-Z]",
                            "type": "string"
                        },
                        "name": "country_id",
                        "in": "path"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Limit",
                            "type": "integer",
                            "default": 200
                        },
                        "name": "limit",
                        "in": "query"
                    },
                    {
                        "description": "Paginate through results. e.g. page=1 will return first page of results",
                        "required": false,
                        "schema": {
                            "title": "Page",
                            "maximum": 6000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Paginate through results. e.g. page=1 will return first page of results",
                            "default": 1
                        },
                        "name": "page",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Offset",
                            "maximum": 10000.0,
                            "minimum": 0.0,
                            "type": "integer",
                            "default": 0
                        },
                        "name": "offset",
                        "in": "query"
                    },
                    {
                        "description": "Define sort order.",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/Sort"
                                }
                            ],
                            "description": "Define sort order.",
                            "default": "asc"
                        },
                        "name": "sort",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)",
                        "required": false,
                        "schema": {
                            "title": "Country",
                            "type": "array",
                            "items": {
                                "maxLength": 2,
                                "minLength": 2,
                                "pattern": "[a-zA-Z][a-zA-Z]",
                                "type": "string"
                            },
                            "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)"
                        },
                        "name": "country",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/CountriesOrder"
                                }
                            ],
                            "default": "country"
                        },
                        "name": "order_by",
                        "in": "query"
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/CountriesResponse"
                                }
                            }
                        }
                    },
                    "422": {
                        "description": "Validation Error",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/HTTPValidationError"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v1/countries/{country_id}": {
            "get": {
                "tags": [
                    "v1"
                ],
                "summary": "Get country by ID",
                "description": "Provides a single country by country ID",
                "operationId": "countries_get_v1_countries__country_id__get",
                "parameters": [
                    {
                        "required": true,
                        "schema": {
                            "title": "Country Id",
                            "maxLength": 2,
                            "minLength": 2,
                            "pattern": "[a-zA-Z][a-zA-Z]",
                            "type": "string"
                        },
                        "name": "country_id",
                        "in": "path"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Limit",
                            "type": "integer",
                            "default": 200
                        },
                        "name": "limit",
                        "in": "query"
                    },
                    {
                        "description": "Paginate through results. e.g. page=1 will return first page of results",
                        "required": false,
                        "schema": {
                            "title": "Page",
                            "maximum": 6000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Paginate through results. e.g. page=1 will return first page of results",
                            "default": 1
                        },
                        "name": "page",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Offset",
                            "maximum": 10000.0,
                            "minimum": 0.0,
                            "type": "integer",
                            "default": 0
                        },
                        "name": "offset",
                        "in": "query"
                    },
                    {
                        "description": "Define sort order.",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/Sort"
                                }
                            ],
                            "description": "Define sort order.",
                            "default": "asc"
                        },
                        "name": "sort",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)",
                        "required": false,
                        "schema": {
                            "title": "Country",
                            "type": "array",
                            "items": {
                                "maxLength": 2,
                                "minLength": 2,
                                "pattern": "[a-zA-Z][a-zA-Z]",
                                "type": "string"
                            },
                            "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)"
                        },
                        "name": "country",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/CountriesOrder"
                                }
                            ],
                            "default": "country"
                        },
                        "name": "order_by",
                        "in": "query"
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/CountriesResponse"
                                }
                            }
                        }
                    },
                    "422": {
                        "description": "Validation Error",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/HTTPValidationError"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v1/countries": {
            "get": {
                "tags": [
                    "v1"
                ],
                "summary": "Get countries",
                "description": "Providecs a list of countries",
                "operationId": "countries_getv1_v1_countries_get",
                "parameters": [
                    {
                        "required": false,
                        "schema": {
                            "title": "Limit",
                            "type": "integer",
                            "default": 200
                        },
                        "name": "limit",
                        "in": "query"
                    },
                    {
                        "description": "Paginate through results. e.g. page=1 will return first page of results",
                        "required": false,
                        "schema": {
                            "title": "Page",
                            "maximum": 6000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Paginate through results. e.g. page=1 will return first page of results",
                            "default": 1
                        },
                        "name": "page",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Offset",
                            "maximum": 10000.0,
                            "minimum": 0.0,
                            "type": "integer",
                            "default": 0
                        },
                        "name": "offset",
                        "in": "query"
                    },
                    {
                        "description": "Define sort order.",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/Sort"
                                }
                            ],
                            "description": "Define sort order.",
                            "default": "asc"
                        },
                        "name": "sort",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. /US)",
                        "required": false,
                        "schema": {
                            "title": "Country Id",
                            "maxLength": 2,
                            "minLength": 2,
                            "pattern": "[a-zA-Z][a-zA-Z]",
                            "type": "string",
                            "description": "Limit results by a certain country using two letter country code. (e.g. /US)"
                        },
                        "name": "country_id",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)",
                        "required": false,
                        "schema": {
                            "title": "Country",
                            "type": "array",
                            "items": {
                                "maxLength": 2,
                                "minLength": 2,
                                "pattern": "[a-zA-Z][a-zA-Z]",
                                "type": "string"
                            },
                            "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)"
                        },
                        "name": "country",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/CountriesOrder"
                                }
                            ],
                            "default": "country"
                        },
                        "name": "order_by",
                        "in": "query"
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/CountriesResponse"
                                }
                            }
                        }
                    },
                    "422": {
                        "description": "Validation Error",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/HTTPValidationError"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v2/locations": {
            "get": {
                "tags": [
                    "v2"
                ],
                "summary": "Get locations",
                "description": "Provides a list of locations",
                "operationId": "locations_get_v2_locations_get",
                "parameters": [
                    {
                        "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                        "required": false,
                        "schema": {
                            "title": "Limit",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                            "default": 100
                        },
                        "name": "limit",
                        "in": "query"
                    },
                    {
                        "description": "Paginate through results. e.g. page=1 will return first page of results",
                        "required": false,
                        "schema": {
                            "title": "Page",
                            "maximum": 6000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Paginate through results. e.g. page=1 will return first page of results",
                            "default": 1
                        },
                        "name": "page",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Offset",
                            "maximum": 10000.0,
                            "minimum": 0.0,
                            "type": "integer",
                            "default": 0
                        },
                        "name": "offset",
                        "in": "query"
                    },
                    {
                        "description": "Sort Direction",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/Sort"
                                }
                            ],
                            "description": "Sort Direction",
                            "default": "desc"
                        },
                        "name": "sort",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Has Geo",
                            "type": "boolean"
                        },
                        "name": "has_geo",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements",
                        "required": false,
                        "schema": {
                            "title": "Parameter Id",
                            "type": "integer",
                            "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements"
                        },
                        "name": "parameter_id",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10",
                        "required": false,
                        "schema": {
                            "title": "Parameter",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "maximum": 2147483647.0,
                                        "exclusiveMinimum": true,
                                        "minimum": 0.0,
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            },
                            "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10"
                        },
                        "name": "parameter",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Unit",
                            "type": "array",
                            "items": {
                                "type": "string"
                            }
                        },
                        "name": "unit",
                        "in": "query"
                    },
                    {
                        "description": "Coordinate pair in form lat,lng. Up to 8 decimal points of precision e.g. 38.907,-77.037",
                        "required": false,
                        "schema": {
                            "title": "Coordinates",
                            "pattern": "^-?\\d{1,2}\\.?\\d{0,8},-?1?\\d{1,2}\\.?\\d{0,8}$",
                            "type": "string",
                            "description": "Coordinate pair in form lat,lng. Up to 8 decimal points of precision e.g. 38.907,-77.037"
                        },
                        "name": "coordinates",
                        "in": "query"
                    },
                    {
                        "description": "Search radius from coordinates as center in meters. Maximum of 100,000 (100km) defaults to 1000 (1km)",
                        "required": false,
                        "schema": {
                            "title": "Radius",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Search radius from coordinates as center in meters. Maximum of 100,000 (100km) defaults to 1000 (1km)",
                            "default": 1000
                        },
                        "name": "radius",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. /US)",
                        "required": false,
                        "schema": {
                            "title": "Country Id",
                            "maxLength": 2,
                            "minLength": 2,
                            "pattern": "[a-zA-Z][a-zA-Z]",
                            "type": "string",
                            "description": "Limit results by a certain country using two letter country code. (e.g. /US)"
                        },
                        "name": "country_id",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)",
                        "required": false,
                        "schema": {
                            "title": "Country",
                            "type": "array",
                            "items": {
                                "maxLength": 2,
                                "minLength": 2,
                                "pattern": "[a-zA-Z][a-zA-Z]",
                                "type": "string"
                            },
                            "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)"
                        },
                        "name": "country",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain city or cities. (e.g. ?city=Chicago or ?city=Chicago&city=Boston)",
                        "required": false,
                        "schema": {
                            "title": "City",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Limit results by a certain city or cities. (e.g. ?city=Chicago or ?city=Chicago&city=Boston)"
                        },
                        "name": "city",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Location Id",
                            "type": "integer"
                        },
                        "name": "location_id",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Location",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            }
                        },
                        "name": "location",
                        "in": "query"
                    },
                    {
                        "description": "Order by a field",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/LocationsOrder"
                                }
                            ],
                            "description": "Order by a field",
                            "default": "lastUpdated"
                        },
                        "name": "order_by",
                        "in": "query"
                    },
                    {
                        "description": "Location is mobile",
                        "required": false,
                        "schema": {
                            "title": "Ismobile",
                            "type": "boolean",
                            "description": "Location is mobile"
                        },
                        "name": "isMobile",
                        "in": "query"
                    },
                    {
                        "description": "Data is the product of a previous analysis/aggregation and not raw measurements",
                        "required": false,
                        "schema": {
                            "title": "Isanalysis",
                            "type": "boolean",
                            "description": "Data is the product of a previous analysis/aggregation and not raw measurements"
                        },
                        "name": "isAnalysis",
                        "in": "query"
                    },
                    {
                        "description": "Name of the data source",
                        "required": false,
                        "schema": {
                            "title": "Sourcename",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Name of the data source"
                        },
                        "name": "sourceName",
                        "in": "query"
                    },
                    {
                        "description": "Source entity type.",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/EntityTypes"
                                }
                            ],
                            "description": "Source entity type."
                        },
                        "name": "entity",
                        "in": "query"
                    },
                    {
                        "description": "Type of Sensor",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/SensorTypes"
                                }
                            ],
                            "description": "Type of Sensor"
                        },
                        "name": "sensorType",
                        "in": "query"
                    },
                    {
                        "description": "Model Name of Sensor",
                        "required": false,
                        "schema": {
                            "title": "Modelname",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Model Name of Sensor"
                        },
                        "name": "modelName",
                        "in": "query"
                    },
                    {
                        "description": "Manufacturer of Sensor",
                        "required": false,
                        "schema": {
                            "title": "Manufacturername",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Manufacturer of Sensor"
                        },
                        "name": "manufacturerName",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Dumpraw",
                            "type": "boolean",
                            "default": false
                        },
                        "name": "dumpRaw",
                        "in": "query"
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/LocationsResponse"
                                }
                            }
                        }
                    },
                    "422": {
                        "description": "Validation Error",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/HTTPValidationError"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v2/locations/{location_id}": {
            "get": {
                "tags": [
                    "v2"
                ],
                "summary": "Get a location by ID",
                "description": "Provides a location by location ID",
                "operationId": "locations_get_v2_locations__location_id__get",
                "parameters": [
                    {
                        "required": true,
                        "schema": {
                            "title": "Location Id",
                            "type": "integer"
                        },
                        "name": "location_id",
                        "in": "path"
                    },
                    {
                        "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                        "required": false,
                        "schema": {
                            "title": "Limit",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                            "default": 100
                        },
                        "name": "limit",
                        "in": "query"
                    },
                    {
                        "description": "Paginate through results. e.g. page=1 will return first page of results",
                        "required": false,
                        "schema": {
                            "title": "Page",
                            "maximum": 6000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Paginate through results. e.g. page=1 will return first page of results",
                            "default": 1
                        },
                        "name": "page",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Offset",
                            "maximum": 10000.0,
                            "minimum": 0.0,
                            "type": "integer",
                            "default": 0
                        },
                        "name": "offset",
                        "in": "query"
                    },
                    {
                        "description": "Sort Direction",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/Sort"
                                }
                            ],
                            "description": "Sort Direction",
                            "default": "desc"
                        },
                        "name": "sort",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Has Geo",
                            "type": "boolean"
                        },
                        "name": "has_geo",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements",
                        "required": false,
                        "schema": {
                            "title": "Parameter Id",
                            "type": "integer",
                            "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements"
                        },
                        "name": "parameter_id",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10",
                        "required": false,
                        "schema": {
                            "title": "Parameter",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "maximum": 2147483647.0,
                                        "exclusiveMinimum": true,
                                        "minimum": 0.0,
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            },
                            "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10"
                        },
                        "name": "parameter",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Unit",
                            "type": "array",
                            "items": {
                                "type": "string"
                            }
                        },
                        "name": "unit",
                        "in": "query"
                    },
                    {
                        "description": "Coordinate pair in form lat,lng. Up to 8 decimal points of precision e.g. 38.907,-77.037",
                        "required": false,
                        "schema": {
                            "title": "Coordinates",
                            "pattern": "^-?\\d{1,2}\\.?\\d{0,8},-?1?\\d{1,2}\\.?\\d{0,8}$",
                            "type": "string",
                            "description": "Coordinate pair in form lat,lng. Up to 8 decimal points of precision e.g. 38.907,-77.037"
                        },
                        "name": "coordinates",
                        "in": "query"
                    },
                    {
                        "description": "Search radius from coordinates as center in meters. Maximum of 100,000 (100km) defaults to 1000 (1km)",
                        "required": false,
                        "schema": {
                            "title": "Radius",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Search radius from coordinates as center in meters. Maximum of 100,000 (100km) defaults to 1000 (1km)",
                            "default": 1000
                        },
                        "name": "radius",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. /US)",
                        "required": false,
                        "schema": {
                            "title": "Country Id",
                            "maxLength": 2,
                            "minLength": 2,
                            "pattern": "[a-zA-Z][a-zA-Z]",
                            "type": "string",
                            "description": "Limit results by a certain country using two letter country code. (e.g. /US)"
                        },
                        "name": "country_id",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)",
                        "required": false,
                        "schema": {
                            "title": "Country",
                            "type": "array",
                            "items": {
                                "maxLength": 2,
                                "minLength": 2,
                                "pattern": "[a-zA-Z][a-zA-Z]",
                                "type": "string"
                            },
                            "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)"
                        },
                        "name": "country",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain city or cities. (e.g. ?city=Chicago or ?city=Chicago&city=Boston)",
                        "required": false,
                        "schema": {
                            "title": "City",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Limit results by a certain city or cities. (e.g. ?city=Chicago or ?city=Chicago&city=Boston)"
                        },
                        "name": "city",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Location",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            }
                        },
                        "name": "location",
                        "in": "query"
                    },
                    {
                        "description": "Order by a field",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/LocationsOrder"
                                }
                            ],
                            "description": "Order by a field",
                            "default": "lastUpdated"
                        },
                        "name": "order_by",
                        "in": "query"
                    },
                    {
                        "description": "Location is mobile",
                        "required": false,
                        "schema": {
                            "title": "Ismobile",
                            "type": "boolean",
                            "description": "Location is mobile"
                        },
                        "name": "isMobile",
                        "in": "query"
                    },
                    {
                        "description": "Data is the product of a previous analysis/aggregation and not raw measurements",
                        "required": false,
                        "schema": {
                            "title": "Isanalysis",
                            "type": "boolean",
                            "description": "Data is the product of a previous analysis/aggregation and not raw measurements"
                        },
                        "name": "isAnalysis",
                        "in": "query"
                    },
                    {
                        "description": "Name of the data source",
                        "required": false,
                        "schema": {
                            "title": "Sourcename",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Name of the data source"
                        },
                        "name": "sourceName",
                        "in": "query"
                    },
                    {
                        "description": "Source entity type.",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/EntityTypes"
                                }
                            ],
                            "description": "Source entity type."
                        },
                        "name": "entity",
                        "in": "query"
                    },
                    {
                        "description": "Type of Sensor",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/SensorTypes"
                                }
                            ],
                            "description": "Type of Sensor"
                        },
                        "name": "sensorType",
                        "in": "query"
                    },
                    {
                        "description": "Model Name of Sensor",
                        "required": false,
                        "schema": {
                            "title": "Modelname",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Model Name of Sensor"
                        },
                        "name": "modelName",
                        "in": "query"
                    },
                    {
                        "description": "Manufacturer of Sensor",
                        "required": false,
                        "schema": {
                            "title": "Manufacturername",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Manufacturer of Sensor"
                        },
                        "name": "manufacturerName",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Dumpraw",
                            "type": "boolean",
                            "default": false
                        },
                        "name": "dumpRaw",
                        "in": "query"
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/LocationsResponse"
                                }
                            }
                        }
                    },
                    "422": {
                        "description": "Validation Error",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/HTTPValidationError"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v2/latest": {
            "get": {
                "tags": [
                    "v2"
                ],
                "summary": "Get latest measurements",
                "description": "Provides a list of locations with latest measurements",
                "operationId": "latest_get_v2_latest_get",
                "parameters": [
                    {
                        "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                        "required": false,
                        "schema": {
                            "title": "Limit",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                            "default": 100
                        },
                        "name": "limit",
                        "in": "query"
                    },
                    {
                        "description": "Paginate through results. e.g. page=1 will return first page of results",
                        "required": false,
                        "schema": {
                            "title": "Page",
                            "maximum": 6000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Paginate through results. e.g. page=1 will return first page of results",
                            "default": 1
                        },
                        "name": "page",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Offset",
                            "maximum": 10000.0,
                            "minimum": 0.0,
                            "type": "integer",
                            "default": 0
                        },
                        "name": "offset",
                        "in": "query"
                    },
                    {
                        "description": "Sort Direction",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/Sort"
                                }
                            ],
                            "description": "Sort Direction",
                            "default": "desc"
                        },
                        "name": "sort",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Has Geo",
                            "type": "boolean"
                        },
                        "name": "has_geo",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements",
                        "required": false,
                        "schema": {
                            "title": "Parameter Id",
                            "type": "integer",
                            "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements"
                        },
                        "name": "parameter_id",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10",
                        "required": false,
                        "schema": {
                            "title": "Parameter",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "maximum": 2147483647.0,
                                        "exclusiveMinimum": true,
                                        "minimum": 0.0,
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            },
                            "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10"
                        },
                        "name": "parameter",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Unit",
                            "type": "array",
                            "items": {
                                "type": "string"
                            }
                        },
                        "name": "unit",
                        "in": "query"
                    },
                    {
                        "description": "Coordinate pair in form lat,lng. Up to 8 decimal points of precision e.g. 38.907,-77.037",
                        "required": false,
                        "schema": {
                            "title": "Coordinates",
                            "pattern": "^-?\\d{1,2}\\.?\\d{0,8},-?1?\\d{1,2}\\.?\\d{0,8}$",
                            "type": "string",
                            "description": "Coordinate pair in form lat,lng. Up to 8 decimal points of precision e.g. 38.907,-77.037"
                        },
                        "name": "coordinates",
                        "in": "query"
                    },
                    {
                        "description": "Search radius from coordinates as center in meters. Maximum of 100,000 (100km) defaults to 1000 (1km)",
                        "required": false,
                        "schema": {
                            "title": "Radius",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Search radius from coordinates as center in meters. Maximum of 100,000 (100km) defaults to 1000 (1km)",
                            "default": 1000
                        },
                        "name": "radius",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. /US)",
                        "required": false,
                        "schema": {
                            "title": "Country Id",
                            "maxLength": 2,
                            "minLength": 2,
                            "pattern": "[a-zA-Z][a-zA-Z]",
                            "type": "string",
                            "description": "Limit results by a certain country using two letter country code. (e.g. /US)"
                        },
                        "name": "country_id",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)",
                        "required": false,
                        "schema": {
                            "title": "Country",
                            "type": "array",
                            "items": {
                                "maxLength": 2,
                                "minLength": 2,
                                "pattern": "[a-zA-Z][a-zA-Z]",
                                "type": "string"
                            },
                            "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)"
                        },
                        "name": "country",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain city or cities. (e.g. ?city=Chicago or ?city=Chicago&city=Boston)",
                        "required": false,
                        "schema": {
                            "title": "City",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Limit results by a certain city or cities. (e.g. ?city=Chicago or ?city=Chicago&city=Boston)"
                        },
                        "name": "city",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Location Id",
                            "type": "integer"
                        },
                        "name": "location_id",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Location",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            }
                        },
                        "name": "location",
                        "in": "query"
                    },
                    {
                        "description": "Order by a field",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/LocationsOrder"
                                }
                            ],
                            "description": "Order by a field",
                            "default": "lastUpdated"
                        },
                        "name": "order_by",
                        "in": "query"
                    },
                    {
                        "description": "Location is mobile",
                        "required": false,
                        "schema": {
                            "title": "Ismobile",
                            "type": "boolean",
                            "description": "Location is mobile"
                        },
                        "name": "isMobile",
                        "in": "query"
                    },
                    {
                        "description": "Data is the product of a previous analysis/aggregation and not raw measurements",
                        "required": false,
                        "schema": {
                            "title": "Isanalysis",
                            "type": "boolean",
                            "description": "Data is the product of a previous analysis/aggregation and not raw measurements"
                        },
                        "name": "isAnalysis",
                        "in": "query"
                    },
                    {
                        "description": "Name of the data source",
                        "required": false,
                        "schema": {
                            "title": "Sourcename",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Name of the data source"
                        },
                        "name": "sourceName",
                        "in": "query"
                    },
                    {
                        "description": "Source entity type.",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/EntityTypes"
                                }
                            ],
                            "description": "Source entity type."
                        },
                        "name": "entity",
                        "in": "query"
                    },
                    {
                        "description": "Type of Sensor",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/SensorTypes"
                                }
                            ],
                            "description": "Type of Sensor"
                        },
                        "name": "sensorType",
                        "in": "query"
                    },
                    {
                        "description": "Model Name of Sensor",
                        "required": false,
                        "schema": {
                            "title": "Modelname",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Model Name of Sensor"
                        },
                        "name": "modelName",
                        "in": "query"
                    },
                    {
                        "description": "Manufacturer of Sensor",
                        "required": false,
                        "schema": {
                            "title": "Manufacturername",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Manufacturer of Sensor"
                        },
                        "name": "manufacturerName",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Dumpraw",
                            "type": "boolean",
                            "default": false
                        },
                        "name": "dumpRaw",
                        "in": "query"
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/LatestResponse"
                                }
                            }
                        }
                    },
                    "422": {
                        "description": "Validation Error",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/HTTPValidationError"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v2/latest/{location_id}": {
            "get": {
                "tags": [
                    "v2"
                ],
                "summary": "Get latest measurements by location ID",
                "description": "Provides latest measurements for a locations by location ID",
                "operationId": "latest_get_v2_latest__location_id__get",
                "parameters": [
                    {
                        "required": true,
                        "schema": {
                            "title": "Location Id",
                            "type": "integer"
                        },
                        "name": "location_id",
                        "in": "path"
                    },
                    {
                        "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                        "required": false,
                        "schema": {
                            "title": "Limit",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                            "default": 100
                        },
                        "name": "limit",
                        "in": "query"
                    },
                    {
                        "description": "Paginate through results. e.g. page=1 will return first page of results",
                        "required": false,
                        "schema": {
                            "title": "Page",
                            "maximum": 6000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Paginate through results. e.g. page=1 will return first page of results",
                            "default": 1
                        },
                        "name": "page",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Offset",
                            "maximum": 10000.0,
                            "minimum": 0.0,
                            "type": "integer",
                            "default": 0
                        },
                        "name": "offset",
                        "in": "query"
                    },
                    {
                        "description": "Sort Direction",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/Sort"
                                }
                            ],
                            "description": "Sort Direction",
                            "default": "desc"
                        },
                        "name": "sort",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Has Geo",
                            "type": "boolean"
                        },
                        "name": "has_geo",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements",
                        "required": false,
                        "schema": {
                            "title": "Parameter Id",
                            "type": "integer",
                            "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements"
                        },
                        "name": "parameter_id",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10",
                        "required": false,
                        "schema": {
                            "title": "Parameter",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "maximum": 2147483647.0,
                                        "exclusiveMinimum": true,
                                        "minimum": 0.0,
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            },
                            "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10"
                        },
                        "name": "parameter",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Unit",
                            "type": "array",
                            "items": {
                                "type": "string"
                            }
                        },
                        "name": "unit",
                        "in": "query"
                    },
                    {
                        "description": "Coordinate pair in form lat,lng. Up to 8 decimal points of precision e.g. 38.907,-77.037",
                        "required": false,
                        "schema": {
                            "title": "Coordinates",
                            "pattern": "^-?\\d{1,2}\\.?\\d{0,8},-?1?\\d{1,2}\\.?\\d{0,8}$",
                            "type": "string",
                            "description": "Coordinate pair in form lat,lng. Up to 8 decimal points of precision e.g. 38.907,-77.037"
                        },
                        "name": "coordinates",
                        "in": "query"
                    },
                    {
                        "description": "Search radius from coordinates as center in meters. Maximum of 100,000 (100km) defaults to 1000 (1km)",
                        "required": false,
                        "schema": {
                            "title": "Radius",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Search radius from coordinates as center in meters. Maximum of 100,000 (100km) defaults to 1000 (1km)",
                            "default": 1000
                        },
                        "name": "radius",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. /US)",
                        "required": false,
                        "schema": {
                            "title": "Country Id",
                            "maxLength": 2,
                            "minLength": 2,
                            "pattern": "[a-zA-Z][a-zA-Z]",
                            "type": "string",
                            "description": "Limit results by a certain country using two letter country code. (e.g. /US)"
                        },
                        "name": "country_id",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)",
                        "required": false,
                        "schema": {
                            "title": "Country",
                            "type": "array",
                            "items": {
                                "maxLength": 2,
                                "minLength": 2,
                                "pattern": "[a-zA-Z][a-zA-Z]",
                                "type": "string"
                            },
                            "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)"
                        },
                        "name": "country",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain city or cities. (e.g. ?city=Chicago or ?city=Chicago&city=Boston)",
                        "required": false,
                        "schema": {
                            "title": "City",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Limit results by a certain city or cities. (e.g. ?city=Chicago or ?city=Chicago&city=Boston)"
                        },
                        "name": "city",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Location",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            }
                        },
                        "name": "location",
                        "in": "query"
                    },
                    {
                        "description": "Order by a field",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/LocationsOrder"
                                }
                            ],
                            "description": "Order by a field",
                            "default": "lastUpdated"
                        },
                        "name": "order_by",
                        "in": "query"
                    },
                    {
                        "description": "Location is mobile",
                        "required": false,
                        "schema": {
                            "title": "Ismobile",
                            "type": "boolean",
                            "description": "Location is mobile"
                        },
                        "name": "isMobile",
                        "in": "query"
                    },
                    {
                        "description": "Data is the product of a previous analysis/aggregation and not raw measurements",
                        "required": false,
                        "schema": {
                            "title": "Isanalysis",
                            "type": "boolean",
                            "description": "Data is the product of a previous analysis/aggregation and not raw measurements"
                        },
                        "name": "isAnalysis",
                        "in": "query"
                    },
                    {
                        "description": "Name of the data source",
                        "required": false,
                        "schema": {
                            "title": "Sourcename",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Name of the data source"
                        },
                        "name": "sourceName",
                        "in": "query"
                    },
                    {
                        "description": "Source entity type.",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/EntityTypes"
                                }
                            ],
                            "description": "Source entity type."
                        },
                        "name": "entity",
                        "in": "query"
                    },
                    {
                        "description": "Type of Sensor",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/SensorTypes"
                                }
                            ],
                            "description": "Type of Sensor"
                        },
                        "name": "sensorType",
                        "in": "query"
                    },
                    {
                        "description": "Model Name of Sensor",
                        "required": false,
                        "schema": {
                            "title": "Modelname",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Model Name of Sensor"
                        },
                        "name": "modelName",
                        "in": "query"
                    },
                    {
                        "description": "Manufacturer of Sensor",
                        "required": false,
                        "schema": {
                            "title": "Manufacturername",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Manufacturer of Sensor"
                        },
                        "name": "manufacturerName",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Dumpraw",
                            "type": "boolean",
                            "default": false
                        },
                        "name": "dumpRaw",
                        "in": "query"
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/LatestResponse"
                                }
                            }
                        }
                    },
                    "422": {
                        "description": "Validation Error",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/HTTPValidationError"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v1/latest": {
            "get": {
                "tags": [
                    "v1"
                ],
                "summary": "Get latest measurements",
                "operationId": "latest_v1_get_v1_latest_get",
                "parameters": [
                    {
                        "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                        "required": false,
                        "schema": {
                            "title": "Limit",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                            "default": 100
                        },
                        "name": "limit",
                        "in": "query"
                    },
                    {
                        "description": "Paginate through results. e.g. page=1 will return first page of results",
                        "required": false,
                        "schema": {
                            "title": "Page",
                            "maximum": 6000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Paginate through results. e.g. page=1 will return first page of results",
                            "default": 1
                        },
                        "name": "page",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Offset",
                            "maximum": 10000.0,
                            "minimum": 0.0,
                            "type": "integer",
                            "default": 0
                        },
                        "name": "offset",
                        "in": "query"
                    },
                    {
                        "description": "Sort Direction",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/Sort"
                                }
                            ],
                            "description": "Sort Direction",
                            "default": "desc"
                        },
                        "name": "sort",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Has Geo",
                            "type": "boolean"
                        },
                        "name": "has_geo",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements",
                        "required": false,
                        "schema": {
                            "title": "Parameter Id",
                            "type": "integer",
                            "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements"
                        },
                        "name": "parameter_id",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10",
                        "required": false,
                        "schema": {
                            "title": "Parameter",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "maximum": 2147483647.0,
                                        "exclusiveMinimum": true,
                                        "minimum": 0.0,
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            },
                            "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10"
                        },
                        "name": "parameter",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Unit",
                            "type": "array",
                            "items": {
                                "type": "string"
                            }
                        },
                        "name": "unit",
                        "in": "query"
                    },
                    {
                        "description": "Coordinate pair in form lat,lng. Up to 8 decimal points of precision e.g. 38.907,-77.037",
                        "required": false,
                        "schema": {
                            "title": "Coordinates",
                            "pattern": "^-?\\d{1,2}\\.?\\d{0,8},-?1?\\d{1,2}\\.?\\d{0,8}$",
                            "type": "string",
                            "description": "Coordinate pair in form lat,lng. Up to 8 decimal points of precision e.g. 38.907,-77.037"
                        },
                        "name": "coordinates",
                        "in": "query"
                    },
                    {
                        "description": "Search radius from coordinates as center in meters. Maximum of 100,000 (100km) defaults to 1000 (1km)",
                        "required": false,
                        "schema": {
                            "title": "Radius",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Search radius from coordinates as center in meters. Maximum of 100,000 (100km) defaults to 1000 (1km)",
                            "default": 1000
                        },
                        "name": "radius",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. /US)",
                        "required": false,
                        "schema": {
                            "title": "Country Id",
                            "maxLength": 2,
                            "minLength": 2,
                            "pattern": "[a-zA-Z][a-zA-Z]",
                            "type": "string",
                            "description": "Limit results by a certain country using two letter country code. (e.g. /US)"
                        },
                        "name": "country_id",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)",
                        "required": false,
                        "schema": {
                            "title": "Country",
                            "type": "array",
                            "items": {
                                "maxLength": 2,
                                "minLength": 2,
                                "pattern": "[a-zA-Z][a-zA-Z]",
                                "type": "string"
                            },
                            "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)"
                        },
                        "name": "country",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain city or cities. (e.g. ?city=Chicago or ?city=Chicago&city=Boston)",
                        "required": false,
                        "schema": {
                            "title": "City",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Limit results by a certain city or cities. (e.g. ?city=Chicago or ?city=Chicago&city=Boston)"
                        },
                        "name": "city",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Location Id",
                            "type": "integer"
                        },
                        "name": "location_id",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Location",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            }
                        },
                        "name": "location",
                        "in": "query"
                    },
                    {
                        "description": "Order by a field",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/LocationsOrder"
                                }
                            ],
                            "description": "Order by a field",
                            "default": "lastUpdated"
                        },
                        "name": "order_by",
                        "in": "query"
                    },
                    {
                        "description": "Location is mobile",
                        "required": false,
                        "schema": {
                            "title": "Ismobile",
                            "type": "boolean",
                            "description": "Location is mobile"
                        },
                        "name": "isMobile",
                        "in": "query"
                    },
                    {
                        "description": "Data is the product of a previous analysis/aggregation and not raw measurements",
                        "required": false,
                        "schema": {
                            "title": "Isanalysis",
                            "type": "boolean",
                            "description": "Data is the product of a previous analysis/aggregation and not raw measurements"
                        },
                        "name": "isAnalysis",
                        "in": "query"
                    },
                    {
                        "description": "Name of the data source",
                        "required": false,
                        "schema": {
                            "title": "Sourcename",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Name of the data source"
                        },
                        "name": "sourceName",
                        "in": "query"
                    },
                    {
                        "description": "Source entity type.",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/EntityTypes"
                                }
                            ],
                            "description": "Source entity type."
                        },
                        "name": "entity",
                        "in": "query"
                    },
                    {
                        "description": "Type of Sensor",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/SensorTypes"
                                }
                            ],
                            "description": "Type of Sensor"
                        },
                        "name": "sensorType",
                        "in": "query"
                    },
                    {
                        "description": "Model Name of Sensor",
                        "required": false,
                        "schema": {
                            "title": "Modelname",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Model Name of Sensor"
                        },
                        "name": "modelName",
                        "in": "query"
                    },
                    {
                        "description": "Manufacturer of Sensor",
                        "required": false,
                        "schema": {
                            "title": "Manufacturername",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Manufacturer of Sensor"
                        },
                        "name": "manufacturerName",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Dumpraw",
                            "type": "boolean",
                            "default": false
                        },
                        "name": "dumpRaw",
                        "in": "query"
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/LatestResponseV1"
                                }
                            }
                        }
                    },
                    "422": {
                        "description": "Validation Error",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/HTTPValidationError"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v1/latest/{location_id}": {
            "get": {
                "tags": [
                    "v1"
                ],
                "summary": "Get latest measurements by location ID",
                "operationId": "latest_v1_get_v1_latest__location_id__get",
                "parameters": [
                    {
                        "required": true,
                        "schema": {
                            "title": "Location Id",
                            "type": "integer"
                        },
                        "name": "location_id",
                        "in": "path"
                    },
                    {
                        "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                        "required": false,
                        "schema": {
                            "title": "Limit",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                            "default": 100
                        },
                        "name": "limit",
                        "in": "query"
                    },
                    {
                        "description": "Paginate through results. e.g. page=1 will return first page of results",
                        "required": false,
                        "schema": {
                            "title": "Page",
                            "maximum": 6000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Paginate through results. e.g. page=1 will return first page of results",
                            "default": 1
                        },
                        "name": "page",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Offset",
                            "maximum": 10000.0,
                            "minimum": 0.0,
                            "type": "integer",
                            "default": 0
                        },
                        "name": "offset",
                        "in": "query"
                    },
                    {
                        "description": "Sort Direction",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/Sort"
                                }
                            ],
                            "description": "Sort Direction",
                            "default": "desc"
                        },
                        "name": "sort",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Has Geo",
                            "type": "boolean"
                        },
                        "name": "has_geo",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements",
                        "required": false,
                        "schema": {
                            "title": "Parameter Id",
                            "type": "integer",
                            "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements"
                        },
                        "name": "parameter_id",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10",
                        "required": false,
                        "schema": {
                            "title": "Parameter",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "maximum": 2147483647.0,
                                        "exclusiveMinimum": true,
                                        "minimum": 0.0,
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            },
                            "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10"
                        },
                        "name": "parameter",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Unit",
                            "type": "array",
                            "items": {
                                "type": "string"
                            }
                        },
                        "name": "unit",
                        "in": "query"
                    },
                    {
                        "description": "Coordinate pair in form lat,lng. Up to 8 decimal points of precision e.g. 38.907,-77.037",
                        "required": false,
                        "schema": {
                            "title": "Coordinates",
                            "pattern": "^-?\\d{1,2}\\.?\\d{0,8},-?1?\\d{1,2}\\.?\\d{0,8}$",
                            "type": "string",
                            "description": "Coordinate pair in form lat,lng. Up to 8 decimal points of precision e.g. 38.907,-77.037"
                        },
                        "name": "coordinates",
                        "in": "query"
                    },
                    {
                        "description": "Search radius from coordinates as center in meters. Maximum of 100,000 (100km) defaults to 1000 (1km)",
                        "required": false,
                        "schema": {
                            "title": "Radius",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Search radius from coordinates as center in meters. Maximum of 100,000 (100km) defaults to 1000 (1km)",
                            "default": 1000
                        },
                        "name": "radius",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. /US)",
                        "required": false,
                        "schema": {
                            "title": "Country Id",
                            "maxLength": 2,
                            "minLength": 2,
                            "pattern": "[a-zA-Z][a-zA-Z]",
                            "type": "string",
                            "description": "Limit results by a certain country using two letter country code. (e.g. /US)"
                        },
                        "name": "country_id",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)",
                        "required": false,
                        "schema": {
                            "title": "Country",
                            "type": "array",
                            "items": {
                                "maxLength": 2,
                                "minLength": 2,
                                "pattern": "[a-zA-Z][a-zA-Z]",
                                "type": "string"
                            },
                            "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)"
                        },
                        "name": "country",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain city or cities. (e.g. ?city=Chicago or ?city=Chicago&city=Boston)",
                        "required": false,
                        "schema": {
                            "title": "City",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Limit results by a certain city or cities. (e.g. ?city=Chicago or ?city=Chicago&city=Boston)"
                        },
                        "name": "city",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Location",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            }
                        },
                        "name": "location",
                        "in": "query"
                    },
                    {
                        "description": "Order by a field",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/LocationsOrder"
                                }
                            ],
                            "description": "Order by a field",
                            "default": "lastUpdated"
                        },
                        "name": "order_by",
                        "in": "query"
                    },
                    {
                        "description": "Location is mobile",
                        "required": false,
                        "schema": {
                            "title": "Ismobile",
                            "type": "boolean",
                            "description": "Location is mobile"
                        },
                        "name": "isMobile",
                        "in": "query"
                    },
                    {
                        "description": "Data is the product of a previous analysis/aggregation and not raw measurements",
                        "required": false,
                        "schema": {
                            "title": "Isanalysis",
                            "type": "boolean",
                            "description": "Data is the product of a previous analysis/aggregation and not raw measurements"
                        },
                        "name": "isAnalysis",
                        "in": "query"
                    },
                    {
                        "description": "Name of the data source",
                        "required": false,
                        "schema": {
                            "title": "Sourcename",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Name of the data source"
                        },
                        "name": "sourceName",
                        "in": "query"
                    },
                    {
                        "description": "Source entity type.",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/EntityTypes"
                                }
                            ],
                            "description": "Source entity type."
                        },
                        "name": "entity",
                        "in": "query"
                    },
                    {
                        "description": "Type of Sensor",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/SensorTypes"
                                }
                            ],
                            "description": "Type of Sensor"
                        },
                        "name": "sensorType",
                        "in": "query"
                    },
                    {
                        "description": "Model Name of Sensor",
                        "required": false,
                        "schema": {
                            "title": "Modelname",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Model Name of Sensor"
                        },
                        "name": "modelName",
                        "in": "query"
                    },
                    {
                        "description": "Manufacturer of Sensor",
                        "required": false,
                        "schema": {
                            "title": "Manufacturername",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Manufacturer of Sensor"
                        },
                        "name": "manufacturerName",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Dumpraw",
                            "type": "boolean",
                            "default": false
                        },
                        "name": "dumpRaw",
                        "in": "query"
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/LatestResponseV1"
                                }
                            }
                        }
                    },
                    "422": {
                        "description": "Validation Error",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/HTTPValidationError"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v1/locations": {
            "get": {
                "tags": [
                    "v1"
                ],
                "summary": "Get locations",
                "operationId": "locationsv1_get_v1_locations_get",
                "parameters": [
                    {
                        "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                        "required": false,
                        "schema": {
                            "title": "Limit",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                            "default": 100
                        },
                        "name": "limit",
                        "in": "query"
                    },
                    {
                        "description": "Paginate through results. e.g. page=1 will return first page of results",
                        "required": false,
                        "schema": {
                            "title": "Page",
                            "maximum": 6000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Paginate through results. e.g. page=1 will return first page of results",
                            "default": 1
                        },
                        "name": "page",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Offset",
                            "maximum": 10000.0,
                            "minimum": 0.0,
                            "type": "integer",
                            "default": 0
                        },
                        "name": "offset",
                        "in": "query"
                    },
                    {
                        "description": "Sort Direction",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/Sort"
                                }
                            ],
                            "description": "Sort Direction",
                            "default": "desc"
                        },
                        "name": "sort",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Has Geo",
                            "type": "boolean"
                        },
                        "name": "has_geo",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements",
                        "required": false,
                        "schema": {
                            "title": "Parameter Id",
                            "type": "integer",
                            "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements"
                        },
                        "name": "parameter_id",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10",
                        "required": false,
                        "schema": {
                            "title": "Parameter",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "maximum": 2147483647.0,
                                        "exclusiveMinimum": true,
                                        "minimum": 0.0,
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            },
                            "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10"
                        },
                        "name": "parameter",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Unit",
                            "type": "array",
                            "items": {
                                "type": "string"
                            }
                        },
                        "name": "unit",
                        "in": "query"
                    },
                    {
                        "description": "Coordinate pair in form lat,lng. Up to 8 decimal points of precision e.g. 38.907,-77.037",
                        "required": false,
                        "schema": {
                            "title": "Coordinates",
                            "pattern": "^-?\\d{1,2}\\.?\\d{0,8},-?1?\\d{1,2}\\.?\\d{0,8}$",
                            "type": "string",
                            "description": "Coordinate pair in form lat,lng. Up to 8 decimal points of precision e.g. 38.907,-77.037"
                        },
                        "name": "coordinates",
                        "in": "query"
                    },
                    {
                        "description": "Search radius from coordinates as center in meters. Maximum of 100,000 (100km) defaults to 1000 (1km)",
                        "required": false,
                        "schema": {
                            "title": "Radius",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Search radius from coordinates as center in meters. Maximum of 100,000 (100km) defaults to 1000 (1km)",
                            "default": 1000
                        },
                        "name": "radius",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. /US)",
                        "required": false,
                        "schema": {
                            "title": "Country Id",
                            "maxLength": 2,
                            "minLength": 2,
                            "pattern": "[a-zA-Z][a-zA-Z]",
                            "type": "string",
                            "description": "Limit results by a certain country using two letter country code. (e.g. /US)"
                        },
                        "name": "country_id",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)",
                        "required": false,
                        "schema": {
                            "title": "Country",
                            "type": "array",
                            "items": {
                                "maxLength": 2,
                                "minLength": 2,
                                "pattern": "[a-zA-Z][a-zA-Z]",
                                "type": "string"
                            },
                            "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)"
                        },
                        "name": "country",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain city or cities. (e.g. ?city=Chicago or ?city=Chicago&city=Boston)",
                        "required": false,
                        "schema": {
                            "title": "City",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Limit results by a certain city or cities. (e.g. ?city=Chicago or ?city=Chicago&city=Boston)"
                        },
                        "name": "city",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Location Id",
                            "type": "integer"
                        },
                        "name": "location_id",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Location",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            }
                        },
                        "name": "location",
                        "in": "query"
                    },
                    {
                        "description": "Order by a field",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/LocationsOrder"
                                }
                            ],
                            "description": "Order by a field",
                            "default": "lastUpdated"
                        },
                        "name": "order_by",
                        "in": "query"
                    },
                    {
                        "description": "Location is mobile",
                        "required": false,
                        "schema": {
                            "title": "Ismobile",
                            "type": "boolean",
                            "description": "Location is mobile"
                        },
                        "name": "isMobile",
                        "in": "query"
                    },
                    {
                        "description": "Data is the product of a previous analysis/aggregation and not raw measurements",
                        "required": false,
                        "schema": {
                            "title": "Isanalysis",
                            "type": "boolean",
                            "description": "Data is the product of a previous analysis/aggregation and not raw measurements"
                        },
                        "name": "isAnalysis",
                        "in": "query"
                    },
                    {
                        "description": "Name of the data source",
                        "required": false,
                        "schema": {
                            "title": "Sourcename",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Name of the data source"
                        },
                        "name": "sourceName",
                        "in": "query"
                    },
                    {
                        "description": "Source entity type.",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/EntityTypes"
                                }
                            ],
                            "description": "Source entity type."
                        },
                        "name": "entity",
                        "in": "query"
                    },
                    {
                        "description": "Type of Sensor",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/SensorTypes"
                                }
                            ],
                            "description": "Type of Sensor"
                        },
                        "name": "sensorType",
                        "in": "query"
                    },
                    {
                        "description": "Model Name of Sensor",
                        "required": false,
                        "schema": {
                            "title": "Modelname",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Model Name of Sensor"
                        },
                        "name": "modelName",
                        "in": "query"
                    },
                    {
                        "description": "Manufacturer of Sensor",
                        "required": false,
                        "schema": {
                            "title": "Manufacturername",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Manufacturer of Sensor"
                        },
                        "name": "manufacturerName",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Dumpraw",
                            "type": "boolean",
                            "default": false
                        },
                        "name": "dumpRaw",
                        "in": "query"
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/LocationsResponseV1"
                                }
                            }
                        }
                    },
                    "422": {
                        "description": "Validation Error",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/HTTPValidationError"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v1/locations/{location_id}": {
            "get": {
                "tags": [
                    "v1"
                ],
                "summary": "Get location by ID",
                "operationId": "locationsv1_get_v1_locations__location_id__get",
                "parameters": [
                    {
                        "required": true,
                        "schema": {
                            "title": "Location Id",
                            "type": "integer"
                        },
                        "name": "location_id",
                        "in": "path"
                    },
                    {
                        "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                        "required": false,
                        "schema": {
                            "title": "Limit",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                            "default": 100
                        },
                        "name": "limit",
                        "in": "query"
                    },
                    {
                        "description": "Paginate through results. e.g. page=1 will return first page of results",
                        "required": false,
                        "schema": {
                            "title": "Page",
                            "maximum": 6000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Paginate through results. e.g. page=1 will return first page of results",
                            "default": 1
                        },
                        "name": "page",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Offset",
                            "maximum": 10000.0,
                            "minimum": 0.0,
                            "type": "integer",
                            "default": 0
                        },
                        "name": "offset",
                        "in": "query"
                    },
                    {
                        "description": "Sort Direction",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/Sort"
                                }
                            ],
                            "description": "Sort Direction",
                            "default": "desc"
                        },
                        "name": "sort",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Has Geo",
                            "type": "boolean"
                        },
                        "name": "has_geo",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements",
                        "required": false,
                        "schema": {
                            "title": "Parameter Id",
                            "type": "integer",
                            "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements"
                        },
                        "name": "parameter_id",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10",
                        "required": false,
                        "schema": {
                            "title": "Parameter",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "maximum": 2147483647.0,
                                        "exclusiveMinimum": true,
                                        "minimum": 0.0,
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            },
                            "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10"
                        },
                        "name": "parameter",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Unit",
                            "type": "array",
                            "items": {
                                "type": "string"
                            }
                        },
                        "name": "unit",
                        "in": "query"
                    },
                    {
                        "description": "Coordinate pair in form lat,lng. Up to 8 decimal points of precision e.g. 38.907,-77.037",
                        "required": false,
                        "schema": {
                            "title": "Coordinates",
                            "pattern": "^-?\\d{1,2}\\.?\\d{0,8},-?1?\\d{1,2}\\.?\\d{0,8}$",
                            "type": "string",
                            "description": "Coordinate pair in form lat,lng. Up to 8 decimal points of precision e.g. 38.907,-77.037"
                        },
                        "name": "coordinates",
                        "in": "query"
                    },
                    {
                        "description": "Search radius from coordinates as center in meters. Maximum of 100,000 (100km) defaults to 1000 (1km)",
                        "required": false,
                        "schema": {
                            "title": "Radius",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Search radius from coordinates as center in meters. Maximum of 100,000 (100km) defaults to 1000 (1km)",
                            "default": 1000
                        },
                        "name": "radius",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. /US)",
                        "required": false,
                        "schema": {
                            "title": "Country Id",
                            "maxLength": 2,
                            "minLength": 2,
                            "pattern": "[a-zA-Z][a-zA-Z]",
                            "type": "string",
                            "description": "Limit results by a certain country using two letter country code. (e.g. /US)"
                        },
                        "name": "country_id",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)",
                        "required": false,
                        "schema": {
                            "title": "Country",
                            "type": "array",
                            "items": {
                                "maxLength": 2,
                                "minLength": 2,
                                "pattern": "[a-zA-Z][a-zA-Z]",
                                "type": "string"
                            },
                            "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)"
                        },
                        "name": "country",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain city or cities. (e.g. ?city=Chicago or ?city=Chicago&city=Boston)",
                        "required": false,
                        "schema": {
                            "title": "City",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Limit results by a certain city or cities. (e.g. ?city=Chicago or ?city=Chicago&city=Boston)"
                        },
                        "name": "city",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Location",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            }
                        },
                        "name": "location",
                        "in": "query"
                    },
                    {
                        "description": "Order by a field",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/LocationsOrder"
                                }
                            ],
                            "description": "Order by a field",
                            "default": "lastUpdated"
                        },
                        "name": "order_by",
                        "in": "query"
                    },
                    {
                        "description": "Location is mobile",
                        "required": false,
                        "schema": {
                            "title": "Ismobile",
                            "type": "boolean",
                            "description": "Location is mobile"
                        },
                        "name": "isMobile",
                        "in": "query"
                    },
                    {
                        "description": "Data is the product of a previous analysis/aggregation and not raw measurements",
                        "required": false,
                        "schema": {
                            "title": "Isanalysis",
                            "type": "boolean",
                            "description": "Data is the product of a previous analysis/aggregation and not raw measurements"
                        },
                        "name": "isAnalysis",
                        "in": "query"
                    },
                    {
                        "description": "Name of the data source",
                        "required": false,
                        "schema": {
                            "title": "Sourcename",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Name of the data source"
                        },
                        "name": "sourceName",
                        "in": "query"
                    },
                    {
                        "description": "Source entity type.",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/EntityTypes"
                                }
                            ],
                            "description": "Source entity type."
                        },
                        "name": "entity",
                        "in": "query"
                    },
                    {
                        "description": "Type of Sensor",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/SensorTypes"
                                }
                            ],
                            "description": "Type of Sensor"
                        },
                        "name": "sensorType",
                        "in": "query"
                    },
                    {
                        "description": "Model Name of Sensor",
                        "required": false,
                        "schema": {
                            "title": "Modelname",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Model Name of Sensor"
                        },
                        "name": "modelName",
                        "in": "query"
                    },
                    {
                        "description": "Manufacturer of Sensor",
                        "required": false,
                        "schema": {
                            "title": "Manufacturername",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Manufacturer of Sensor"
                        },
                        "name": "manufacturerName",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Dumpraw",
                            "type": "boolean",
                            "default": false
                        },
                        "name": "dumpRaw",
                        "in": "query"
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/LocationsResponseV1"
                                }
                            }
                        }
                    },
                    "422": {
                        "description": "Validation Error",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/HTTPValidationError"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v2/manufacturers": {
            "get": {
                "tags": [
                    "v2"
                ],
                "summary": "Get manufacturers",
                "description": "Provides a list of sensor manufacturers",
                "operationId": "mfr_get_v2_manufacturers_get",
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/ManufacturersResponse"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v2/models": {
            "get": {
                "tags": [
                    "v2"
                ],
                "summary": "Get models",
                "description": "Provides a list of sensor models",
                "operationId": "model_get_v2_models_get",
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/ModelsResponse"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v2/measurements": {
            "get": {
                "tags": [
                    "v2"
                ],
                "summary": "Get measurements",
                "operationId": "measurements_get_v2_measurements_get",
                "parameters": [
                    {
                        "required": false,
                        "schema": {
                            "title": "Format",
                            "type": "string"
                        },
                        "name": "format",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Date From",
                            "anyOf": [
                                {
                                    "type": "string",
                                    "format": "date-time"
                                },
                                {
                                    "type": "string",
                                    "format": "date"
                                }
                            ],
                            "default": "2000-01-01T00:00:00+00:00"
                        },
                        "name": "date_from",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Date To",
                            "anyOf": [
                                {
                                    "type": "string",
                                    "format": "date-time"
                                },
                                {
                                    "type": "string",
                                    "format": "date"
                                }
                            ],
                            "default": "2022-06-16T22:51:00+00:00"
                        },
                        "name": "date_to",
                        "in": "query"
                    },
                    {
                        "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                        "required": false,
                        "schema": {
                            "title": "Limit",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                            "default": 100
                        },
                        "name": "limit",
                        "in": "query"
                    },
                    {
                        "description": "Paginate through results. e.g. page=1 will return first page of results",
                        "required": false,
                        "schema": {
                            "title": "Page",
                            "maximum": 6000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Paginate through results. e.g. page=1 will return first page of results",
                            "default": 1
                        },
                        "name": "page",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Offset",
                            "maximum": 10000.0,
                            "minimum": 0.0,
                            "type": "integer",
                            "default": 0
                        },
                        "name": "offset",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/Sort"
                                }
                            ],
                            "default": "desc"
                        },
                        "name": "sort",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Has Geo",
                            "type": "boolean"
                        },
                        "name": "has_geo",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements",
                        "required": false,
                        "schema": {
                            "title": "Parameter Id",
                            "type": "integer",
                            "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements"
                        },
                        "name": "parameter_id",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10",
                        "required": false,
                        "schema": {
                            "title": "Parameter",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "maximum": 2147483647.0,
                                        "exclusiveMinimum": true,
                                        "minimum": 0.0,
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            },
                            "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10"
                        },
                        "name": "parameter",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Unit",
                            "type": "array",
                            "items": {
                                "type": "string"
                            }
                        },
                        "name": "unit",
                        "in": "query"
                    },
                    {
                        "description": "Coordinate pair in form lat,lng. Up to 8 decimal points of precision e.g. 38.907,-77.037",
                        "required": false,
                        "schema": {
                            "title": "Coordinates",
                            "pattern": "^-?\\d{1,2}\\.?\\d{0,8},-?1?\\d{1,2}\\.?\\d{0,8}$",
                            "type": "string",
                            "description": "Coordinate pair in form lat,lng. Up to 8 decimal points of precision e.g. 38.907,-77.037"
                        },
                        "name": "coordinates",
                        "in": "query"
                    },
                    {
                        "description": "Search radius from coordinates as center in meters. Maximum of 100,000 (100km) defaults to 1000 (1km)",
                        "required": false,
                        "schema": {
                            "title": "Radius",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Search radius from coordinates as center in meters. Maximum of 100,000 (100km) defaults to 1000 (1km)",
                            "default": 1000
                        },
                        "name": "radius",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. /US)",
                        "required": false,
                        "schema": {
                            "title": "Country Id",
                            "maxLength": 2,
                            "minLength": 2,
                            "pattern": "[a-zA-Z][a-zA-Z]",
                            "type": "string",
                            "description": "Limit results by a certain country using two letter country code. (e.g. /US)"
                        },
                        "name": "country_id",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)",
                        "required": false,
                        "schema": {
                            "title": "Country",
                            "type": "array",
                            "items": {
                                "maxLength": 2,
                                "minLength": 2,
                                "pattern": "[a-zA-Z][a-zA-Z]",
                                "type": "string"
                            },
                            "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)"
                        },
                        "name": "country",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain city or cities. (e.g. ?city=Chicago or ?city=Chicago&city=Boston)",
                        "required": false,
                        "schema": {
                            "title": "City",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Limit results by a certain city or cities. (e.g. ?city=Chicago or ?city=Chicago&city=Boston)"
                        },
                        "name": "city",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Location Id",
                            "type": "integer"
                        },
                        "name": "location_id",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Location",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            }
                        },
                        "name": "location",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/MeasOrder"
                                }
                            ],
                            "default": "datetime"
                        },
                        "name": "order_by",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Ismobile",
                            "type": "boolean"
                        },
                        "name": "isMobile",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Isanalysis",
                            "type": "boolean"
                        },
                        "name": "isAnalysis",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Project",
                            "type": "integer"
                        },
                        "name": "project",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "$ref": "#/components/schemas/EntityTypes"
                        },
                        "name": "entity",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "$ref": "#/components/schemas/SensorTypes"
                        },
                        "name": "sensorType",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Value From",
                            "type": "number"
                        },
                        "name": "value_from",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Value To",
                            "type": "number"
                        },
                        "name": "value_to",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Include Fields",
                            "type": "string"
                        },
                        "name": "include_fields",
                        "in": "query"
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/MeasurementsResponse"
                                }
                            }
                        }
                    },
                    "422": {
                        "description": "Validation Error",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/HTTPValidationError"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v1/measurements": {
            "get": {
                "tags": [
                    "v1"
                ],
                "summary": "Get a list of measurements",
                "operationId": "measurements_get_v1_v1_measurements_get",
                "parameters": [
                    {
                        "required": false,
                        "schema": {
                            "title": "Format",
                            "type": "string"
                        },
                        "name": "format",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Date From",
                            "anyOf": [
                                {
                                    "type": "string",
                                    "format": "date-time"
                                },
                                {
                                    "type": "string",
                                    "format": "date"
                                }
                            ],
                            "default": "2000-01-01T00:00:00+00:00"
                        },
                        "name": "date_from",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Date To",
                            "anyOf": [
                                {
                                    "type": "string",
                                    "format": "date-time"
                                },
                                {
                                    "type": "string",
                                    "format": "date"
                                }
                            ],
                            "default": "2022-06-16T22:51:00+00:00"
                        },
                        "name": "date_to",
                        "in": "query"
                    },
                    {
                        "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                        "required": false,
                        "schema": {
                            "title": "Limit",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                            "default": 100
                        },
                        "name": "limit",
                        "in": "query"
                    },
                    {
                        "description": "Paginate through results. e.g. page=1 will return first page of results",
                        "required": false,
                        "schema": {
                            "title": "Page",
                            "maximum": 6000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Paginate through results. e.g. page=1 will return first page of results",
                            "default": 1
                        },
                        "name": "page",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Offset",
                            "maximum": 10000.0,
                            "minimum": 0.0,
                            "type": "integer",
                            "default": 0
                        },
                        "name": "offset",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/Sort"
                                }
                            ],
                            "default": "desc"
                        },
                        "name": "sort",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Has Geo",
                            "type": "boolean"
                        },
                        "name": "has_geo",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements",
                        "required": false,
                        "schema": {
                            "title": "Parameter Id",
                            "type": "integer",
                            "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements"
                        },
                        "name": "parameter_id",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10",
                        "required": false,
                        "schema": {
                            "title": "Parameter",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "maximum": 2147483647.0,
                                        "exclusiveMinimum": true,
                                        "minimum": 0.0,
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            },
                            "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10"
                        },
                        "name": "parameter",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Unit",
                            "type": "array",
                            "items": {
                                "type": "string"
                            }
                        },
                        "name": "unit",
                        "in": "query"
                    },
                    {
                        "description": "Coordinate pair in form lat,lng. Up to 8 decimal points of precision e.g. 38.907,-77.037",
                        "required": false,
                        "schema": {
                            "title": "Coordinates",
                            "pattern": "^-?\\d{1,2}\\.?\\d{0,8},-?1?\\d{1,2}\\.?\\d{0,8}$",
                            "type": "string",
                            "description": "Coordinate pair in form lat,lng. Up to 8 decimal points of precision e.g. 38.907,-77.037"
                        },
                        "name": "coordinates",
                        "in": "query"
                    },
                    {
                        "description": "Search radius from coordinates as center in meters. Maximum of 100,000 (100km) defaults to 1000 (1km)",
                        "required": false,
                        "schema": {
                            "title": "Radius",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Search radius from coordinates as center in meters. Maximum of 100,000 (100km) defaults to 1000 (1km)",
                            "default": 1000
                        },
                        "name": "radius",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. /US)",
                        "required": false,
                        "schema": {
                            "title": "Country Id",
                            "maxLength": 2,
                            "minLength": 2,
                            "pattern": "[a-zA-Z][a-zA-Z]",
                            "type": "string",
                            "description": "Limit results by a certain country using two letter country code. (e.g. /US)"
                        },
                        "name": "country_id",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)",
                        "required": false,
                        "schema": {
                            "title": "Country",
                            "type": "array",
                            "items": {
                                "maxLength": 2,
                                "minLength": 2,
                                "pattern": "[a-zA-Z][a-zA-Z]",
                                "type": "string"
                            },
                            "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)"
                        },
                        "name": "country",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain city or cities. (e.g. ?city=Chicago or ?city=Chicago&city=Boston)",
                        "required": false,
                        "schema": {
                            "title": "City",
                            "type": "array",
                            "items": {
                                "type": "string"
                            },
                            "description": "Limit results by a certain city or cities. (e.g. ?city=Chicago or ?city=Chicago&city=Boston)"
                        },
                        "name": "city",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Location Id",
                            "type": "integer"
                        },
                        "name": "location_id",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Location",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            }
                        },
                        "name": "location",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/MeasOrder"
                                }
                            ],
                            "default": "datetime"
                        },
                        "name": "order_by",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Ismobile",
                            "type": "boolean"
                        },
                        "name": "isMobile",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Isanalysis",
                            "type": "boolean"
                        },
                        "name": "isAnalysis",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Project",
                            "type": "integer"
                        },
                        "name": "project",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "$ref": "#/components/schemas/EntityTypes"
                        },
                        "name": "entity",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "$ref": "#/components/schemas/SensorTypes"
                        },
                        "name": "sensorType",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Value From",
                            "type": "number"
                        },
                        "name": "value_from",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Value To",
                            "type": "number"
                        },
                        "name": "value_to",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Include Fields",
                            "type": "string"
                        },
                        "name": "include_fields",
                        "in": "query"
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/MeasurementsResponseV1"
                                }
                            }
                        }
                    },
                    "422": {
                        "description": "Validation Error",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/HTTPValidationError"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v2/parameters": {
            "get": {
                "tags": [
                    "v2"
                ],
                "summary": "Get parameters",
                "description": "Provides a list of parameters supported by the platform",
                "operationId": "parameters_get_v2_parameters_get",
                "parameters": [
                    {
                        "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                        "required": false,
                        "schema": {
                            "title": "Limit",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                            "default": 100
                        },
                        "name": "limit",
                        "in": "query"
                    },
                    {
                        "description": "Paginate through results. e.g. page=1 will return first page of results",
                        "required": false,
                        "schema": {
                            "title": "Page",
                            "maximum": 6000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Paginate through results. e.g. page=1 will return first page of results",
                            "default": 1
                        },
                        "name": "page",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Offset",
                            "maximum": 10000.0,
                            "minimum": 0.0,
                            "type": "integer",
                            "default": 0
                        },
                        "name": "offset",
                        "in": "query"
                    },
                    {
                        "description": "Define sort order.",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/Sort"
                                }
                            ],
                            "description": "Define sort order.",
                            "default": "asc"
                        },
                        "name": "sort",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Sourcename",
                            "type": "array",
                            "items": {
                                "type": "string"
                            }
                        },
                        "name": "sourceName",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Sourceid",
                            "type": "array",
                            "items": {
                                "type": "integer"
                            }
                        },
                        "name": "sourceId",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Sourceslug",
                            "type": "array",
                            "items": {
                                "type": "string"
                            }
                        },
                        "name": "sourceSlug",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Order By",
                            "enum": [
                                "id",
                                "name",
                                "preferredUnit"
                            ],
                            "type": "string",
                            "default": "id"
                        },
                        "name": "order_by",
                        "in": "query"
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/ParametersResponse"
                                }
                            }
                        }
                    },
                    "422": {
                        "description": "Validation Error",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/HTTPValidationError"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v1/parameters": {
            "get": {
                "tags": [
                    "v1"
                ],
                "summary": "Get parameters",
                "description": "Provides a list of parameters supported by the platform",
                "operationId": "parameters_getv1_v1_parameters_get",
                "parameters": [
                    {
                        "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                        "required": false,
                        "schema": {
                            "title": "Limit",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                            "default": 100
                        },
                        "name": "limit",
                        "in": "query"
                    },
                    {
                        "description": "Paginate through results. e.g. page=1 will return first page of results",
                        "required": false,
                        "schema": {
                            "title": "Page",
                            "maximum": 6000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Paginate through results. e.g. page=1 will return first page of results",
                            "default": 1
                        },
                        "name": "page",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Offset",
                            "maximum": 10000.0,
                            "minimum": 0.0,
                            "type": "integer",
                            "default": 0
                        },
                        "name": "offset",
                        "in": "query"
                    },
                    {
                        "description": "Define sort order.",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/Sort"
                                }
                            ],
                            "description": "Define sort order.",
                            "default": "asc"
                        },
                        "name": "sort",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Sourcename",
                            "type": "array",
                            "items": {
                                "type": "string"
                            }
                        },
                        "name": "sourceName",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Sourceid",
                            "type": "array",
                            "items": {
                                "type": "integer"
                            }
                        },
                        "name": "sourceId",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Sourceslug",
                            "type": "array",
                            "items": {
                                "type": "string"
                            }
                        },
                        "name": "sourceSlug",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Order By",
                            "enum": [
                                "id",
                                "name",
                                "preferredUnit"
                            ],
                            "type": "string",
                            "default": "id"
                        },
                        "name": "order_by",
                        "in": "query"
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/ParametersResponse"
                                }
                            }
                        }
                    },
                    "422": {
                        "description": "Validation Error",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/HTTPValidationError"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v2/projects": {
            "get": {
                "tags": [
                    "v2"
                ],
                "summary": "Projects",
                "description": "Provides a list of projects",
                "operationId": "projects_get_v2_projects_get",
                "parameters": [
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. /US)",
                        "required": false,
                        "schema": {
                            "title": "Country Id",
                            "maxLength": 2,
                            "minLength": 2,
                            "pattern": "[a-zA-Z][a-zA-Z]",
                            "type": "string",
                            "description": "Limit results by a certain country using two letter country code. (e.g. /US)"
                        },
                        "name": "country_id",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)",
                        "required": false,
                        "schema": {
                            "title": "Country",
                            "type": "array",
                            "items": {
                                "maxLength": 2,
                                "minLength": 2,
                                "pattern": "[a-zA-Z][a-zA-Z]",
                                "type": "string"
                            },
                            "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)"
                        },
                        "name": "country",
                        "in": "query"
                    },
                    {
                        "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                        "required": false,
                        "schema": {
                            "title": "Limit",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                            "default": 100
                        },
                        "name": "limit",
                        "in": "query"
                    },
                    {
                        "description": "Paginate through results. e.g. page=1 will return first page of results",
                        "required": false,
                        "schema": {
                            "title": "Page",
                            "maximum": 6000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Paginate through results. e.g. page=1 will return first page of results",
                            "default": 1
                        },
                        "name": "page",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Offset",
                            "maximum": 10000.0,
                            "minimum": 0.0,
                            "type": "integer",
                            "default": 0
                        },
                        "name": "offset",
                        "in": "query"
                    },
                    {
                        "description": "Define sort order.",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/Sort"
                                }
                            ],
                            "description": "Define sort order.",
                            "default": "asc"
                        },
                        "name": "sort",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements",
                        "required": false,
                        "schema": {
                            "title": "Parameter Id",
                            "type": "integer",
                            "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements"
                        },
                        "name": "parameter_id",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10",
                        "required": false,
                        "schema": {
                            "title": "Parameter",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "maximum": 2147483647.0,
                                        "exclusiveMinimum": true,
                                        "minimum": 0.0,
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            },
                            "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10"
                        },
                        "name": "parameter",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Unit",
                            "type": "array",
                            "items": {
                                "type": "string"
                            }
                        },
                        "name": "unit",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Project Id",
                            "type": "integer"
                        },
                        "name": "project_id",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Project",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "maximum": 2147483647.0,
                                        "exclusiveMinimum": true,
                                        "minimum": 0.0,
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            }
                        },
                        "name": "project",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/ProjectsOrder"
                                }
                            ],
                            "default": "lastUpdated"
                        },
                        "name": "order_by",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Ismobile",
                            "type": "boolean"
                        },
                        "name": "isMobile",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Isanalysis",
                            "type": "boolean"
                        },
                        "name": "isAnalysis",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Entity",
                            "type": "string"
                        },
                        "name": "entity",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Sensortype",
                            "type": "string"
                        },
                        "name": "sensorType",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Sourcename",
                            "type": "array",
                            "items": {
                                "type": "string"
                            }
                        },
                        "name": "sourceName",
                        "in": "query"
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/ProjectsResponse"
                                }
                            }
                        }
                    },
                    "422": {
                        "description": "Validation Error",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/HTTPValidationError"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v2/projects/{project_id}": {
            "get": {
                "tags": [
                    "v2"
                ],
                "summary": "Project by ID",
                "description": "Provides a project by project ID",
                "operationId": "projects_get_v2_projects__project_id__get",
                "parameters": [
                    {
                        "required": true,
                        "schema": {
                            "title": "Project Id",
                            "type": "integer"
                        },
                        "name": "project_id",
                        "in": "path"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. /US)",
                        "required": false,
                        "schema": {
                            "title": "Country Id",
                            "maxLength": 2,
                            "minLength": 2,
                            "pattern": "[a-zA-Z][a-zA-Z]",
                            "type": "string",
                            "description": "Limit results by a certain country using two letter country code. (e.g. /US)"
                        },
                        "name": "country_id",
                        "in": "query"
                    },
                    {
                        "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)",
                        "required": false,
                        "schema": {
                            "title": "Country",
                            "type": "array",
                            "items": {
                                "maxLength": 2,
                                "minLength": 2,
                                "pattern": "[a-zA-Z][a-zA-Z]",
                                "type": "string"
                            },
                            "description": "Limit results by a certain country using two letter country code. (e.g. ?country=US or ?country=US&country=MX)"
                        },
                        "name": "country",
                        "in": "query"
                    },
                    {
                        "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                        "required": false,
                        "schema": {
                            "title": "Limit",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                            "default": 100
                        },
                        "name": "limit",
                        "in": "query"
                    },
                    {
                        "description": "Paginate through results. e.g. page=1 will return first page of results",
                        "required": false,
                        "schema": {
                            "title": "Page",
                            "maximum": 6000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Paginate through results. e.g. page=1 will return first page of results",
                            "default": 1
                        },
                        "name": "page",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Offset",
                            "maximum": 10000.0,
                            "minimum": 0.0,
                            "type": "integer",
                            "default": 0
                        },
                        "name": "offset",
                        "in": "query"
                    },
                    {
                        "description": "Define sort order.",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/Sort"
                                }
                            ],
                            "description": "Define sort order.",
                            "default": "asc"
                        },
                        "name": "sort",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements",
                        "required": false,
                        "schema": {
                            "title": "Parameter Id",
                            "type": "integer",
                            "description": "(optional) A parameter ID to filter measurement results. e.g. parameter_id=2 parameter ID 2 (i.e. PM2.5) will limit measurement results to only PM2.5 measurements"
                        },
                        "name": "parameter_id",
                        "in": "query"
                    },
                    {
                        "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10",
                        "required": false,
                        "schema": {
                            "title": "Parameter",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "maximum": 2147483647.0,
                                        "exclusiveMinimum": true,
                                        "minimum": 0.0,
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            },
                            "description": "(optional) A parameter name or ID by which to filter measurement results. e.g. parameter=pm25 or parameter=pm25&parameter=pm10"
                        },
                        "name": "parameter",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Unit",
                            "type": "array",
                            "items": {
                                "type": "string"
                            }
                        },
                        "name": "unit",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Project",
                            "type": "array",
                            "items": {
                                "anyOf": [
                                    {
                                        "maximum": 2147483647.0,
                                        "exclusiveMinimum": true,
                                        "minimum": 0.0,
                                        "type": "integer"
                                    },
                                    {
                                        "type": "string"
                                    }
                                ]
                            }
                        },
                        "name": "project",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/ProjectsOrder"
                                }
                            ],
                            "default": "lastUpdated"
                        },
                        "name": "order_by",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Ismobile",
                            "type": "boolean"
                        },
                        "name": "isMobile",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Isanalysis",
                            "type": "boolean"
                        },
                        "name": "isAnalysis",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Entity",
                            "type": "string"
                        },
                        "name": "entity",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Sensortype",
                            "type": "string"
                        },
                        "name": "sensorType",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Sourcename",
                            "type": "array",
                            "items": {
                                "type": "string"
                            }
                        },
                        "name": "sourceName",
                        "in": "query"
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/ProjectsResponse"
                                }
                            }
                        }
                    },
                    "422": {
                        "description": "Validation Error",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/HTTPValidationError"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v2/sources": {
            "get": {
                "tags": [
                    "v2"
                ],
                "summary": "Sources",
                "description": "Provides a list of sources",
                "operationId": "sources_get_v2_sources_get",
                "parameters": [
                    {
                        "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                        "required": false,
                        "schema": {
                            "title": "Limit",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                            "default": 100
                        },
                        "name": "limit",
                        "in": "query"
                    },
                    {
                        "description": "Paginate through results. e.g. page=1 will return first page of results",
                        "required": false,
                        "schema": {
                            "title": "Page",
                            "maximum": 6000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Paginate through results. e.g. page=1 will return first page of results",
                            "default": 1
                        },
                        "name": "page",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Offset",
                            "maximum": 10000.0,
                            "minimum": 0.0,
                            "type": "integer",
                            "default": 0
                        },
                        "name": "offset",
                        "in": "query"
                    },
                    {
                        "description": "Define sort order.",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/Sort"
                                }
                            ],
                            "description": "Define sort order.",
                            "default": "asc"
                        },
                        "name": "sort",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Sourcename",
                            "type": "array",
                            "items": {
                                "type": "string"
                            }
                        },
                        "name": "sourceName",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Sourceid",
                            "type": "array",
                            "items": {
                                "type": "integer"
                            }
                        },
                        "name": "sourceId",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Sourceslug",
                            "type": "array",
                            "items": {
                                "type": "string"
                            }
                        },
                        "name": "sourceSlug",
                        "in": "query"
                    },
                    {
                        "description": "Field by which to order the results",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/SourcesOrder"
                                }
                            ],
                            "description": "Field by which to order the results",
                            "default": "sourceName"
                        },
                        "name": "order_by",
                        "in": "query"
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/SourcesResponse"
                                }
                            }
                        }
                    },
                    "422": {
                        "description": "Validation Error",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/HTTPValidationError"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v1/sources": {
            "get": {
                "tags": [
                    "v1"
                ],
                "summary": "Sources",
                "description": "Provides a list of sources",
                "operationId": "sources_v1_get_v1_sources_get",
                "parameters": [
                    {
                        "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                        "required": false,
                        "schema": {
                            "title": "Limit",
                            "maximum": 100000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Change the number of results returned. e.g. limit=1000 will return up to 1000 results",
                            "default": 100
                        },
                        "name": "limit",
                        "in": "query"
                    },
                    {
                        "description": "Paginate through results. e.g. page=1 will return first page of results",
                        "required": false,
                        "schema": {
                            "title": "Page",
                            "maximum": 6000.0,
                            "exclusiveMinimum": true,
                            "minimum": 0.0,
                            "type": "integer",
                            "description": "Paginate through results. e.g. page=1 will return first page of results",
                            "default": 1
                        },
                        "name": "page",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Offset",
                            "maximum": 10000.0,
                            "minimum": 0.0,
                            "type": "integer",
                            "default": 0
                        },
                        "name": "offset",
                        "in": "query"
                    },
                    {
                        "description": "Define sort order.",
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/Sort"
                                }
                            ],
                            "description": "Define sort order.",
                            "default": "asc"
                        },
                        "name": "sort",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "title": "Name",
                            "type": "string"
                        },
                        "name": "name",
                        "in": "query"
                    },
                    {
                        "required": false,
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/components/schemas/SourcesV1Order"
                                }
                            ],
                            "default": "name"
                        },
                        "name": "order_by",
                        "in": "query"
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/SourcesResponseV1"
                                }
                            }
                        }
                    },
                    "422": {
                        "description": "Validation Error",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/HTTPValidationError"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v2/sources/readme/{slug}": {
            "get": {
                "tags": [
                    "v2"
                ],
                "summary": "Source Readme",
                "description": "Provides a readme for a given source by the source slug",
                "operationId": "readme_get_v2_sources_readme__slug__get",
                "parameters": [
                    {
                        "required": true,
                        "schema": {
                            "title": "Slug",
                            "type": "string"
                        },
                        "name": "slug",
                        "in": "path"
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "text/html": {
                                "schema": {
                                    "type": "string"
                                }
                            }
                        }
                    },
                    "422": {
                        "description": "Validation Error",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/HTTPValidationError"
                                }
                            }
                        }
                    }
                }
            }
        },
        "/v2/summary": {
            "get": {
                "tags": [
                    "v2"
                ],
                "summary": "Platform Summary",
                "description": "Provides a summary of platform data",
                "operationId": "summary_get_v2_summary_get",
                "responses": {
                    "200": {
                        "description": "Successful Response",
                        "content": {
                            "application/json": {
                                "schema": {
                                    "$ref": "#/components/schemas/SummaryResponse"
                                }
                            }
                        }
                    }
                }
            }
        }
    },
    "components": {
        "schemas": {
            "AveragesResponse": {
                "title": "AveragesResponse",
                "required": [
                    "results"
                ],
                "type": "object",
                "properties": {
                    "meta": {
                        "title": "Meta",
                        "allOf": [
                            {
                                "$ref": "#/components/schemas/Meta"
                            }
                        ],
                        "default": {
                            "name": "openaq-api",
                            "license": "CC BY 4.0d",
                            "website": "/",
                            "page": 1,
                            "limit": 100,
                            "found": 0
                        }
                    },
                    "results": {
                        "title": "Results",
                        "type": "array",
                        "items": {
                            "$ref": "#/components/schemas/AveragesRow"
                        }
                    }
                }
            },
            "AveragesRow": {
                "title": "AveragesRow",
                "required": [
                    "id",
                    "name",
                    "average",
                    "subtitle",
                    "measurement_count",
                    "parameter",
                    "parameterId",
                    "displayName"
                ],
                "type": "object",
                "properties": {
                    "id": {
                        "title": "Id",
                        "type": "integer"
                    },
                    "hour": {
                        "title": "Hour",
                        "type": "string",
                        "format": "date-time"
                    },
                    "day": {
                        "title": "Day",
                        "type": "string",
                        "format": "date-time"
                    },
                    "month": {
                        "title": "Month",
                        "type": "string",
                        "format": "date"
                    },
                    "year": {
                        "title": "Year",
                        "type": "string",
                        "format": "date"
                    },
                    "hod": {
                        "title": "Hod",
                        "type": "integer"
                    },
                    "dom": {
                        "title": "Dom",
                        "type": "integer"
                    },
                    "name": {
                        "title": "Name",
                        "type": "string"
                    },
                    "average": {
                        "title": "Average",
                        "type": "number"
                    },
                    "subtitle": {
                        "title": "Subtitle",
                        "type": "string"
                    },
                    "measurement_count": {
                        "title": "Measurement Count",
                        "type": "integer"
                    },
                    "parameter": {
                        "title": "Parameter",
                        "type": "string"
                    },
                    "parameterId": {
                        "title": "Parameterid",
                        "type": "integer"
                    },
                    "displayName": {
                        "title": "Displayname",
                        "type": "string"
                    },
                    "unit": {
                        "title": "Unit",
                        "type": "string"
                    }
                }
            },
            "AveragingPeriodV1": {
                "title": "AveragingPeriodV1",
                "required": [
                    "value",
                    "unit"
                ],
                "type": "object",
                "properties": {
                    "value": {
                        "title": "Value",
                        "type": "integer"
                    },
                    "unit": {
                        "title": "Unit",
                        "type": "string"
                    }
                }
            },
            "CitiesOrder": {
                "title": "CitiesOrder",
                "enum": [
                    "city",
                    "country",
                    "firstUpdated",
                    "lastUpdated"
                ],
                "type": "string",
                "description": "An enumeration."
            },
            "CitiesResponse": {
                "title": "CitiesResponse",
                "required": [
                    "results"
                ],
                "type": "object",
                "properties": {
                    "meta": {
                        "title": "Meta",
                        "allOf": [
                            {
                                "$ref": "#/components/schemas/Meta"
                            }
                        ],
                        "default": {
                            "name": "openaq-api",
                            "license": "CC BY 4.0d",
                            "website": "/",
                            "page": 1,
                            "limit": 100,
                            "found": 0
                        }
                    },
                    "results": {
                        "title": "Results",
                        "type": "array",
                        "items": {
                            "$ref": "#/components/schemas/CityRow"
                        }
                    }
                }
            },
            "CityRow": {
                "title": "CityRow",
                "required": [
                    "country",
                    "city",
                    "count",
                    "locations",
                    "firstUpdated",
                    "lastUpdated",
                    "parameters"
                ],
                "type": "object",
                "properties": {
                    "country": {
                        "title": "Country",
                        "type": "string"
                    },
                    "city": {
                        "title": "City",
                        "type": "string"
                    },
                    "count": {
                        "title": "Count",
                        "type": "integer"
                    },
                    "locations": {
                        "title": "Locations",
                        "type": "integer"
                    },
                    "firstUpdated": {
                        "title": "Firstupdated",
                        "type": "string"
                    },
                    "lastUpdated": {
                        "title": "Lastupdated",
                        "type": "string"
                    },
                    "parameters": {
                        "title": "Parameters",
                        "type": "array",
                        "items": {
                            "type": "string"
                        }
                    }
                }
            },
            "Coordinates": {
                "title": "Coordinates",
                "required": [
                    "latitude",
                    "longitude"
                ],
                "type": "object",
                "properties": {
                    "latitude": {
                        "title": "Latitude",
                        "type": "number"
                    },
                    "longitude": {
                        "title": "Longitude",
                        "type": "number"
                    }
                }
            },
            "CountriesOrder": {
                "title": "CountriesOrder",
                "enum": [
                    "country",
                    "firstUpdated",
                    "lastUpdated",
                    "locations",
                    "count"
                ],
                "type": "string",
                "description": "An enumeration."
            },
            "CountriesResponse": {
                "title": "CountriesResponse",
                "required": [
                    "results"
                ],
                "type": "object",
                "properties": {
                    "meta": {
                        "title": "Meta",
                        "allOf": [
                            {
                                "$ref": "#/components/schemas/Meta"
                            }
                        ],
                        "default": {
                            "name": "openaq-api",
                            "license": "CC BY 4.0d",
                            "website": "/",
                            "page": 1,
                            "limit": 100,
                            "found": 0
                        }
                    },
                    "results": {
                        "title": "Results",
                        "type": "array",
                        "items": {
                            "$ref": "#/components/schemas/CountriesRow"
                        }
                    }
                }
            },
            "CountriesRow": {
                "title": "CountriesRow",
                "required": [
                    "code",
                    "name",
                    "locations",
                    "firstUpdated",
                    "lastUpdated",
                    "parameters",
                    "count",
                    "cities",
                    "sources"
                ],
                "type": "object",
                "properties": {
                    "code": {
                        "title": "Code",
                        "type": "string"
                    },
                    "name": {
                        "title": "Name",
                        "type": "string"
                    },
                    "locations": {
                        "title": "Locations",
                        "type": "integer"
                    },
                    "firstUpdated": {
                        "title": "Firstupdated",
                        "type": "string"
                    },
                    "lastUpdated": {
                        "title": "Lastupdated",
                        "type": "string"
                    },
                    "parameters": {
                        "title": "Parameters",
                        "type": "array",
                        "items": {
                            "type": "string"
                        }
                    },
                    "count": {
                        "title": "Count",
                        "type": "integer"
                    },
                    "cities": {
                        "title": "Cities",
                        "type": "integer"
                    },
                    "sources": {
                        "title": "Sources",
                        "type": "integer"
                    }
                }
            },
            "CountsByMeasurementItem": {
                "title": "CountsByMeasurementItem",
                "required": [
                    "parameter",
                    "count"
                ],
                "type": "object",
                "properties": {
                    "parameter": {
                        "title": "Parameter",
                        "type": "string"
                    },
                    "count": {
                        "title": "Count",
                        "type": "integer"
                    }
                }
            },
            "Date": {
                "title": "Date",
                "required": [
                    "utc",
                    "local"
                ],
                "type": "object",
                "properties": {
                    "utc": {
                        "title": "Utc",
                        "type": "string"
                    },
                    "local": {
                        "title": "Local",
                        "type": "string"
                    }
                }
            },
            "Datum": {
                "title": "Datum",
                "type": "object",
                "properties": {
                    "url": {
                        "title": "Url",
                        "type": "string"
                    },
                    "data_avg_dur": {
                        "title": "Data Avg Dur",
                        "type": "string"
                    },
                    "organization": {
                        "title": "Organization",
                        "type": "string"
                    },
                    "lifecycle_stage": {
                        "title": "Lifecycle Stage",
                        "type": "string"
                    }
                }
            },
            "EntityTypes": {
                "title": "EntityTypes",
                "enum": [
                    "government",
                    "community",
                    "research"
                ],
                "type": "string",
                "description": "An enumeration."
            },
            "HTTPValidationError": {
                "title": "HTTPValidationError",
                "type": "object",
                "properties": {
                    "detail": {
                        "title": "Detail",
                        "type": "array",
                        "items": {
                            "$ref": "#/components/schemas/ValidationError"
                        }
                    }
                }
            },
            "LatestMeasurement": {
                "title": "LatestMeasurement",
                "required": [
                    "parameter",
                    "value",
                    "lastUpdated",
                    "unit"
                ],
                "type": "object",
                "properties": {
                    "parameter": {
                        "title": "Parameter",
                        "type": "string"
                    },
                    "value": {
                        "title": "Value",
                        "type": "number"
                    },
                    "lastUpdated": {
                        "title": "Lastupdated",
                        "type": "string"
                    },
                    "unit": {
                        "title": "Unit",
                        "type": "string"
                    }
                }
            },
            "LatestMeasurementRow": {
                "title": "LatestMeasurementRow",
                "required": [
                    "parameter",
                    "value",
                    "lastUpdated",
                    "unit",
                    "sourceName",
                    "averagingPeriod"
                ],
                "type": "object",
                "properties": {
                    "parameter": {
                        "title": "Parameter",
                        "type": "string"
                    },
                    "value": {
                        "title": "Value",
                        "type": "number"
                    },
                    "lastUpdated": {
                        "title": "Lastupdated",
                        "type": "string"
                    },
                    "unit": {
                        "title": "Unit",
                        "type": "string"
                    },
                    "sourceName": {
                        "title": "Sourcename",
                        "type": "string"
                    },
                    "averagingPeriod": {
                        "$ref": "#/components/schemas/AveragingPeriodV1"
                    }
                }
            },
            "LatestResponse": {
                "title": "LatestResponse",
                "required": [
                    "results"
                ],
                "type": "object",
                "properties": {
                    "meta": {
                        "title": "Meta",
                        "allOf": [
                            {
                                "$ref": "#/components/schemas/Meta"
                            }
                        ],
                        "default": {
                            "name": "openaq-api",
                            "license": "CC BY 4.0d",
                            "website": "/",
                            "page": 1,
                            "limit": 100,
                            "found": 0
                        }
                    },
                    "results": {
                        "title": "Results",
                        "type": "array",
                        "items": {
                            "$ref": "#/components/schemas/LatestRow"
                        }
                    }
                }
            },
            "LatestResponseV1": {
                "title": "LatestResponseV1",
                "required": [
                    "results"
                ],
                "type": "object",
                "properties": {
                    "meta": {
                        "title": "Meta",
                        "allOf": [
                            {
                                "$ref": "#/components/schemas/Meta"
                            }
                        ],
                        "default": {
                            "name": "openaq-api",
                            "license": "CC BY 4.0d",
                            "website": "/",
                            "page": 1,
                            "limit": 100,
                            "found": 0
                        }
                    },
                    "results": {
                        "title": "Results",
                        "type": "array",
                        "items": {
                            "$ref": "#/components/schemas/LatestRowV1"
                        }
                    }
                }
            },
            "LatestRow": {
                "title": "LatestRow",
                "required": [
                    "location",
                    "city",
                    "country",
                    "measurements"
                ],
                "type": "object",
                "properties": {
                    "location": {
                        "title": "Location",
                        "type": "string"
                    },
                    "city": {
                        "title": "City",
                        "type": "string"
                    },
                    "country": {
                        "title": "Country",
                        "type": "string"
                    },
                    "coordinates": {
                        "$ref": "#/components/schemas/Coordinates"
                    },
                    "measurements": {
                        "title": "Measurements",
                        "type": "array",
                        "items": {
                            "$ref": "#/components/schemas/LatestMeasurement"
                        }
                    }
                }
            },
            "LatestRowV1": {
                "title": "LatestRowV1",
                "required": [
                    "location",
                    "city",
                    "country",
                    "coordinates",
                    "measurements"
                ],
                "type": "object",
                "properties": {
                    "location": {
                        "title": "Location",
                        "type": "string"
                    },
                    "city": {
                        "title": "City",
                        "type": "string"
                    },
                    "country": {
                        "title": "Country",
                        "type": "string"
                    },
                    "coordinates": {
                        "$ref": "#/components/schemas/Coordinates"
                    },
                    "measurements": {
                        "title": "Measurements",
                        "type": "array",
                        "items": {
                            "$ref": "#/components/schemas/LatestMeasurementRow"
                        }
                    }
                }
            },
            "LocationsOrder": {
                "title": "LocationsOrder",
                "enum": [
                    "city",
                    "country",
                    "location",
                    "sourceName",
                    "firstUpdated",
                    "lastUpdated",
                    "count",
                    "random"
                ],
                "type": "string",
                "description": "An enumeration."
            },
            "LocationsResponse": {
                "title": "LocationsResponse",
                "required": [
                    "results"
                ],
                "type": "object",
                "properties": {
                    "meta": {
                        "title": "Meta",
                        "allOf": [
                            {
                                "$ref": "#/components/schemas/Meta"
                            }
                        ],
                        "default": {
                            "name": "openaq-api",
                            "license": "CC BY 4.0d",
                            "website": "/",
                            "page": 1,
                            "limit": 100,
                            "found": 0
                        }
                    },
                    "results": {
                        "title": "Results",
                        "type": "array",
                        "items": {
                            "$ref": "#/components/schemas/LocationsRow"
                        }
                    }
                }
            },
            "LocationsResponseV1": {
                "title": "LocationsResponseV1",
                "required": [
                    "results"
                ],
                "type": "object",
                "properties": {
                    "meta": {
                        "title": "Meta",
                        "allOf": [
                            {
                                "$ref": "#/components/schemas/Meta"
                            }
                        ],
                        "default": {
                            "name": "openaq-api",
                            "license": "CC BY 4.0d",
                            "website": "/",
                            "page": 1,
                            "limit": 100,
                            "found": 0
                        }
                    },
                    "results": {
                        "title": "Results",
                        "type": "array",
                        "items": {
                            "$ref": "#/components/schemas/LocationsRowV1"
                        }
                    }
                }
            },
            "LocationsRow": {
                "title": "LocationsRow",
                "required": [
                    "id",
                    "city",
                    "name",
                    "entity",
                    "country",
                    "isMobile",
                    "isAnalysis",
                    "parameters",
                    "sensorType",
                    "lastUpdated",
                    "firstUpdated",
                    "measurements"
                ],
                "type": "object",
                "properties": {
                    "id": {
                        "title": "Id",
                        "type": "integer"
                    },
                    "city": {
                        "title": "City",
                        "type": "string"
                    },
                    "name": {
                        "title": "Name",
                        "type": "string"
                    },
                    "entity": {
                        "title": "Entity",
                        "type": "string"
                    },
                    "country": {
                        "title": "Country",
                        "type": "string"
                    },
                    "sources": {
                        "title": "Sources",
                        "type": "array",
                        "items": {
                            "$ref": "#/components/schemas/Source"
                        }
                    },
                    "isMobile": {
                        "title": "Ismobile",
                        "type": "boolean"
                    },
                    "isAnalysis": {
                        "title": "Isanalysis",
                        "type": "boolean"
                    },
                    "parameters": {
                        "title": "Parameters",
                        "type": "array",
                        "items": {
                            "$ref": "#/components/schemas/Parameter"
                        }
                    },
                    "sensorType": {
                        "title": "Sensortype",
                        "type": "string"
                    },
                    "coordinates": {
                        "$ref": "#/components/schemas/Coordinates"
                    },
                    "lastUpdated": {
                        "title": "Lastupdated",
                        "type": "string"
                    },
                    "firstUpdated": {
                        "title": "Firstupdated",
                        "type": "string"
                    },
                    "measurements": {
                        "title": "Measurements",
                        "type": "integer"
                    },
                    "bounds": {
                        "title": "Bounds",
                        "type": "array",
                        "items": {
                            "type": "number"
                        }
                    },
                    "manufacturers": {
                        "title": "Manufacturers",
                        "type": "array",
                        "items": {
                            "$ref": "#/components/schemas/Manufacturer"
                        }
                    }
                }
            },
            "LocationsRowV1": {
                "title": "LocationsRowV1",
                "required": [
                    "id",
                    "country",
                    "city",
                    "cities",
                    "location",
                    "locations",
                    "sourceName",
                    "sourceNames",
                    "sourceType",
                    "sourceTypes",
                    "coordinates",
                    "firstUpdated",
                    "lastUpdated",
                    "parameters",
                    "countsByMeasurement",
                    "count"
                ],
                "type": "object",
                "properties": {
                    "id": {
                        "title": "Id",
                        "type": "integer"
                    },
                    "country": {
                        "title": "Country",
                        "type": "string"
                    },
                    "city": {
                        "title": "City",
                        "type": "string"
                    },
                    "cities": {
                        "title": "Cities",
                        "type": "array",
                        "items": {
                            "type": "string"
                        }
                    },
                    "location": {
                        "title": "Location",
                        "type": "string"
                    },
                    "locations": {
                        "title": "Locations",
                        "type": "array",
                        "items": {
                            "type": "string"
                        }
                    },
                    "sourceName": {
                        "title": "Sourcename",
                        "type": "string"
                    },
                    "sourceNames": {
                        "title": "Sourcenames",
                        "type": "array",
                        "items": {
                            "type": "string"
                        }
                    },
                    "sourceType": {
                        "title": "Sourcetype",
                        "type": "string"
                    },
                    "sourceTypes": {
                        "title": "Sourcetypes",
                        "type": "array",
                        "items": {
                            "type": "string"
                        }
                    },
                    "coordinates": {
                        "$ref": "#/components/schemas/Coordinates"
                    },
                    "firstUpdated": {
                        "title": "Firstupdated",
                        "type": "string"
                    },
                    "lastUpdated": {
                        "title": "Lastupdated",
                        "type": "string"
                    },
                    "parameters": {
                        "title": "Parameters",
                        "type": "array",
                        "items": {
                            "type": "string"
                        }
                    },
                    "countsByMeasurement": {
                        "title": "Countsbymeasurement",
                        "type": "array",
                        "items": {
                            "$ref": "#/components/schemas/CountsByMeasurementItem"
                        }
                    },
                    "count": {
                        "title": "Count",
                        "type": "integer"
                    }
                }
            },
            "Manufacturer": {
                "title": "Manufacturer",
                "required": [
                    "modelName",
                    "manufacturerName"
                ],
                "type": "object",
                "properties": {
                    "modelName": {
                        "title": "Modelname",
                        "type": "string"
                    },
                    "manufacturerName": {
                        "title": "Manufacturername",
                        "type": "string"
                    }
                }
            },
            "ManufacturersResponse": {
                "title": "ManufacturersResponse",
                "required": [
                    "results"
                ],
                "type": "object",
                "properties": {
                    "meta": {
                        "title": "Meta",
                        "allOf": [
                            {
                                "$ref": "#/components/schemas/Meta"
                            }
                        ],
                        "default": {
                            "name": "openaq-api",
                            "license": "CC BY 4.0d",
                            "website": "/",
                            "page": 1,
                            "limit": 100,
                            "found": 0
                        }
                    },
                    "results": {
                        "title": "Results",
                        "type": "array",
                        "items": {
                            "type": "string"
                        }
                    }
                }
            },
            "MeasOrder": {
                "title": "MeasOrder",
                "enum": [
                    "city",
                    "country",
                    "location",
                    "datetime"
                ],
                "type": "string",
                "description": "An enumeration."
            },
            "MeasurementsResponse": {
                "title": "MeasurementsResponse",
                "required": [
                    "results"
                ],
                "type": "object",
                "properties": {
                    "meta": {
                        "title": "Meta",
                        "allOf": [
                            {
                                "$ref": "#/components/schemas/Meta"
                            }
                        ],
                        "default": {
                            "name": "openaq-api",
                            "license": "CC BY 4.0d",
                            "website": "/",
                            "page": 1,
                            "limit": 100,
                            "found": 0
                        }
                    },
                    "results": {
                        "title": "Results",
                        "type": "array",
                        "items": {
                            "$ref": "#/components/schemas/MeasurementsRow"
                        }
                    }
                }
            },
            "MeasurementsResponseV1": {
                "title": "MeasurementsResponseV1",
                "required": [
                    "results"
                ],
                "type": "object",
                "properties": {
                    "meta": {
                        "title": "Meta",
                        "allOf": [
                            {
                                "$ref": "#/components/schemas/Meta"
                            }
                        ],
                        "default": {
                            "name": "openaq-api",
                            "license": "CC BY 4.0d",
                            "website": "/",
                            "page": 1,
                            "limit": 100,
                            "found": 0
                        }
                    },
                    "results": {
                        "title": "Results",
                        "type": "array",
                        "items": {
                            "$ref": "#/components/schemas/MeasurementsRowV1"
                        }
                    }
                }
            },
            "MeasurementsRow": {
                "title": "MeasurementsRow",
                "required": [
                    "locationId",
                    "location",
                    "parameter",
                    "value",
                    "date",
                    "unit",
                    "coordinates",
                    "country",
                    "isMobile",
                    "isAnalysis",
                    "entity",
                    "sensorType"
                ],
                "type": "object",
                "properties": {
                    "locationId": {
                        "title": "Locationid",
                        "type": "integer"
                    },
                    "location": {
                        "title": "Location",
                        "type": "string"
                    },
                    "parameter": {
                        "title": "Parameter",
                        "type": "string"
                    },
                    "value": {
                        "title": "Value",
                        "type": "number"
                    },
                    "date": {
                        "$ref": "#/components/schemas/Date"
                    },
                    "unit": {
                        "title": "Unit",
                        "type": "string"
                    },
                    "coordinates": {
                        "$ref": "#/components/schemas/Coordinates"
                    },
                    "country": {
                        "title": "Country",
                        "type": "string"
                    },
                    "city": {
                        "title": "City",
                        "type": "string"
                    },
                    "isMobile": {
                        "title": "Ismobile",
                        "type": "boolean"
                    },
                    "isAnalysis": {
                        "title": "Isanalysis",
                        "type": "boolean"
                    },
                    "entity": {
                        "title": "Entity",
                        "type": "string"
                    },
                    "sensorType": {
                        "title": "Sensortype",
                        "type": "string"
                    }
                }
            },
            "MeasurementsRowV1": {
                "title": "MeasurementsRowV1",
                "required": [
                    "location",
                    "parameter",
                    "value",
                    "date",
                    "unit",
                    "coordinates",
                    "country",
                    "city"
                ],
                "type": "object",
                "properties": {
                    "location": {
                        "title": "Location",
                        "type": "string"
                    },
                    "parameter": {
                        "title": "Parameter",
                        "type": "string"
                    },
                    "value": {
                        "title": "Value",
                        "type": "number"
                    },
                    "date": {
                        "$ref": "#/components/schemas/Date"
                    },
                    "unit": {
                        "title": "Unit",
                        "type": "string"
                    },
                    "coordinates": {
                        "$ref": "#/components/schemas/Coordinates"
                    },
                    "country": {
                        "title": "Country",
                        "type": "string"
                    },
                    "city": {
                        "title": "City",
                        "type": "string"
                    }
                }
            },
            "Meta": {
                "title": "Meta",
                "type": "object",
                "properties": {
                    "name": {
                        "title": "Name",
                        "type": "string",
                        "default": "openaq-api"
                    },
                    "license": {
                        "title": "License",
                        "type": "string",
                        "default": "CC BY 4.0d"
                    },
                    "website": {
                        "title": "Website",
                        "type": "string",
                        "default": "/"
                    },
                    "page": {
                        "title": "Page",
                        "type": "integer",
                        "default": 1
                    },
                    "limit": {
                        "title": "Limit",
                        "type": "integer",
                        "default": 100
                    },
                    "found": {
                        "title": "Found",
                        "type": "integer",
                        "default": 0
                    }
                }
            },
            "ModelsResponse": {
                "title": "ModelsResponse",
                "required": [
                    "results"
                ],
                "type": "object",
                "properties": {
                    "meta": {
                        "title": "Meta",
                        "allOf": [
                            {
                                "$ref": "#/components/schemas/Meta"
                            }
                        ],
                        "default": {
                            "name": "openaq-api",
                            "license": "CC BY 4.0d",
                            "website": "/",
                            "page": 1,
                            "limit": 100,
                            "found": 0
                        }
                    },
                    "results": {
                        "title": "Results",
                        "type": "array",
                        "items": {
                            "type": "string"
                        }
                    }
                }
            },
            "Parameter": {
                "title": "Parameter",
                "required": [
                    "id",
                    "unit",
                    "count",
                    "average",
                    "lastValue",
                    "parameter",
                    "displayName",
                    "lastUpdated",
                    "parameterId",
                    "firstUpdated"
                ],
                "type": "object",
                "properties": {
                    "id": {
                        "title": "Id",
                        "type": "integer"
                    },
                    "unit": {
                        "title": "Unit",
                        "type": "string"
                    },
                    "count": {
                        "title": "Count",
                        "type": "integer"
                    },
                    "average": {
                        "title": "Average",
                        "type": "number"
                    },
                    "lastValue": {
                        "title": "Lastvalue",
                        "type": "number"
                    },
                    "parameter": {
                        "title": "Parameter",
                        "type": "string"
                    },
                    "displayName": {
                        "title": "Displayname",
                        "type": "string"
                    },
                    "lastUpdated": {
                        "title": "Lastupdated",
                        "type": "string"
                    },
                    "parameterId": {
                        "title": "Parameterid",
                        "type": "integer"
                    },
                    "firstUpdated": {
                        "title": "Firstupdated",
                        "type": "string"
                    },
                    "manufacturers": {
                        "title": "Manufacturers",
                        "type": "array",
                        "items": {
                            "$ref": "#/components/schemas/Manufacturer"
                        }
                    }
                }
            },
            "ParametersResponse": {
                "title": "ParametersResponse",
                "required": [
                    "results"
                ],
                "type": "object",
                "properties": {
                    "meta": {
                        "title": "Meta",
                        "allOf": [
                            {
                                "$ref": "#/components/schemas/Meta"
                            }
                        ],
                        "default": {
                            "name": "openaq-api",
                            "license": "CC BY 4.0d",
                            "website": "/",
                            "page": 1,
                            "limit": 100,
                            "found": 0
                        }
                    },
                    "results": {
                        "title": "Results",
                        "type": "array",
                        "items": {
                            "$ref": "#/components/schemas/ParametersRow"
                        }
                    }
                }
            },
            "ParametersRow": {
                "title": "ParametersRow",
                "required": [
                    "id",
                    "name",
                    "displayName",
                    "description",
                    "preferredUnit",
                    "isCore"
                ],
                "type": "object",
                "properties": {
                    "id": {
                        "title": "Id",
                        "type": "integer"
                    },
                    "name": {
                        "title": "Name",
                        "type": "string"
                    },
                    "displayName": {
                        "title": "Displayname",
                        "type": "string"
                    },
                    "description": {
                        "title": "Description",
                        "type": "string"
                    },
                    "preferredUnit": {
                        "title": "Preferredunit",
                        "type": "string"
                    },
                    "isCore": {
                        "title": "Iscore",
                        "type": "boolean"
                    },
                    "max_color_value": {
                        "title": "Max Color Value",
                        "type": "number"
                    }
                }
            },
            "ProjectsOrder": {
                "title": "ProjectsOrder",
                "enum": [
                    "id",
                    "name",
                    "subtitle",
                    "firstUpdated",
                    "lastUpdated"
                ],
                "type": "string",
                "description": "An enumeration."
            },
            "ProjectsResponse": {
                "title": "ProjectsResponse",
                "required": [
                    "results"
                ],
                "type": "object",
                "properties": {
                    "meta": {
                        "title": "Meta",
                        "allOf": [
                            {
                                "$ref": "#/components/schemas/Meta"
                            }
                        ],
                        "default": {
                            "name": "openaq-api",
                            "license": "CC BY 4.0d",
                            "website": "/",
                            "page": 1,
                            "limit": 100,
                            "found": 0
                        }
                    },
                    "results": {
                        "title": "Results",
                        "type": "array",
                        "items": {
                            "$ref": "#/components/schemas/ProjectsRow"
                        }
                    }
                }
            },
            "ProjectsRow": {
                "title": "ProjectsRow",
                "required": [
                    "id",
                    "name",
                    "subtitle",
                    "isMobile",
                    "isAnalysis",
                    "sensorType",
                    "locations",
                    "locationIds",
                    "countries",
                    "parameters",
                    "measurements",
                    "firstUpdated",
                    "lastUpdated",
                    "sources"
                ],
                "type": "object",
                "properties": {
                    "id": {
                        "title": "Id",
                        "type": "integer"
                    },
                    "name": {
                        "title": "Name",
                        "type": "string"
                    },
                    "subtitle": {
                        "title": "Subtitle",
                        "type": "string"
                    },
                    "isMobile": {
                        "title": "Ismobile",
                        "type": "boolean"
                    },
                    "isAnalysis": {
                        "title": "Isanalysis",
                        "type": "boolean"
                    },
                    "entity": {
                        "title": "Entity",
                        "type": "string"
                    },
                    "sensorType": {
                        "title": "Sensortype",
                        "type": "string"
                    },
                    "locations": {
                        "title": "Locations",
                        "type": "integer"
                    },
                    "locationIds": {
                        "title": "Locationids",
                        "type": "array",
                        "items": {
                            "type": "integer"
                        }
                    },
                    "countries": {
                        "title": "Countries",
                        "type": "array",
                        "items": {
                            "type": "string"
                        }
                    },
                    "parameters": {
                        "title": "Parameters",
                        "type": "array",
                        "items": {
                            "$ref": "#/components/schemas/Parameter"
                        }
                    },
                    "bbox": {
                        "title": "Bbox",
                        "type": "array",
                        "items": {
                            "type": "number"
                        }
                    },
                    "measurements": {
                        "title": "Measurements",
                        "type": "integer"
                    },
                    "firstUpdated": {
                        "title": "Firstupdated",
                        "type": "string"
                    },
                    "lastUpdated": {
                        "title": "Lastupdated",
                        "type": "string"
                    },
                    "sources": {
                        "title": "Sources",
                        "type": "array",
                        "items": {
                            "$ref": "#/components/schemas/ProjectsSource"
                        }
                    }
                }
            },
            "ProjectsSource": {
                "title": "ProjectsSource",
                "required": [
                    "id",
                    "name"
                ],
                "type": "object",
                "properties": {
                    "id": {
                        "title": "Id",
                        "type": "string"
                    },
                    "name": {
                        "title": "Name",
                        "type": "string"
                    },
                    "readme": {
                        "title": "Readme",
                        "type": "string"
                    },
                    "data_avg_dur": {
                        "title": "Data Avg Dur",
                        "type": "string"
                    },
                    "organization": {
                        "title": "Organization",
                        "type": "string"
                    },
                    "lifecycle_stage": {
                        "title": "Lifecycle Stage",
                        "type": "string"
                    }
                }
            },
            "SensorTypes": {
                "title": "SensorTypes",
                "enum": [
                    "reference grade",
                    "low-cost sensor"
                ],
                "type": "string",
                "description": "An enumeration."
            },
            "Sort": {
                "title": "Sort",
                "enum": [
                    "asc",
                    "desc"
                ],
                "type": "string",
                "description": "An enumeration."
            },
            "Source": {
                "title": "Source",
                "required": [
                    "name"
                ],
                "type": "object",
                "properties": {
                    "url": {
                        "title": "Url",
                        "type": "string"
                    },
                    "name": {
                        "title": "Name",
                        "type": "string"
                    },
                    "id": {
                        "title": "Id",
                        "type": "string"
                    },
                    "readme": {
                        "title": "Readme",
                        "type": "string"
                    },
                    "organization": {
                        "title": "Organization",
                        "type": "string"
                    },
                    "lifecycle_stage": {
                        "title": "Lifecycle Stage",
                        "type": "string"
                    }
                }
            },
            "SourcesOrder": {
                "title": "SourcesOrder",
                "enum": [
                    "sourceName",
                    "firstUpdated",
                    "lastUpdated"
                ],
                "type": "string",
                "description": "An enumeration."
            },
            "SourcesResponse": {
                "title": "SourcesResponse",
                "required": [
                    "results"
                ],
                "type": "object",
                "properties": {
                    "meta": {
                        "title": "Meta",
                        "allOf": [
                            {
                                "$ref": "#/components/schemas/Meta"
                            }
                        ],
                        "default": {
                            "name": "openaq-api",
                            "license": "CC BY 4.0d",
                            "website": "/",
                            "page": 1,
                            "limit": 100,
                            "found": 0
                        }
                    },
                    "results": {
                        "title": "Results",
                        "type": "array",
                        "items": {
                            "$ref": "#/components/schemas/SourcesRow"
                        }
                    }
                }
            },
            "SourcesResponseV1": {
                "title": "SourcesResponseV1",
                "required": [
                    "results"
                ],
                "type": "object",
                "properties": {
                    "meta": {
                        "title": "Meta",
                        "allOf": [
                            {
                                "$ref": "#/components/schemas/Meta"
                            }
                        ],
                        "default": {
                            "name": "openaq-api",
                            "license": "CC BY 4.0d",
                            "website": "/",
                            "page": 1,
                            "limit": 100,
                            "found": 0
                        }
                    },
                    "results": {
                        "title": "Results",
                        "type": "array",
                        "items": {
                            "$ref": "#/components/schemas/SourcesRowV1"
                        }
                    }
                }
            },
            "SourcesRow": {
                "title": "SourcesRow",
                "required": [
                    "sourceId",
                    "locations",
                    "sourceName",
                    "sourceSlug"
                ],
                "type": "object",
                "properties": {
                    "data": {
                        "$ref": "#/components/schemas/Datum"
                    },
                    "readme": {
                        "title": "Readme",
                        "type": "string"
                    },
                    "sourceId": {
                        "title": "Sourceid",
                        "type": "integer"
                    },
                    "locations": {
                        "title": "Locations",
                        "type": "integer"
                    },
                    "sourceName": {
                        "title": "Sourcename",
                        "type": "string"
                    },
                    "sourceSlug": {
                        "title": "Sourceslug",
                        "type": "string"
                    }
                }
            },
            "SourcesRowV1": {
                "title": "SourcesRowV1",
                "required": [
                    "url",
                    "adapter",
                    "name",
                    "country",
                    "sourceURL",
                    "contacts",
                    "active"
                ],
                "type": "object",
                "properties": {
                    "url": {
                        "title": "Url",
                        "type": "string"
                    },
                    "adapter": {
                        "title": "Adapter",
                        "type": "string"
                    },
                    "name": {
                        "title": "Name",
                        "type": "string"
                    },
                    "city": {
                        "title": "City",
                        "type": "string"
                    },
                    "country": {
                        "title": "Country",
                        "type": "string"
                    },
                    "description": {
                        "title": "Description",
                        "type": "string"
                    },
                    "sourceURL": {
                        "title": "Sourceurl",
                        "maxLength": 65536,
                        "minLength": 1,
                        "type": "string",
                        "format": "uri"
                    },
                    "resolution": {
                        "title": "Resolution",
                        "type": "string"
                    },
                    "contacts": {
                        "title": "Contacts",
                        "type": "array",
                        "items": {
                            "type": "string"
                        }
                    },
                    "active": {
                        "title": "Active",
                        "type": "boolean"
                    }
                }
            },
            "SourcesV1Order": {
                "title": "SourcesV1Order",
                "enum": [
                    "name"
                ],
                "type": "string",
                "description": "An enumeration."
            },
            "Spatial": {
                "title": "Spatial",
                "enum": [
                    "country",
                    "location",
                    "project",
                    "total"
                ],
                "type": "string",
                "description": "An enumeration."
            },
            "SummaryResponse": {
                "title": "SummaryResponse",
                "required": [
                    "results"
                ],
                "type": "object",
                "properties": {
                    "meta": {
                        "title": "Meta",
                        "allOf": [
                            {
                                "$ref": "#/components/schemas/Meta"
                            }
                        ],
                        "default": {
                            "name": "openaq-api",
                            "license": "CC BY 4.0d",
                            "website": "/",
                            "page": 1,
                            "limit": 100,
                            "found": 0
                        }
                    },
                    "results": {
                        "title": "Results",
                        "type": "array",
                        "items": {
                            "$ref": "#/components/schemas/SummaryRow"
                        }
                    }
                }
            },
            "SummaryRow": {
                "title": "SummaryRow",
                "required": [
                    "count",
                    "cities",
                    "sources",
                    "countries",
                    "locations"
                ],
                "type": "object",
                "properties": {
                    "count": {
                        "title": "Count",
                        "type": "integer"
                    },
                    "cities": {
                        "title": "Cities",
                        "type": "integer"
                    },
                    "sources": {
                        "title": "Sources",
                        "type": "integer"
                    },
                    "countries": {
                        "title": "Countries",
                        "type": "integer"
                    },
                    "locations": {
                        "title": "Locations",
                        "type": "integer"
                    }
                }
            },
            "Temporal": {
                "title": "Temporal",
                "enum": [
                    "day",
                    "month",
                    "year",
                    "moy",
                    "dow",
                    "hour",
                    "hod"
                ],
                "type": "string",
                "description": "An enumeration."
            },
            "ValidationError": {
                "title": "ValidationError",
                "required": [
                    "loc",
                    "msg",
                    "type"
                ],
                "type": "object",
                "properties": {
                    "loc": {
                        "title": "Location",
                        "type": "array",
                        "items": {
                            "anyOf": [
                                {
                                    "type": "string"
                                },
                                {
                                    "type": "integer"
                                }
                            ]
                        }
                    },
                    "msg": {
                        "title": "Message",
                        "type": "string"
                    },
                    "type": {
                        "title": "Error Type",
                        "type": "string"
                    }
                }
            }
        }
    }
}

```
Updated about 2 years ago 



---

