# Queue Monitor

This webhook will check the queue status and show the status of the queue if changes happen.

This webhook monitors queue status and reports any changes.

#### It can display more than one queue status at a time.


!!! danger "New Update: Queue Monitor payload "

    You now receive an array of update objects. Each object contains exactly one user entry keyed by `userId` and includes the user's `agentstatus` and a `queues` map with details per `queueId`.

    - **userId level**: `agentstatus` shows one of: `WRAP_UP`, `UNAVAILABLE`, `SIGN_OUT`.
    - **queues map (by queueId)**: Each queue includes `queuename`, `extension`, and `status` where `status` is either `active` or `inactive`.
    - **Full snapshot semantics**: Every update delivers the full set of queues for the user, even when a given queue did not change. Use this to keep your local state fully in sync without diffing.

    ### Example (full payload array)

    ```json
    [ # only agent status changed -> Different user 
      {
        "body": {
          "payload": "queue-monitor",
          "items": {
            "Y2lzY29zcGFyazovL3VzL1BFT1BMRS85NWIwZTU1Yi1iYmU0LTQyZDItYmNmMi0zZGNlMGU0MDE0M2E": {
              "agentstatus": "WRAP_UP",
              "queues": {
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvNmRhZjY5MGQtYmMzNi00OTM3LWI4NWQtMmJmMGZjN2YzMWRi": {
                  "queuename": "CQX Q1",
                  "extension": "284",
                  "status": "active"
                },
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvNTk5YTk1MTUtMmQ3MS00ZWI1LTkyZTQtNWU3NWY5MDk4NDg4": {
                  "queuename": "FWD CXQ",
                  "extension": "111",
                  "status": "active"
                },
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvNTdiZDFjZjItNTA3NS00NGFkLWI5MTItZjg3YWY1ZDVhYWJl": {
                  "queuename": "CQX2 .",
                  "extension": "333",
                  "status": "inactive"
                },
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvNmQ2MTgyYTktNjMzMi00M2Q5LThmYTgtN2VkZTliMzRmMGY2": {
                  "queuename": "Sales Q",
                  "extension": "274",
                  "status": "active"
                },
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvM2E3YTdlOGEtNjhlMC00NjE0LWJiMzgtMjhmMjc3OGI5Mzcw": {
                  "queuename": "Webex Dev",
                  "extension": "500",
                  "status": "active"
                }
              }
            }
          }
        }
      },
      { # FWD CXQ to inactive
        "body": {
          "payload": "queue-monitor",
          "items": {
            "Y2lzY29zcGFyazovL3VzL1BFT1BMRS9hODA4YmVmYS05MTM4LTQ2MWMtYjlhZi0zOTJjNzg0ZTBjMWE": {
              "agentstatus": "WRAP_UP",
              "queues": {
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvNmRhZjY5MGQtYmMzNi00OTM3LWI4NWQtMmJmMGZjN2YzMWRi": {
                  "queuename": "CQX Q1",
                  "extension": "284",
                  "status": "active"
                },
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvNTk5YTk1MTUtMmQ3MS00ZWI1LTkyZTQtNWU3NWY5MDk4NDg4": {
                  "queuename": "FWD CXQ",
                  "extension": "111",
                  "status": "inactive"
                },
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvNmQ2MTgyYTktNjMzMi00M2Q5LThmYTgtN2VkZTliMzRmMGY2": {
                  "queuename": "Sales Q",
                  "extension": "274",
                  "status": "active"
                },
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvM2E3YTdlOGEtNjhlMC00NjE0LWJiMzgtMjhmMjc3OGI5Mzcw": {
                  "queuename": "Webex Dev",
                  "extension": "500",
                  "status": "active"
                }
              }
            }
          }
        }
      },
      { # Agent Status Changed 
        "body": {
          "payload": "queue-monitor",
          "items": {
            "Y2lzY29zcGFyazovL3VzL1BFT1BMRS9hODA4YmVmYS05MTM4LTQ2MWMtYjlhZi0zOTJjNzg0ZTBjMWE": {
              "agentstatus": "UNAVAILABLE",
              "queues": {
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvNmRhZjY5MGQtYmMzNi00OTM3LWI4NWQtMmJmMGZjN2YzMWRi": {
                  "queuename": "CQX Q1",
                  "extension": "284",
                  "status": "active"
                },
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvNTk5YTk1MTUtMmQ3MS00ZWI1LTkyZTQtNWU3NWY5MDk4NDg4": {
                  "queuename": "FWD CXQ",
                  "extension": "111",
                  "status": "inactive"
                },
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvNmQ2MTgyYTktNjMzMi00M2Q5LThmYTgtN2VkZTliMzRmMGY2": {
                  "queuename": "Sales Q",
                  "extension": "274",
                  "status": "active"
                },
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvM2E3YTdlOGEtNjhlMC00NjE0LWJiMzgtMjhmMjc3OGI5Mzcw": {
                  "queuename": "Webex Dev",
                  "extension": "500",
                  "status": "active"
                }
              }
            }
          }
        }
      },
      { # Agent Status Changed 
        "body": {
          "payload": "queue-monitor",
          "items": {
            "Y2lzY29zcGFyazovL3VzL1BFT1BMRS9hODA4YmVmYS05MTM4LTQ2MWMtYjlhZi0zOTJjNzg0ZTBjMWE": {
              "agentstatus": "WRAP_UP",
              "queues": {
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvNmRhZjY5MGQtYmMzNi00OTM3LWI4NWQtMmJmMGZjN2YzMWRi": {
                  "queuename": "CQX Q1",
                  "extension": "284",
                  "status": "active"
                },
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvNTk5YTk1MTUtMmQ3MS00ZWI1LTkyZTQtNWU3NWY5MDk4NDg4": {
                  "queuename": "FWD CXQ",
                  "extension": "111",
                  "status": "inactive"
                },
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvNmQ2MTgyYTktNjMzMi00M2Q5LThmYTgtN2VkZTliMzRmMGY2": {
                  "queuename": "Sales Q",
                  "extension": "274",
                  "status": "active"
                },
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvM2E3YTdlOGEtNjhlMC00NjE0LWJiMzgtMjhmMjc3OGI5Mzcw": {
                  "queuename": "Webex Dev",
                  "extension": "500",
                  "status": "active"
                }
              }
            }
          }
        }
      },
      {# Multiple Queues Got Inactive 
        "body": {
          "payload": "queue-monitor",
          "items": {
            "Y2lzY29zcGFyazovL3VzL1BFT1BMRS9hODA4YmVmYS05MTM4LTQ2MWMtYjlhZi0zOTJjNzg0ZTBjMWE": {
              "agentstatus": "WRAP_UP",
              "queues": {
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvNmRhZjY5MGQtYmMzNi00OTM3LWI4NWQtMmJmMGZjN2YzMWRi": {
                  "queuename": "CQX Q1",
                  "extension": "284",
                  "status": "inactive"
                },
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvNTk5YTk1MTUtMmQ3MS00ZWI1LTkyZTQtNWU3NWY5MDk4NDg4": {
                  "queuename": "FWD CXQ",
                  "extension": "111",
                  "status": "inactive"
                },
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvNmQ2MTgyYTktNjMzMi00M2Q5LThmYTgtN2VkZTliMzRmMGY2": {
                  "queuename": "Sales Q",
                  "extension": "274",
                  "status": "inactive"
                },
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvM2E3YTdlOGEtNjhlMC00NjE0LWJiMzgtMjhmMjc3OGI5Mzcw": {
                  "queuename": "Webex Dev",
                  "extension": "500",
                  "status": "active"
                }
              }
            }
          }
        }
      },
      { # Agent Signed Out 
        "body": {
          "payload": "queue-monitor",
          "items": {
            "Y2lzY29zcGFyazovL3VzL1BFT1BMRS9hODA4YmVmYS05MTM4LTQ2MWMtYjlhZi0zOTJjNzg0ZTBjMWE": {
              "agentstatus": "SIGN_OUT",
              "queues": {
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvNmRhZjY5MGQtYmMzNi00OTM3LWI4NWQtMmJmMGZjN2YzMWRi": {
                  "queuename": "CQX Q1",
                  "extension": "284",
                  "status": "inactive"
                },
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvNTk5YTk1MTUtMmQ3MS00ZWI1LTkyZTQtNWU3NWY5MDk4NDg4": {
                  "queuename": "FWD CXQ",
                  "extension": "111",
                  "status": "inactive"
                },
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvNmQ2MTgyYTktNjMzMi00M2Q5LThmYTgtN2VkZTliMzRmMGY2": {
                  "queuename": "Sales Q",
                  "extension": "274",
                  "status": "inactive"
                },
                "Y2lzY29zcGFyazovL3VzL0NBTExfUVVFVUUvM2E3YTdlOGEtNjhlMC00NjE0LWJiMzgtMjhmMjc3OGI5Mzcw": {
                  "queuename": "Webex Dev",
                  "extension": "500",
                  "status": "active"
                }
              }
            }
          }
        }
      }
    ]
    ```