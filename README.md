# swagger


{
  "swagger": "2.0",
  "schemes": [
    "https"
  ],
  "basePath": "/v1",
  "host": "apis.cert.vantiv.com",
  "info": {
    "version": "1.0.0",
    "title": "Element Express",
    "description": "Element Express RESTful"
  },
  "consumes": [
    "application/json",
    "application/xml"
  ],
  "produces": [
    "application/json",
    "application/xml"
  ],
  "paths": {
    "/account": {
      "parameters": [],
      "delete": {
        "tags": [
          "Account"
        ],
        "summary": "Account Delete",
        "description": "",
        "parameters": [
          {
            "name": "body",
            "in": "body",
            "schema": {
              "type": "object",
              "properties": {
                "Application": {
                  "$ref": "#/definitions/Application"
                },
                "PaymentAccount": {
                  "allOf": [
                    {
                      "$ref": "#/definitions/PaymentAccountID"
                    }
                  ]
                }
              },
              "required": [
                "Application",
                "PaymentAccount"
              ]
            }
          },
          {
            "name": "Content-Type",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Accept",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Authorization",
            "in": "header",
            "description": "",
            "type": "string"
          }
        ],
        "responses": {
          "200": {
            "description": "",
            "schema": {
              "$ref": "#/definitions/ResponseServicesBase"
            }
          }
        }
      },
      "post": {
        "tags": [
          "Account"
        ],
        "summary": "Account Create",
        "description": "",
        "parameters": [
          {
            "name": "body",
            "in": "body",
            "schema": {
              "type": "object",
              "properties": {
                "Application": {
                  "$ref": "#/definitions/Application"
                },
                "PaymentAccount": {
                  "allOf": [
                    {
                      "$ref": "#/definitions/PaymentAccountType"
                    },
                    {
                      "$ref": "#/definitions/PaymentAccountReferenceNumber"
                    },
                    {
                      "$ref": "#/definitions/PASSUpdaterBatchStatus"
                    },
                    {
                      "$ref": "#/definitions/PASSUpdaterOption"
                    }
                  ]
                },
                "Card": {
                  "$ref": "#/definitions/Card"
                },
                "DemandDepositAccount": {
                  "$ref": "#/definitions/DemandDepositAccount"
                },
                "Address": {
                  "$ref": "#/definitions/Address"
                }
              },
              "required": [
                "Application",
                "PaymentAccount"
              ]
            }
          }
        ],
        "responses": {
          "201": {
            "description": "",
            "schema": {
              "$ref": "#/definitions/ResponseServicesBase"
            }
          }
        }
      },
      "put": {
        "tags": [
          "Account"
        ],
        "summary": "Account Update",
        "description": "",
        "parameters": [
          {
            "name": "body",
            "in": "body",
            "schema": {
              "type": "object",
              "properties": {
                "Application": {
                  "$ref": "#/definitions/Application"
                },
                "PaymentAccount": {
                  "allOf": [
                    {
                      "$ref": "#/definitions/PaymentAccountID"
                    },
                    {
                      "$ref": "#/definitions/PaymentAccountReferenceNumber"
                    },
                    {
                      "$ref": "#/definitions/PaymentAccountType"
                    }
                  ]
                },
                "Card": {
                  "$ref": "#/definitions/Card"
                },
                "DemandDepositAccount": {
                  "$ref": "#/definitions/DemandDepositAccount"
                },
                "Address": {
                  "$ref": "#/definitions/Address"
                }
              }
            }
          }
        ],
        "responses": {
          "200": {
            "description": "",
            "schema": {
              "$ref": "#/definitions/ResponseServicesBase"
            }
          }
        }
      }
    },
    "/decryption": {
      "parameters": [],
      "post": {
        "summary": "Decryption",
        "description": "",
        "parameters": [],
        "responses": {
          "default": {
            "description": "",
            "schema": {}
          }
        }
      }
    },
    "/account/query": {
      "parameters": [],
      "post": {
        "tags": [
          "Account"
        ],
        "summary": "Account Query",
        "description": "",
        "parameters": [
          {
            "name": "body",
            "in": "body",
            "schema": {
              "type": "object",
              "properties": {
                "Application": {
                  "$ref": "#/definitions/Application"
                },
                "PaymentAccountParameters": {
                  "$ref": "#/definitions/PaymentAccountParameters"
                }
              },
              "required": [
                "Application"
              ]
            }
          },
          {
            "name": "Content-Type",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Accept",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Authorization",
            "in": "header",
            "description": "",
            "type": "string"
          }
        ],
        "responses": {
          "200": {
            "description": "",
            "schema": {
              "allOf": [
                {
                  "$ref": "#/definitions/ResponseServicesBase"
                },
                {
                  "type": "object",
                  "properties": {
                    "QueryData": {
                      "type": "string"
                    }
                  }
                }
              ]
            }
          }
        }
      }
    },
    "/account/withtransactionid": {
      "parameters": [],
      "post": {
        "tags": [
          "Account"
        ],
        "summary": "Account Create with Transaction ID",
        "description": "",
        "parameters": [
          {
            "name": "body",
            "in": "body",
            "schema": {
              "type": "object",
              "properties": {
                "Application": {
                  "$ref": "#/definitions/Application"
                },
                "PaymentAcount": {
                  "allOf": [
                    {
                      "$ref": "#/definitions/PaymentAccountType"
                    },
                    {
                      "$ref": "#/definitions/PaymentAccountReferenceNumber"
                    }
                  ]
                },
                "Transaction": {
                  "type": "object",
                  "properties": {
                    "TransactionID": {
                      "$ref": "#/definitions/TransactionID"
                    }
                  }
                },
                "Address": {
                  "$ref": "#/definitions/Address"
                }
              }
            }
          },
          {
            "name": "Authorization",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Content-Type",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Accept",
            "in": "header",
            "description": "",
            "type": "string"
          }
        ],
        "responses": {
          "201": {
            "description": "",
            "schema": {
              "$ref": "#/definitions/ResponseServicesBase"
            }
          }
        }
      }
    },
    "/account/querytokenreport": {
      "parameters": [],
      "post": {
        "tags": [
          "Account"
        ],
        "summary": "Account Query Token Report",
        "description": "",
        "parameters": [
          {
            "name": "body",
            "in": "body",
            "schema": {
              "type": "object",
              "properties": {
                "Application": {
                  "$ref": "#/definitions/Application"
                },
                "Paging": {
                  "type": "object",
                  "required": [
                    "Page"
                  ],
                  "properties": {
                    "Page": {
                      "$ref": "#/definitions/Page"
                    }
                  }
                }
              },
              "required": [
                "Application",
                "Paging"
              ]
            }
          },
          {
            "name": "Content-Type",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Accept",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Authorization",
            "in": "header",
            "description": "",
            "type": "string"
          }
        ],
        "responses": {
          "200": {
            "description": "",
            "schema": {
              "allOf": [
                {
                  "$ref": "#/definitions/ResponseBase"
                },
                {
                  "type": "object",
                  "properties": {
                    "ServicesID": {
                      "$ref": "#/definitions/ServicesID"
                    },
                    "QueryData": {
                      "type": "string"
                    }
                  }
                }
              ]
            }
          }
        }
      }
    },
    "/task/{taskid}": {
      "parameters": [
        {
          "name": "taskid",
          "in": "path",
          "required": true,
          "type": "string"
        }
      ],
      "delete": {
        "tags": [
          "Task"
        ],
        "summary": "Task Delete",
        "description": "",
        "parameters": [
          {
            "name": "body",
            "in": "body",
            "schema": {
              "type": "object",
              "properties": {
                "Application": {
                  "$ref": "#/definitions/Application"
                }
              },
              "required": [
                "Application"
              ]
            }
          },
          {
            "name": "Content-Type",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Accept",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Authorization",
            "in": "header",
            "description": "",
            "type": "string"
          }
        ],
        "responses": {
          "200": {
            "description": "",
            "schema": {
              "$ref": "#/definitions/ResponseBase"
            }
          }
        }
      },
      "put": {
        "tags": [
          "Task"
        ],
        "summary": "Task Update",
        "description": "",
        "parameters": [
          {
            "name": "body",
            "in": "body",
            "schema": {
              "type": "object",
              "properties": {
                "Application": {
                  "$ref": "#/definitions/Application"
                },
                "ScheduledTask": {
                  "type": "object",
                  "required": [
                    "ScheduledTaskID",
                    "ScheduledTaskReferenceNumber",
                    "RunFrequency",
                    "RunUntilCancelFlag",
                    "ScheduledTaskStatus"
                  ],
                  "properties": {
                    "ScheduledTaskID": {
                      "$ref": "#/definitions/ScheduledTaskID"
                    },
                    "ScheduledTaskReferenceNumber": {
                      "$ref": "#/definitions/ScheduledTaskReferenceNumber"
                    },
                    "RunFrequency": {
                      "$ref": "#/definitions/RunFrequency"
                    },
                    "RunUntilCancelFlag": {
                      "$ref": "#/definitions/RunUntilCancelFlag"
                    },
                    "RunCycles": {
                      "type": "string"
                    },
                    "ScheduledTaskStatus": {
                      "$ref": "#/definitions/ScheduledTaskStatus"
                    },
                    "ScheduledTaskName": {
                      "$ref": "#/definitions/ScheduledTaskName"
                    },
                    "ScheduledTaskGroupID": {
                      "$ref": "#/definitions/ScheduledTaskGroupID"
                    }
                  }
                }
              },
              "required": [
                "Application",
                "ScheduledTask"
              ]
            }
          },
          {
            "name": "Content-Type",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Accept",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Authorization",
            "in": "header",
            "description": "",
            "type": "string"
          }
        ],
        "responses": {
          "200": {
            "description": "",
            "schema": {
              "$ref": "#/definitions/ResponseBase"
            }
          }
        }
      }
    },
    "/account/autoupdate": {
      "parameters": [],
      "put": {
        "tags": [
          "Account"
        ],
        "summary": "Account Auto Update",
        "description": "",
        "parameters": [
          {
            "name": "body",
            "in": "body",
            "schema": {
              "type": "object",
              "properties": {
                "Application": {
                  "$ref": "#/definitions/Application"
                },
                "PaymentAccount": {
                  "allOf": [
                    {
                      "$ref": "#/definitions/PaymentAccountID"
                    },
                    {
                      "$ref": "#/definitions/PASSUpdaterBatchStatus"
                    },
                    {
                      "$ref": "#/definitions/PASSUpdaterOption"
                    }
                  ]
                }
              },
              "required": [
                "Application"
              ]
            }
          },
          {
            "name": "Accept",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Content-Type",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Authorization",
            "in": "header",
            "description": "",
            "type": "string"
          }
        ],
        "responses": {
          "200": {
            "description": "",
            "schema": {
              "allOf": [
                {
                  "$ref": "#/definitions/ResponseServicesBase"
                }
              ]
            }
          }
        }
      }
    },
    "/task/query/{taskid}": {
      "parameters": [
        {
          "name": "taskid",
          "in": "path",
          "required": true,
          "type": "string"
        }
      ],
      "post": {
        "tags": [
          "Task"
        ],
        "summary": "Task Query",
        "description": "",
        "parameters": [
          {
            "name": "body",
            "in": "body",
            "schema": {
              "type": "object",
              "properties": {
                "Application": {
                  "$ref": "#/definitions/Application"
                },
                "ScheduledTaskParameters": {
                  "$ref": "#/definitions/ScheduledTaskParameters"
                }
              },
              "required": [
                "Application"
              ]
            }
          },
          {
            "name": "Content-Type",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Accept",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Authorization",
            "in": "header",
            "description": "",
            "type": "string"
          }
        ],
        "responses": {
          "201": {
            "description": "",
            "schema": {
              "allOf": [
                {
                  "$ref": "#/definitions/ResponseBase"
                },
                {
                  "type": "object",
                  "properties": {
                    "QueryData": {
                      "type": "string"
                    },
                    "ServicesID": {
                      "$ref": "#/definitions/ServicesID"
                    },
                    "ScheduledTask": {
                      "$ref": "#/definitions/ResponseScheduledTask"
                    }
                  }
                }
              ]
            }
          }
        }
      }
    },
    "/transaction/expire": {
      "parameters": [],
      "post": {
        "tags": [
          "Transaction"
        ],
        "summary": "Transaction Expire",
        "description": "",
        "parameters": [
          {
            "name": "body",
            "in": "body",
            "schema": {
              "type": "object",
              "properties": {
                "Application": {
                  "$ref": "#/definitions/Application"
                },
                "TransactionSetup": {
                  "type": "object",
                  "required": [
                    "TransactionSetupID"
                  ],
                  "properties": {
                    "TransactionSetupID": {
                      "type": "string"
                    }
                  }
                }
              },
              "required": [
                "TransactionSetup"
              ]
            }
          },
          {
            "name": "Content-Type",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Accept",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Authorization",
            "in": "header",
            "description": "",
            "type": "string"
          }
        ],
        "responses": {
          "200": {
            "description": "",
            "schema": {
              "$ref": "#/definitions/ResponseBase"
            }
          }
        }
      }
    },
    "/bin/query": {
      "parameters": [],
      "post": {
        "tags": [
          "BIN"
        ],
        "summary": "BIN Query",
        "description": "",
        "parameters": [
          {
            "name": "body",
            "in": "body",
            "schema": {
              "type": "object",
              "properties": {
                "Application": {
                  "$ref": "#/definitions/Application"
                },
                "Card": {
                  "$ref": "#/definitions/Card"
                },
                "ExtendedParameters": {
                  "type": "object",
                  "properties": {
                    "PaymentAccount": {
                      "type": "object",
                      "properties": {
                        "PaymentAccountID": {
                          "type": "string"
                        }
                      }
                    }
                  }
                },
                "Terminal": {
                  "type": "object",
                  "properties": {
                    "TerminalID": {
                      "type": "string"
                    }
                  }
                }
              },
              "required": [
                "Application",
                "Card"
              ]
            }
          },
          {
            "name": "Content-Type",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Accept",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Authorization",
            "in": "header",
            "description": "",
            "type": "string"
          }
        ],
        "responses": {
          "200": {
            "description": "",
            "schema": {
              "allOf": [
                {
                  "$ref": "#/definitions/ResponseBase"
                },
                {
                  "type": "object",
                  "properties": {
                    "BIN": {
                      "type": "object",
                      "properties": {
                        "BINTypeCode": {
                          "type": "string"
                        },
                        "BINTypeValue": {
                          "type": "string"
                        },
                        "BINDecorator": {
                          "type": "string"
                        }
                      }
                    }
                  }
                }
              ]
            }
          }
        }
      }
    },
    "/transaction/query": {
      "parameters": [],
      "post": {
        "tags": [
          "Transaction"
        ],
        "summary": "Transaction Query",
        "description": "",
        "parameters": [
          {
            "name": "body",
            "in": "body",
            "schema": {
              "type": "object",
              "properties": {
                "Application": {
                  "$ref": "#/definitions/Application"
                },
                "Parameters": {
                  "type": "object",
                  "properties": {
                    "TransactionDateTimeBegin": {
                      "type": "string"
                    },
                    "TransactionDateTimeEnd": {
                      "type": "string"
                    },
                    "TransactionID": {
                      "$ref": "#/definitions/TransactionID"
                    },
                    "TerminalID": {
                      "$ref": "#/definitions/TerminalID"
                    },
                    "ApplicationID": {
                      "$ref": "#/definitions/ApplicationID"
                    },
                    "ApprovalNumber": {
                      "type": "string"
                    },
                    "ApprovedAmount": {
                      "type": "string"
                    },
                    "ExpressTransactionDate": {
                      "type": "string"
                    },
                    "ExpressTransactionTime": {
                      "type": "string"
                    },
                    "HostBatchID": {
                      "type": "string"
                    },
                    "HostItemID": {
                      "type": "string"
                    },
                    "ReferenceNumber": {
                      "type": "string"
                    },
                    "ShiftID": {
                      "type": "string"
                    },
                    "TrackingID": {
                      "type": "string"
                    },
                    "TransactionAmount": {
                      "type": "string"
                    },
                    "TransactionSetupID": {
                      "type": "string"
                    },
                    "TransactionStatusCode": {
                      "type": "string"
                    },
                    "TransactionType": {
                      "type": "string"
                    },
                    "ReverseOrder": {
                      "type": "string"
                    }
                  }
                }
              },
              "required": [
                "Application"
              ]
            }
          },
          {
            "name": "Content-Type",
            "in": "header",
            "description": "",
            "required": true,
            "type": "string"
          },
          {
            "name": "Accept",
            "in": "header",
            "description": "",
            "required": true,
            "type": "string"
          },
          {
            "name": "Authorization",
            "in": "header",
            "description": "",
            "required": true,
            "type": "string"
          }
        ],
        "responses": {
          "201": {
            "description": "",
            "schema": {
              "allOf": [
                {
                  "$ref": "#/definitions/ResponseBase"
                },
                {
                  "type": "object",
                  "properties": {
                    "ReportingID": {
                      "type": "string"
                    },
                    "ReportingData": {
                      "type": "string"
                    }
                  },
                  "required": [
                    "ReportingID",
                    "ReportingData"
                  ]
                }
              ]
            }
          }
        }
      }
    },
    "/account/queryrecordcount": {
      "parameters": [],
      "post": {
        "tags": [
          "Account"
        ],
        "summary": "Account Query Record Count",
        "description": "",
        "parameters": [
          {
            "name": "body",
            "in": "body",
            "schema": {
              "type": "object",
              "properties": {
                "Application": {
                  "$ref": "#/definitions/Application"
                }
              }
            }
          },
          {
            "name": "Authorization",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Content-Type",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Accept",
            "in": "header",
            "description": "",
            "type": "string"
          }
        ],
        "responses": {
          "200": {
            "description": "",
            "schema": {
              "allOf": [
                {
                  "$ref": "#/definitions/ResponseBase"
                },
                {
                  "type": "object",
                  "properties": {
                    "ServicesID": {
                      "$ref": "#/definitions/ServicesID"
                    },
                    "QueryData": {
                      "type": "string"
                    }
                  }
                }
              ]
            }
          }
        }
      }
    },
    "/task/retry/{taskid}": {
      "parameters": [
        {
          "name": "taskid",
          "in": "path",
          "required": true,
          "type": "string"
        }
      ],
      "put": {
        "tags": [
          "Task"
        ],
        "summary": "Task Retry",
        "description": "",
        "parameters": [
          {
            "name": "body",
            "in": "body",
            "schema": {
              "type": "object",
              "properties": {
                "Application": {
                  "$ref": "#/definitions/Application"
                },
                "ScheduledTask": {
                  "type": "object",
                  "properties": {
                    "ScheduledTaskRunLogID": {
                      "type": "string"
                    }
                  }
                }
              }
            }
          },
          {
            "name": "Content-Type",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Accept",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Authorization",
            "in": "header",
            "description": "",
            "type": "string"
          }
        ],
        "responses": {
          "200": {
            "description": "",
            "schema": {
              "allOf": [
                {
                  "$ref": "#/definitions/ResponseBase"
                },
                {
                  "type": "object",
                  "properties": {
                    "ServicesID": {
                      "$ref": "#/definitions/ServicesID"
                    },
                    "Transaction": {
                      "$ref": "#/definitions/ResponseTransaction"
                    },
                    "ScheduledTask": {
                      "type": "object",
                      "properties": {
                        "ScheduledTaskID": {
                          "$ref": "#/definitions/ScheduledTaskID"
                        }
                      }
                    }
                  }
                }
              ]
            }
          }
        }
      }
    },
    "/token": {
      "parameters": [],
      "post": {
        "tags": [
          "Token"
        ],
        "summary": "Create Token",
        "description": "",
        "parameters": [
          {
            "name": "body",
            "in": "body",
            "schema": {
              "type": "object",
              "properties": {
                "Application": {
                  "$ref": "#/definitions/Application"
                },
                "Card": {
                  "$ref": "#/definitions/Card"
                },
                "Terminal": {
                  "$ref": "#/definitions/Terminal"
                },
                "Token": {
                  "type": "object",
                  "required": [
                    "TokenProvider"
                  ],
                  "properties": {
                    "TokenProvider": {
                      "$ref": "#/definitions/TokenProvider"
                    },
                    "VaultID": {
                      "$ref": "#/definitions/VaultID"
                    }
                  }
                }
              },
              "required": [
                "Application",
                "Card",
                "Token"
              ]
            }
          },
          {
            "name": "Content-Type",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Accept",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Authorization",
            "in": "header",
            "description": "",
            "type": "string"
          }
        ],
        "responses": {
          "201": {
            "description": "",
            "schema": {
              "allOf": [
                {
                  "$ref": "#/definitions/ResponseBase"
                },
                {
                  "type": "object",
                  "properties": {
                    "Card": {
                      "$ref": "#/definitions/ResponseCard"
                    },
                    "Token": {
                      "$ref": "#/definitions/ResponseToken"
                    }
                  }
                }
              ]
            }
          }
        }
      }
    },
    "/token/withtransactionid": {
      "parameters": [],
      "post": {
        "tags": [
          "Token"
        ],
        "summary": "Create Token with Transaction ID",
        "description": "",
        "parameters": [
          {
            "name": "body",
            "in": "body",
            "schema": {
              "type": "object",
              "properties": {
                "Application": {
                  "$ref": "#/definitions/Application"
                },
                "Card": {
                  "$ref": "#/definitions/Card"
                },
                "Terminal": {
                  "$ref": "#/definitions/Terminal"
                },
                "Token": {
                  "type": "object",
                  "required": [
                    "TokenProvider"
                  ],
                  "properties": {
                    "TokenProvider": {
                      "$ref": "#/definitions/TokenProvider"
                    },
                    "VaultID": {
                      "$ref": "#/definitions/VaultID"
                    }
                  }
                },
                "Transaction": {
                  "type": "object",
                  "required": [
                    "TransactionID"
                  ],
                  "properties": {
                    "TransactionID": {
                      "$ref": "#/definitions/TransactionID"
                    }
                  }
                }
              },
              "required": [
                "Application",
                "Card",
                "Token",
                "Transaction"
              ]
            }
          },
          {
            "name": "Content-Type",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Accept",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Authorization",
            "in": "header",
            "description": "",
            "type": "string"
          }
        ],
        "responses": {
          "201": {
            "description": "",
            "schema": {
              "allOf": [
                {
                  "$ref": "#/definitions/ResponseBase"
                },
                {
                  "type": "object",
                  "properties": {
                    "Card": {
                      "$ref": "#/definitions/ResponseCard"
                    },
                    "Token": {
                      "$ref": "#/definitions/ResponseToken"
                    },
                    "ServicesID": {
                      "$ref": "#/definitions/ServicesID"
                    }
                  }
                }
              ]
            }
          }
        }
      }
    },
    "/transaction/setup": {
      "parameters": [],
      "post": {
        "tags": [
          "Transaction"
        ],
        "summary": "Transaction Setup",
        "parameters": [
          {
            "name": "body",
            "in": "body",
            "schema": {
              "type": "object",
              "properties": {
                "Application": {
                  "$ref": "#/definitions/Application"
                },
                "Transaction": {
                  "$ref": "#/definitions/Transaction"
                },
                "Terminal": {
                  "$ref": "#/definitions/Terminal"
                },
                "PaymentAccount": {
                  "type": "object",
                  "properties": {
                    "PaymentAccountID": {
                      "$ref": "#/definitions/PaymentAccountID"
                    },
                    "PaymentAccountType": {
                      "$ref": "#/definitions/PaymentAccountType"
                    },
                    "PaymentAccountReferenceNumber": {
                      "$ref": "#/definitions/PaymentAccountReferenceNumber"
                    }
                  }
                },
                "Address": {
                  "$ref": "#/definitions/Address"
                },
                "TransactionSetup": {
                  "type": "object",
                  "properties": {
                    "TransactionSetupMethod": {
                      "type": "string"
                    },
                    "Device": {
                      "type": "string"
                    },
                    "Embedded": {
                      "type": "string"
                    },
                    "CVVRequired": {
                      "type": "string"
                    },
                    "AutoReturn": {
                      "type": "string"
                    },
                    "DeviceInputCode": {
                      "type": "string"
                    },
                    "CompanyName": {
                      "type": "string"
                    },
                    "LogoURL": {
                      "type": "string"
                    },
                    "Tagline": {
                      "type": "string"
                    },
                    "WelcomeMessage": {
                      "type": "string"
                    },
                    "ReturnURL": {
                      "type": "string"
                    },
                    "ReturnURLTitle": {
                      "type": "string"
                    },
                    "OrderDetails": {
                      "type": "string"
                    }
                  }
                },
                "ExtendedParameters": {
                  "type": "object",
                  "properties": {
                    "Lodging": {
                      "$ref": "#/definitions/Lodging"
                    },
                    "Healtcare": {
                      "$ref": "#/definitions/Healthcare"
                    },
                    "AutoRental": {
                      "$ref": "#/definitions/AutoRental"
                    }
                  }
                }
              },
              "required": [
                "Application",
                "Terminal"
              ]
            }
          },
          {
            "name": "Authorization",
            "in": "header",
            "description": "",
            "required": true,
            "type": "string"
          },
          {
            "name": "Content-Type",
            "in": "header",
            "description": "",
            "required": true,
            "type": "string"
          },
          {
            "name": "Accept",
            "in": "header",
            "description": "",
            "required": true,
            "type": "string"
          }
        ],
        "responses": {
          "201": {
            "description": "",
            "schema": {
              "allOf": [
                {
                  "$ref": "#/definitions/ResponseBase"
                },
                {
                  "type": "object",
                  "properties": {
                    "Transaction": {
                      "type": "object",
                      "properties": {
                        "TransactionSetupID": {
                          "$ref": "#/definitions/TransactionSetupID"
                        }
                      }
                    },
                    "PaymentAccount": {
                      "type": "object",
                      "properties": {
                        "TransactionSetupID": {
                          "$ref": "#/definitions/TransactionSetupID"
                        }
                      }
                    },
                    "TransactionSetup": {
                      "type": "object",
                      "properties": {
                        "TransactionSetupID": {
                          "$ref": "#/definitions/TransactionSetupID"
                        },
                        "ValidationCode": {
                          "type": "string"
                        }
                      }
                    }
                  }
                }
              ]
            }
          }
        }
      }
    },
    "/bin/enhancedquery": {
      "parameters": [],
      "post": {
        "tags": [
          "BIN"
        ],
        "summary": "BIN Enhanced Query",
        "description": "",
        "parameters": [
          {
            "name": "body",
            "in": "body",
            "schema": {
              "type": "object",
              "properties": {
                "Application": {
                  "$ref": "#/definitions/Application"
                },
                "Card": {
                  "$ref": "#/definitions/Card"
                },
                "ExtendedParameters": {
                  "type": "object",
                  "properties": {
                    "PaymentAccount": {
                      "type": "object",
                      "properties": {
                        "PaymentAccountID": {
                          "type": "string"
                        }
                      }
                    }
                  }
                },
                "Terminal": {
                  "type": "object",
                  "properties": {
                    "TerminalID": {
                      "type": "string"
                    }
                  }
                }
              },
              "required": [
                "Application",
                "Card"
              ]
            }
          },
          {
            "name": "Content-Type",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Accept",
            "in": "header",
            "description": "",
            "type": "string"
          },
          {
            "name": "Authorization",
            "in": "header",
            "description": "",
            "type": "string"
          }
        ],
        "responses": {
          "200": {
            "description": "",
            "schema": {
              "allOf": [
                {
                  "$ref": "#/definitions/ResponseBase"
                },
                {
                  "type": "object",
                  "properties": {
                    "EnhancedBIN": {
                      "type": "object",
                      "properties": {
                        "Status": {
                          "type": "string"
                        },
                        "CheckCard": {
                          "type": "string"
                        },
                        "CommercialCard": {
                          "type": "string"
                        },
                        "CreditCard": {
                          "type": "string"
                        },
                        "DebitCard": {
                          "type": "string"
                        },
                        "DurbinBINRegulation": {
                          "type": "string"
                        },
                        "EBT": {
                          "type": "string"
                        },
                        "FleetCard": {
                          "type": "string"
                        },
                        "GiftCard": {
                          "type": "string"
                        },
                        "HSAFSACard": {
                          "type": "string"
                        },
                        "InternationalBN": {
                          "type": "string"
                        },
                        "PrepaidCard": {
                          "type": "string"
                        },
                        "WIC": {
                          "type": "string"
                        },
                        "": {
                          "type": "string"
                        }
                      }
                    }
                  }
                }
              ]
            }
          }
        }
      }
    }
  },
  "definitions": {
    "PaymentAccountReferenceNumber": {
      "type": "string"
    },
    "PaymentAccountType": {
      "type": "string"
    },
    "TransactionID": {
      "type": "string"
    },
    "Page": {
      "type": "string"
    },
    "PASSUpdaterBatchStatus": {
      "type": "string"
    },
    "PaymentAccountID": {
      "type": "string"
    },
    "ServicesID": {
      "type": "string"
    },
    "TransactionSetupID": {
      "type": "string"
    },
    "ResponseServicesBase": {
      "allOf": [
        {
          "$ref": "#/definitions/ResponseBase"
        },
        {
          "type": "object",
          "properties": {
            "ServicesID": {
              "type": "string"
            }
          }
        },
        {
          "type": "object",
          "properties": {
            "PaymentAccount": {
              "$ref": "#/definitions/ResponsePaymentAccount"
            }
          }
        }
      ]
    },
    "TerminalID": {
      "type": "string"
    },
    "ApplicationID": {
      "type": "string"
    },
    "PaymentAccountParameters": {
      "type": "object",
      "properties": {
        "PaymentAccountID": {
          "$ref": "#/definitions/PaymentAccountID"
        },
        "PaymentAccountReferenceNumber": {
          "$ref": "#/definitions/PaymentAccountReferenceNumber"
        },
        "PaymentBrand": {
          "type": "string"
        },
        "ExpirationMonthBegin": {
          "type": "string"
        },
        "ExpirationMonthEnd": {
          "type": "string"
        },
        "ExpirationYearBegin": {
          "type": "string"
        },
        "ExpirationYearEnd": {
          "type": "string"
        },
        "TransactionSetupID": {
          "type": "string"
        },
        "PASSUpdaterDateTimeBegin": {
          "type": "string"
        },
        "PASSUpdaterDateTimeEnd": {
          "type": "string"
        },
        "PASSUpdaterBatchStatus": {
          "$ref": "#/definitions/PASSUpdaterBatchStatus"
        },
        "PASSUpdaterStatus": {
          "type": "string"
        }
      }
    },
    "PASSUpdaterOption": {
      "type": "string"
    },
    "ResponseBase": {
      "type": "object",
      "properties": {
        "ExpressResponseCode": {
          "type": "string"
        },
        "ExpressResponseMessage": {
          "type": "string"
        },
        "ExpressTransactionDate": {
          "type": "string"
        },
        "ExpressTransactionTime": {
          "type": "string"
        },
        "ExpressTransactionTimezone": {
          "type": "string"
        }
      },
      "required": [
        "ExpressResponseCode",
        "ExpressResponseMessage",
        "ExpressTransactionDate",
        "ExpressTransactionTime",
        "ExpressTransactionTimezone"
      ]
    },
    "ResponseBatch": {
      "type": "object",
      "required": [
        "HostBatchID",
        "HostItemID",
        "HostBatchAmount"
      ],
      "properties": {
        "HostBatchID": {
          "type": "string"
        },
        "HostItemID": {
          "type": "string"
        },
        "HostBatchAmount": {
          "type": "string"
        }
      }
    },
    "ResponseCard": {
      "type": "object",
      "properties": {
        "CardLogo": {
          "type": "string"
        },
        "TruncatedCardNumber": {
          "type": "string"
        },
        "ExpirationMonth": {
          "type": "string"
        },
        "ExpirationYear": {
          "type": "string"
        }
      },
      "required": [
        "CardLogo"
      ]
    },
    "ResponseTransaction": {
      "type": "object",
      "properties": {
        "TransactionID": {
          "type": "string"
        },
        "ProcessorName": {
          "type": "string"
        },
        "TransactionStatus": {
          "type": "string"
        },
        "TransactionStatusCode": {
          "type": "string"
        }
      },
      "required": [
        "TransactionID",
        "ProcessorName",
        "TransactionStatus",
        "TransactionStatusCode"
      ]
    },
    "ResponseToken": {
      "type": "object",
      "properties": {
        "TokenID": {
          "type": "string"
        },
        "TokenProvider": {
          "type": "string"
        }
      }
    },
    "ResponseAddress": {
      "type": "object",
      "properties": {
        "BillingAddress1": {
          "type": "string"
        },
        "BillingZipcode": {
          "type": "string"
        }
      }
    },
    "ResponsePaymentAccount": {
      "type": "object",
      "properties": {
        "PaymentAccountID": {
          "type": "string"
        },
        "PaymentAccountReferenceNumber": {
          "type": "string"
        }
      },
      "required": [
        "PaymentAccountID",
        "PaymentAccountReferenceNumber"
      ]
    },
    "ResponseScheduledTask": {
      "type": "object",
      "properties": {
        "ScheduledTaskID": {
          "type": "string"
        },
        "ScheduledTaskName": {
          "type": "string"
        },
        "ScheduledTaskGroupID": {
          "type": "string"
        }
      }
    },
    "Application": {
      "type": "object",
      "properties": {
        "ApplicationID": {
          "type": "string"
        },
        "ApplicationName": {
          "type": "string"
        },
        "ApplicationVersion": {
          "type": "string"
        }
      },
      "required": [
        "ApplicationID",
        "ApplicationName",
        "ApplicationVersion"
      ]
    },
    "Transaction": {
      "type": "object",
      "properties": {
        "TransactionAmount": {
          "type": "string"
        },
        "ClerkNumber": {
          "type": "string"
        },
        "ShiftID": {
          "type": "string"
        },
        "ReferenceNumber": {
          "type": "string"
        },
        "MarketCode": {
          "type": "string",
          "enum": [
            "Default",
            "AutoRental",
            "DirectMarketing",
            "ECommerce",
            "FoodRestaurant",
            "HotelLodging",
            "Petroleum",
            "Retail",
            "QSR"
          ]
        },
        "SalesTaxAmount": {
          "type": "string"
        },
        "TipAmount": {
          "type": "string"
        },
        "ConvenienceFeeAmount": {
          "type": "string"
        },
        "TicketNumber": {
          "type": "string"
        }
      }
    },
    "Terminal": {
      "type": "object",
      "properties": {
        "TerminalID": {
          "$ref": "#/definitions/TerminalID"
        },
        "CardPresentCode": {
          "type": "string",
          "enum": [
            "Default",
            "Unknown",
            "Present",
            "NotPresent"
          ]
        },
        "CardholderPresentCode": {
          "type": "string",
          "enum": [
            "Default",
            "Unknown",
            "Present",
            "NotPresent",
            "MailOrder",
            "PhoneOrder",
            "StandingAuth",
            "ECommerce"
          ]
        },
        "CardInputCode": {
          "type": "string",
          "enum": [
            "Default",
            "Unknown",
            "MagstripeRead",
            "ContactlessMagstripeRead",
            "ManualKeyed",
            "ManualKeyedMagstripeFailure"
          ]
        },
        "TerminalCapabilityCode": {
          "type": "string",
          "enum": [
            "Default",
            "Unknown",
            "NoTerminal",
            "MagstripeReader",
            "ContactlessMagstripeReader",
            "KeyEntered"
          ]
        },
        "TerminalEnvironmentCode": {
          "type": "string",
          "enum": [
            "Default",
            "NoTerminal",
            "LocalAttended",
            "LocalUnattended",
            "RemoteAttended",
            "RemoteUnattended",
            "ECommerce"
          ]
        },
        "MotoECICode": {
          "type": "string",
          "enum": [
            "Default",
            "NotUsed",
            "Single",
            "Recurring",
            "Installment",
            "SecureElectronicCommerce",
            "NonAuthenticatedSecureTransaction",
            "NonAuthenticatedSecureECommerceTransaction",
            "NonSecureECommerceTransaction"
          ]
        },
        "TerminalType": {
          "type": "string",
          "enum": [
            "Unknown",
            "PointOfSale",
            "ECommerce",
            "MOTO",
            "FuelPump",
            "ATM",
            "Voice"
          ]
        },
        "LaneNumber": {
          "type": "string"
        },
        "CVVPresenceCode": {
          "type": "string"
        },
        "CVVResponseType": {
          "type": "string"
        },
        "ConsentCode": {
          "type": "string"
        },
        "TerminalEncryptionFormat": {
          "type": "string"
        }
      },
      "required": [
        "TerminalID"
      ]
    },
    "Card": {
      "type": "object",
      "properties": {
        "Track1Data": {
          "type": "string"
        },
        "Track2Data": {
          "type": "string"
        },
        "MagneprintData": {
          "type": "string"
        },
        "EncryptedTrack1Data": {
          "type": "string"
        },
        "EncryptedTrack2Data": {
          "type": "string"
        },
        "EncryptedCardData": {
          "type": "string"
        },
        "CardDataKeySerialNumber": {
          "type": "string"
        },
        "EncryptedFormat": {
          "type": "string",
          "enum": [
            "Default",
            "Format1",
            "Format2",
            "Format3",
            "Format4"
          ]
        },
        "CardNumber": {
          "type": "string"
        },
        "ExpirationMonth": {
          "type": "string"
        },
        "ExpirationYear": {
          "type": "string"
        }
      }
    },
    "Address": {
      "type": "object",
      "properties": {
        "BillingName": {
          "type": "string"
        },
        "BillingAddress1": {
          "type": "string"
        },
        "BillingAddress2": {
          "type": "string"
        },
        "BillingCity": {
          "type": "string"
        },
        "BillingState": {
          "type": "string"
        },
        "BillingZipcode": {
          "type": "string"
        },
        "BillingEmail": {
          "type": "string"
        },
        "BillingPhone": {
          "type": "string"
        },
        "ShippingName": {
          "type": "string"
        },
        "ShippingAddress1": {
          "type": "string"
        },
        "ShippingAddress2": {
          "type": "string"
        },
        "ShippingCity": {
          "type": "string"
        },
        "ShippingState": {
          "type": "string"
        },
        "ShippingZipcode": {
          "type": "string"
        },
        "ShippingEmail": {
          "type": "string"
        },
        "ShippingPhone": {
          "type": "string"
        }
      }
    },
    "RunFrequency": {
      "type": "string"
    },
    "ScheduledTaskStatus": {
      "type": "string"
    },
    "ScheduledTask": {
      "type": "object",
      "properties": {
        "ScheduledTaskReferenceNumber": {
          "type": "string"
        },
        "RunFrequency": {
          "type": "string"
        },
        "RunStartDate": {
          "type": "string"
        },
        "RunCycles": {
          "type": "string"
        },
        "RunUntilCancelFlag": {
          "type": "string"
        },
        "ScheduledTaskStatus": {
          "type": "string"
        },
        "ScheduledTaskGroupID": {
          "type": "string"
        },
        "ScheduledTaskName": {
          "type": "string"
        }
      }
    },
    "AutoRental": {
      "type": "object",
      "properties": {
        "AutoRentalAgreementNumber": {
          "type": "string"
        },
        "AutoRentalNoShowIndicator": {
          "type": "string"
        },
        "AutoRentalExtraChargesDetail": {
          "type": "string"
        },
        "AutoRentalPickupDate": {
          "type": "string"
        },
        "AutoRentalDropoffDate": {
          "type": "string"
        },
        "AutoRentalCustomerName": {
          "type": "string"
        },
        "AutoRentalReturnCity": {
          "type": "string"
        },
        "AutoRentalReturnState": {
          "type": "string"
        },
        "AutoRentalReturnLocationID": {
          "type": "string"
        },
        "AutoRentalDuration": {
          "type": "string"
        },
        "AutoRentalPickupLocation": {
          "type": "string"
        },
        "AutoRentalPickupCity": {
          "type": "string"
        },
        "AutoRentalPickupState": {
          "type": "string"
        },
        "AutoRentalPickupCountryCode": {
          "type": "string"
        },
        "AutoRentalPickupTime": {
          "type": "string"
        },
        "AutoRentalReturnCountryCode": {
          "type": "string"
        },
        "AutoRentalReturnDate": {
          "type": "string"
        },
        "AutoRentalReturnTime": {
          "type": "string"
        },
        "AutoRentalVehicleClassCode": {
          "type": "string"
        },
        "AutoRentalDistance": {
          "type": "string"
        },
        "AutoRentalDistanceUnit": {
          "type": "string"
        },
        "AutoRentalAuditAdjustmentCode": {
          "type": "string"
        },
        "AutoRentalAuditAdjustmentAmount": {
          "type": "string"
        }
      }
    },
    "Healthcare": {
      "type": "object",
      "properties": {
        "HealthcareFlag": {
          "type": "string"
        },
        "HealthcareFirstAccountType": {
          "type": "string"
        },
        "HealthcareFirstAmountType": {
          "type": "string"
        },
        "HealthcareFirstCurrencyCode": {
          "type": "string"
        },
        "HealthcareFirstAmountSign": {
          "type": "string"
        },
        "HealthcareFirstAmount": {
          "type": "string"
        },
        "HealthcareSecondAccountType": {
          "type": "string"
        },
        "HealthcareSecondAmountType": {
          "type": "string"
        },
        "HealthcareSecondCurrencyCode": {
          "type": "string"
        },
        "HealthcareSecondAmountSign": {
          "type": "string"
        },
        "HealthcareSecondAmount": {
          "type": "string"
        },
        "HealthcareThirdAccountType": {
          "type": "string"
        },
        "HealthcareThirdAmountType": {
          "type": "string"
        },
        "HealthcareThirdCurrencyCode": {
          "type": "string"
        },
        "HealthcareThirdAmountSign": {
          "type": "string"
        },
        "HealthcareThirdAmount": {
          "type": "string"
        },
        "HealthcareFourthAccountType": {
          "type": "string"
        },
        "HealthcareFourthAmountType": {
          "type": "string"
        },
        "HealthcareFourthCurrencyCode": {
          "type": "string"
        },
        "HealthcareFourthAmountSign": {
          "type": "string"
        },
        "HealthcareFourthAmount": {
          "type": "string"
        }
      }
    },
    "Lodging": {
      "type": "object",
      "properties": {
        "LodgingAgreementNumber": {
          "type": "string"
        },
        "LodgingCheckInDate": {
          "type": "string"
        },
        "LodgingCheckOutDate": {
          "type": "string"
        },
        "LodgingRoomAmount": {
          "type": "string"
        },
        "LodgingRoomTax": {
          "type": "string"
        },
        "LodgingNoShowIndicator": {
          "type": "string"
        },
        "LodgingDuration": {
          "type": "string"
        },
        "LodgingCustomerName": {
          "type": "string"
        },
        "LodgingClientCode": {
          "type": "string"
        },
        "LodgingExtraChargesDetail": {
          "type": "string"
        },
        "LodgingExtraChargesAmounts": {
          "type": "string"
        },
        "LodgingPrestigiousPropertyCode": {
          "type": "string"
        },
        "LodgingSpecialProgramCode": {
          "type": "string"
        },
        "LodgingChargeType": {
          "type": "string"
        }
      }
    },
    "EnhancedData": {
      "type": "object",
      "properties": {
        "MerchantVATRegistrationNumber": {
          "type": "string"
        },
        "CustomerVATRegistrationNumber": {
          "type": "string"
        },
        "SummaryCommodityCode": {
          "type": "string"
        },
        "DiscountAmount": {
          "type": "string"
        },
        "FreightAmount": {
          "type": "string"
        },
        "DutyAmount": {
          "type": "string"
        },
        "DestinationZIPCode": {
          "type": "string"
        },
        "ShipFromZIPCode": {
          "type": "string"
        },
        "DestinationCountryCode": {
          "type": "string"
        },
        "UniqueVATInvoiceReferenceNumber": {
          "type": "string"
        },
        "OrderDate": {
          "type": "string"
        },
        "VATAmount": {
          "type": "string"
        },
        "VATRate": {
          "type": "string"
        },
        "LineItemCount": {
          "type": "string"
        },
        "AlternateTaxAmount": {
          "type": "string"
        },
        "NationalTaxAmount": {
          "type": "string"
        },
        "RequesterName": {
          "type": "string"
        },
        "RequesterCityName": {
          "type": "string"
        },
        "RequesterStateProvinceCode": {
          "type": "string"
        },
        "RequesterPostalCode": {
          "type": "string"
        },
        "RequesterCountryCode": {
          "type": "string"
        },
        "LineItemDetail": {
          "$ref": "#/definitions/LineItemDetail"
        }
      }
    },
    "LineItemDetail": {
      "type": "array",
      "items": {
        "$ref": "#/definitions/LineItem"
      },
      "minItems": 1,
      "maxItems": 50
    },
    "LineItem": {
      "type": "object",
      "properties": {
        "ItemCommodityCode": {
          "type": "string",
          "maxLength": 12
        },
        "ItemDescription": {
          "type": "string",
          "maxLength": 35
        },
        "ProductCode": {
          "type": "string",
          "maxLength": 12
        },
        "Quantity": {
          "type": "string",
          "maxLength": 12
        },
        "UnitOfMeasure": {
          "type": "string",
          "maxLength": 12
        },
        "UnitCost": {
          "type": "string",
          "maxLength": 12
        },
        "LineItemVATAmount": {
          "type": "string",
          "maxLength": 12
        },
        "LineItemVATRate": {
          "type": "string",
          "maxLength": 12
        },
        "LineItemDiscountAmount": {
          "type": "string",
          "maxLength": 12
        },
        "LineItemTotalAmount": {
          "type": "string",
          "maxLength": 12
        },
        "AlternateTaxIdentifier": {
          "type": "string",
          "maxLength": 15
        },
        "VATType": {
          "type": "string",
          "maxLength": 4
        },
        "DiscountCode": {
          "type": "string"
        },
        "NetGrossCode": {
          "type": "string"
        },
        "ExtendedItemAmount": {
          "type": "string",
          "maxLength": 12
        },
        "DebitCreditCode": {
          "type": "string"
        },
        "ItemDiscountRate": {
          "type": "string",
          "maxLength": 12
        }
      },
      "required": [
        "ItemCommodityCode",
        "ItemDescription",
        "ProductCode",
        "Quantity",
        "UnitOfMeasure",
        "UnitCost",
        "LineItemVATAmount",
        "LineItemVATRate",
        "LineItemDiscountAmount",
        "LineItemTotalAmount",
        "AlternateTaxIdentifier",
        "VATType",
        "DiscountCode",
        "NetGrossCode",
        "ExtendedItemAmount",
        "DebitCreditCode",
        "ItemDiscountRate"
      ]
    },
    "TerminalEncryptionFormat": {
      "type": "string",
      "enum": [
        "Default",
        "Format1",
        "Format2",
        "Format3",
        "Format4"
      ]
    },
    "PartialApprovalFlag": {
      "type": "boolean"
    },
    "CVVPresenceCode": {
      "type": "string",
      "enum": [
        "UseDefault",
        "NotProvided",
        "Provided",
        "Illegible",
        "CustomerIllegible"
      ]
    },
    "DuplicateOverrideFlag": {
      "type": "boolean"
    },
    "DuplicateCheckDisableFlag": {
      "type": "boolean"
    },
    "ReversalType": {
      "type": "string",
      "enum": [
        "System",
        "Full",
        "Partial"
      ]
    },
    "DemandDepositAccount": {
      "type": "object",
      "properties": {
        "AccountNumber": {
          "type": "string"
        },
        "RoutingNumber": {
          "type": "string"
        }
      },
      "required": [
        "AccountNumber",
        "RoutingNumber"
      ]
    },
    "ScheduledTaskID": {
      "type": "string"
    },
    "ScheduledTaskReferenceNumber": {
      "type": "string"
    },
    "ScheduledTaskName": {
      "type": "string"
    },
    "ScheduledTaskGroupID": {
      "type": "string"
    },
    "RunUntilCancelFlag": {
      "type": "string"
    },
    "ScheduledTaskParameters": {
      "type": "object",
      "properties": {
        "ScheduledTaskID": {
          "$ref": "#/definitions/ScheduledTaskID"
        },
        "ScheduledTaskReferenceNumber": {
          "$ref": "#/definitions/ScheduledTaskReferenceNumber"
        },
        "ScheduledTaskName": {
          "$ref": "#/definitions/ScheduledTaskName"
        },
        "ScheduledTaskGroupID": {
          "$ref": "#/definitions/ScheduledTaskGroupID"
        },
        "RunStartDate": {
          "type": "string"
        },
        "RunUntilCancelFlag": {
          "$ref": "#/definitions/RunUntilCancelFlag"
        },
        "RunFrequency": {
          "$ref": "#/definitions/RunFrequency"
        },
        "ScheduledTaskStatus": {
          "$ref": "#/definitions/ScheduledTaskStatus"
        },
        "ScheduledTaskQueryType": {
          "type": "string"
        },
        "ScheduledTaskRunStatus": {
          "type": "string"
        }
      }
    },
    "VaultID": {
      "type": "string"
    },
    "TokenProvider": {
      "type": "string",
      "enum": [
        "Null",
        "ExpressPASS",
        "OmniToken",
        "Paymetric",
        "TransArmor"
      ]
    }
  },
  "parameters": {},
  "responses": {}
}



