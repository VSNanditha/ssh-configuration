# ssh-configuration

## Setup

1. cd ~/.ssh
2. vim config
3. Add the specified and required options in the file

## Options Explained

### IdentityFile 
	* rd_rsa file usually present at ~/.ssh/rd_rsa. 
	* It contains the private keys for any host connection which requires a key authentication.

### ServerAliveInterval
	* Used to keep a connection alive during inactive period as ssh connection automatically disconnects after some inactivity.
	* Sends a null packet to the remote for every specified seconds

### LogLevel
	* Used to increase or decrease the log verbosity level of any remote connection on the client-side.
	* Available options - QUIET/FATAL/ERROR/INFO/VERBOSE/DEBUG/DEBUG1/DEBUG2/DEBUG3
	* Default is INFO

### StrictHostKeyChecking
	* Used to define the behavior when a new host connection is requested.
	* Available options
		* yes - New host keys will never be automatically added to the ~/.ssh/known_hosts file. Host connections with changed host keys are refused. Provides maximum protection against man-in-the-middle attacks.
		* accept-new - New host keys will be automatically added to user known hosts file. Host connections with changed host keys are refused.
		* no/off - New host keys will be automatically added to user known hosts file. Host connections with changed host keys are accepted.
		* ask - Default. New host keys will be added to user known hosts file only after user confirmation. Host connections with changed host keys are refused. Host keys of known hosts will be automatically verified in all cases.

### VisualHostKey
	* Used to display the ASCII representation of the host ket upon connection to remote in addition to fingerprint string at login and for unknown hosts.
	* Available options - yes/no

### LocalForward
	* Used to specify that a TCP port on the local machine be forwarded over the secure channel to the specified host and port from the remote machine.
	* IPv6 addresses can be specified by enclosing addresses in square brackets.
	* To restrict the connecting interfaces, provide the bind address. This will be used to bind the connection to the specified address. If not specified, then the forwarding can be requested to be listened by any interface.

### RemoteForward
	* Used to specify that a TCP port on remote machine be forwarded over the secure channel.
	* The remote port can either be forwarded to local port or it can act as a remote client and forward the port to a specific remote. 
	* If a destination is not specified, it will act as a SOCKS proxy for all connections.
