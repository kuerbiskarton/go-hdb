go-hdb
======

[![GoDoc](https://godoc.org/github.com/SAP/go-hdb/driver?status.png)](https://godoc.org/github.com/SAP/go-hdb/driver)
[![Go Report Card](https://goreportcard.com/badge/github.com/SAP/go-hdb)](https://goreportcard.com/report/github.com/SAP/go-hdb)
[![REUSE status](https://api.reuse.software/badge/git.fsfe.org/reuse/api)](https://api.reuse.software/info/git.fsfe.org/reuse/api)
![](https://github.com/SAP/go-hdb/workflows/build/badge.svg)

Go-hdb is a native Go (golang) HANA database driver for Go's sql package. It implements the SAP HANA SQL command network protocol:  
<http://help.sap.com/hana/SAP_HANA_SQL_Command_Network_Protocol_Reference_en.pdf>

For the official SAP HANA client Go support (not this database driver) please see [SAP Help Portal](https://help.sap.com/viewer/0eec0d68141541d1b07893a39944924e/2.0.02/en-US/0ffbe86c9d9f44338441829c6bee15e6.html).

## Installation

```
go get github.com/SAP/go-hdb/driver
```

## Building

To build go-hdb you need to have a working Go environment with [version 1.15 or higher installed](https://golang.org/dl/).

## Documentation

API documentation and documented examples can be found at <https://godoc.org/github.com/SAP/go-hdb/driver>.

## Tests

To run the driver tests a HANA Database server is required. The test user must have privileges to create database schemas.

```
go test -dsn hdb://user:password@host:port
```

## Features

* Native Go implementation (no C libraries, CGO).
* Go <http://golang.org/pkg/database/sql> package compliant.
* Support of database/sql/driver Execer and Queryer interface for parameter free statements and queries.
* Support of bulk inserts.
* Support of UTF-8 to / from CESU-8 encodings for HANA Unicode types.
* Built-in support of HANA decimals as Go rational numbers <http://golang.org/pkg/math/big>.
* Support of Large Object streaming.
* Support of Stored Procedures with table output parameters.
* Support of TLS TCP connections.
* Support of little-endian (e.g. amd64) and big-endian architectures (e.g. s390x).
* Support of [driver connector](https://golang.org/pkg/database/sql/driver/#Connector).
* Support of [PBKDF2](https://tools.ietf.org/html/rfc2898) authentication as default and standard user / password as fallback.

## Dependencies

* Please see [go.mod](https://github.com/SAP/go-hdb/blob/main/go.mod).
