# Fluent-bit hands-on

## Dependencies
- fluent-bit 4.2
- Python 3.14
- uv 0.7.17
- pre-commit

## Organization
```sh
fluent-bit/config
├── input
│   ├── docker.conf
│   └── dummy.conf
├── output
│   ├── docker.conf
│   ├── dummy.conf
│   └── loki.conf
├── parsers
│   └── parsers.conf
└── services
    ├── dummys
            dummy.conf
        └── main.conf
```
*services*: Service configuration
*input*: Inputs configuration
*output*: Outputs configuration
*parsers*: Parsers configuration

## Service configuration example

```
@INCLUDE main.conf
@INCLUDE ../input/dummy.conf
@INCLUDE ../output/dummy.conf
#TODO: Fix permissions issue
#@INCLUDE ../input/docker.conf
#@INCLUDE ../output/docker.conf
@INCLUDE ../output/loki.conf
```
