# Ansible role to install the Microsoft Operations Manager Agent & Dependency Agent on Linux

The Microsoft Operations Manager agent connects to an Azure Operations Manager Suite (OMS) workspace, a part of the [Microsoft Azure Monitor solution](https://docs.microsoft.com/en-us/azure/azure-monitor/). The solution allows you to collect and analyze telemetry to maximize performance and availability of your resources. For more information about Azure monitor refer to the [Microsoft documentation](https://docs.microsoft.com/en-us/azure/azure-monitor/overview)

This role installs the OMS agent and (optionally) the dependency agent.

## Requirements

To make use of the agents, you need a configured OMS workspace. You need a `workspace ID` and a `workspace key`. For more information on how to create a workspace, consult the Microsoft [documentation](https://docs.microsoft.com/en-us/azure/azure-monitor/learn/quick-create-workspace)

## Role Variables

| Variable                  | Default | Comments (type)                                                                |
| ---                       | ---     | ---                                                                            |
| `workspace_id`            | -       | Required. The workspace ID                                                     |
| `workspace_key`           | -       | Required. The workspace Key                                                    |
| `purge_oms_config`        | `False` | Optional. Clear out any existing OMS agent config and re-install it            |
| `install_dependencyagent` | `True`  | Optional. Whether to install the dependency agent, False will remove the agent |

## Dependencies

No specific dependencies.

## Example Playbook

An example on how to use this role

```json
---
- hosts: all
  roles:
    - svendewindt.omsagentlinux
  vars:
    - workspace_id: '260adb3c-007d-4704-a645-c8f2def53718'
    - workspace_key: '1111254hBqVldHplArZCuBlWoy6sJtJP8XSaLPHKNQYdVtrhOuwG/w0Cuc+F9HbPLEj6AvPVUKt6i/uXWAnooQ=='
```

## License

2-clause BSD license, see [LICENSE.md](LICENSE.md)

## Contributors

* [Sven de Windt](https://github.com/svendewindt)
* [DaveB93](https://github.com/DaveB93)
