# pyciphersuite

Get information related to cipher suites.

## Installation

```bash
python3 -m venv env && source env/bin/activate
(env) python3 -m pip install pyciphersuite
```

## Usage

List all available cipher suites:

```python
import pyciphersuite

suites = pyciphersuite.list_all_cs()
print(suites)
```

Display cipher suite information for the given IANA name:

```python
suite = pyciphersuite.display_cs("TLS_DH_anon_EXPORT_WITH_RC4_40_MD5")
print(suite)
```

Display cipher suites supported by the given TLS version:

```python
suites = pyciphersuite.display_cs_for_tls_version("12") # TLS version 1.2
print(suites)
```

Display cipher suites with the given security level:

```python
suites = pyciphersuite.display_cs_for_security_lvl("weak")
print(suites)
```

Display cipher suites supported by the given library:

```python
suites = pyciphersuite.display_cs_for_given_lib("gnutls")
print(suites)
```

List all available RFCs:

```python
rfcs = pyciphersuite.list_all_rfcs()
print(rfcs)
```

Display RFC with the given number:

```python
rfc = pyciphersuite.display_rfc("6367")
print(rfc)
```

## Purpose

I've been using ciphersuite APIs in a lot of my internally developed security scripts, and felt it was really redundant to write the same requests over and over, so I've decided to write
this small API wrapper. It will get rid of redundancies in my scripts and maybe help some other people too.

## License

[MIT](./LICENSE)
