# Viewing Systemd Services on Debian 12

To view all services managed by systemd on your freshly installed Debian 12 system, you have several options depending on what information you need. Here are the most useful commands:

## Basic Service Listing Commands

### List All Units (Including Services)

```bash
systemctl list-units
```

This shows all active units (not just services). Units are systemd's objects that it knows about and manages, including services, sockets, devices, and more.

### List Only Services

```bash
systemctl list-units --type=service
```

This filters the output to show only service units, which is probably what you're looking for.

### List All Services (Including Inactive)

```bash
systemctl list-units --type=service --all
```

The `--all` flag shows both active and inactive services, giving you a complete picture of what's installed.

## More Detailed Information

### Status of All Services

```bash
systemctl status
```

This provides an overview of your system status, including running services.

### Detailed Service List

```bash
systemctl list-units --type=service --all --no-pager
```

The `--no-pager` option prevents output from being piped through a pager, showing everything at once.

### Check Status of a Specific Service

If you want details about a particular service:

```bash
systemctl status service_name
```

For example: `systemctl status ssh`

## Understanding Service States

In the output, you'll see services with different states:

- **active (running)**: Service is running normally
- **active (exited)**: Service ran successfully and completed (one-shot services)
- **inactive**: Service is installed but not running
- **failed**: Service attempted to start but failed

## Advanced Listing Options

### List Failed Services

```bash
systemctl --failed
```

This is helpful to quickly identify services that are having problems.

### List Services That Start at Boot

```bash
systemctl list-unit-files --type=service | grep enabled
```

This shows which services are configured to start automatically when your system boots up.

### List Dependencies

To see what other services a particular service depends on:

```bash
systemctl list-dependencies service_name
```

## Tips for Working with Services

After finding services, you might want to:

- Start a service: `sudo systemctl start service_name`
- Stop a service: `sudo systemctl stop service_name`
- Enable a service (start at boot): `sudo systemctl enable service_name`
- Disable a service (don't start at boot): `sudo systemctl disable service_name`

These commands typically require sudo privileges since they modify system behavior.

Does this help with what you're trying to do with your new Debian installation?
