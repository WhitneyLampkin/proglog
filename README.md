<h1 align="center" style="border-bottom: none">
    <a href="https://github.com/WhitneyLampkin/devscriber/blob/main/assets/default-img.png?raw=true" target="_blank">
        <img alt="" src="https://github.com/WhitneyLampkin/devscriber/blob/main/assets/default-img.png?raw=true" style="border-radius: 50%; height: 100px;">
    </a>
    <br>
    Proglog
</h1>

<hr />

<p align="center">
    Auto-generated by the <a href="https://github.com/WhitneyLampkin/devscriber" target="_blank">devscriber</a> command-line tool.
</p>

<div align="center">

![GitHub language count](https://img.shields.io/github/languages/count/WhitneyLampkin/proglog?label=Languages)
![GitHub contributors](https://img.shields.io/github/contributors/WhitneyLampkin/proglog?label=Contributors&color=yellow)
![GitHub repo size](https://img.shields.io/github/repo-size/WhitneyLampkin/proglog?label=Repo%20Size&color=teal)
![GitHub repo file count (file type)](https://img.shields.io/github/directory-file-count/WhitneyLampkin/proglog?label=Files&color=purple)

</div>

This GitHub repo has code examples from the [Distributed Services with Go]() O'Reilly book by Travis Jeffrey.

## Initial Setup

After cloning the repo, run the following:

```shell
make init
make gencert
make compile
```

## Usage

To run the program's API, execute the command below from proglog/cmd/server:

```shell
$ go run main.go
```

POST new records to the log:

```shell
$ curl -X POST localhost:8080 -d '{"record": {"value": "TGV0J3MgR28gIzEK"}}'
​$ curl -X POST localhost:8080 -d '{"record": {"value": "TGV0J3MgR28gIzIK"}}'
$ curl -X POST localhost:8080 -d '{"record": {"value": "TGV0J3MgR28gIzMK"}}'
```

GET records from the log:

```shell
 curl -X GET localhost:8080 -d '{"offset": [RECORD_OFFSET_#]}'
```

## Testing

```shell
make test
```

## Features

The project's features are as follows:

⭐ Chapter 1: JSON/HTTP commit log service that stores and retrieves records from an in-memory log.
<br />
⭐ Chapter 2: Protobuf fundamentals and using them to create a protocol buffer for the Record type.
<br />
⭐ Chapter 3: Writing a custom log package
<br />
⭐ Chapter 4: Serve Requests w/ gRPC
<br />
⭐ Chapter 5: Securing the Service w/ Mutual TLS Authentication
<br />
⭐ Chapter 6: Observing the System
<br />
⭐ Chapter 7: Adding Service Discovery
<br />
⭐ Chapter 8: Implementing Raft
<br />
⭐ Chapter 9: Discover Servers and Load Balance from the Client
<br />

## Notes

- Chapter 5 uses `go get` to install the cfssl tools. If this doesn't work, I recommend using `sudo apt install golang-cfssl` and `sudo apt install golang-cfssljson`.
- *Observability* - a measure of how well we understand a system's behavior or state based on external outputs.
- Types of Telemetry
    1. *Metrics* - measure numeric data over time (counters, histograms, gauges).
        - Google's 4 Golden Signals - latency, errors, traffic, saturation (L.E.T.S.).
    1. *Structured logs* - descriptions of events that have occurred in a system.
    1. *Traces* - details the request lifecycle as it flows through the system.
- Chapter 9: Load balancing strategies
    1. Server Proxying
        ![image](./assets/c9-server-proxying.png)
    1. External Load Balancing
        ![image](./assets/c9-external-loadbalancing.png)
    1. Client-side Balancing
        ![image](./assets/c9-client-loadbalancing.png)

## License

None

<h1 align="center" style="border-bottom: none; margin-top: 50px;">
    <a href="https://github.com/WhitneyLampkin/devscriber/blob/main/assets/default-img.png?raw=true" target="_blank">
        <img alt="" src="https://github.com/WhitneyLampkin/devscriber/blob/main/assets/default-img.png?raw=true" style="border-radius: 50%; height: 100px;">
    </a>
</h1>
