
# Hosts CLI

`hostscli` is a `BASH` script that allows easy manipulation of the records in a hosts file, e.g. `/etc/hosts`

## Usage
```
Usage: hosts-cli {-D|-I|-R} -i <ip address> -h <hostname> [-f <filename>]

Actions:
  -D, --delete       Delete all matching records from the hosts file
                     If only IP or hostname is provided, all records matching will be deleted. If both are provided only an exact match is deleted.
  -I, --insert       Insert a new record into the hosts file.
  -R, --replace      Replace a host record in the hosts file with the new IP address.

Options:
  -i <ip_address>    The IP address of the record
  -h <hostname>      The hostname address of the record
  -f <filename>      The hosts file to operate on (defaults to /etc/hosts)

```

## Examples 
### Inserting a new record
This command adds a new line to the hosts file

```bash
hosts-cli -I -i 1.1.1.1 -h one.x.io
```

### Replacing an existing record
This command replaces a line in the hosts file

```bash
hosts-cli -R -i 2.2.2.2 -h one.x.io
```

### Deleting an exact record
This command deletes a record that exactly matches this IP and hostname, e.g.
```bash
hosts-cli -D -i 1.1.1.1 -h one.x.io
```

### Deleting all matching IP records
This command deletes all records that match an IP
```bash
hosts-cli -D -i 1.1.1.1
```

### Deleting all matching hostname records
This command deletes all records that match a hostname

```bash
hosts-cli -D -h one.x.io 
```


