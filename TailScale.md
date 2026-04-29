# TailScale Setup

## Initial Config
- Create an Account
- Install the client on the local (client) machine.
- Sign in to the client and verify you can view the dashboard

## Setting up the remote host
- Download and install the TailScale Client
- Sign in with your username and password

## Setting up subnet routing
### Host Machine (On the subnet you want to access)
- Modify the following reg key, changing the `IPEnableRouter` value to 1
```
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters
```
- Open an administrative command prompt share the route:
```cmd
tailscale set --advertise-routes=<net>/<mask>

# Example
tailscale set --advertise-routes=192.0.2.0/24
```
> Multiple subnets can be shared with a comma

- Subnet routing is now in place. Client machine merely needs to connect to the machine and it will have the entire subnet.


