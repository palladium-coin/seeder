## Quick Setup

These instructions are for Ubuntu/Debian-based systems.

### 1. Install Prerequisites

```bash
sudo apt-get install git build-essential libboost-all-dev libssl-dev libcurl4-openssl-dev libconfig++-dev
````

### 2\. Download Source

```bash
git clone [https://github.com/palladium-coin/palladium.git](https://github.com/palladium-coin/seeder.git)
cd seeder
```

### 3\. Configure Seeder

Copy the template and edit the new file.

```bash
nano ./settings.conf
```


### 4\. Build from Source

```bash
make
```

This will create the `dnsseed` binary.

## Usage

To run the seeder, you must provide your hostnames. The seeder must be run with `sudo` to use the default DNS port (53).

```bash
sudo ./dnsseed -h seed.palladium-coin.com -n ns1.palladium-coin.com -m your-email@example.com
```

### :exclamation: Ubuntu Users (systemd-resolved)

On modern Ubuntu systems, `systemd-resolved` already uses port 53. This will cause `dnsseed` to fail.

The recommended solution is to force `dnsseed` to bind only to your server's public IP address using the `-a` flag:

```bash
sudo ./dnsseed -h seed.palladium-coin.com -n ns1.palladium-coin.com -a YOUR_SERVER_IP -m your-email@example.com
```

```
```