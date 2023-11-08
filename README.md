# rust-protobuf-pyo3-example

How to use Protocol Buffers (protobuf) as an interface (I/F) between Rust code (using pyo3) and Python code

## Directory structures

```bash
├── main.py  # python test script
├── proto  # protobuf definitions
│   └── function_a
│       └── v1
│           └── function.proto
├── proto_example  # python package
│   ├── __init__.py
│   └── generated  # python protobuf client
│       ├── __init__.py
│       └── function_a
│           └── v1
│               └── function_pb2.py
└── src  # rust crate
    ├── generated  # rust protobuf client
    │   ├── function_a
    │   │   ├── mod.rs
    │   │   └── v1
    │   │       ├── function.rs
    │   │       └── mod.rs
    │   └── mod.rs
    └── lib.rs
```

## Build

```bash
$ python setup.py develop
```

### Optional

```bash
$ python3 -m venv venv
$ source venv/bin/activate
(venv) $ python setup.py --help-commands # complete list of available commands for your specific package, ie python setup.py build etc. 
(venv) $ python setup.py develop # changes you make to the package's source code will immediately affect the installed package
```

## Testing

```bash
$ python main.py
[src/lib.rs:11] &req = descriptions: "hello from python"

rust response: descriptions: "hello from rust"

```
