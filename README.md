# Coder
Coder is a Self-Hosted Remote Development Platform
Coder shifts software development from local machines to the cloud. 
Onboard new developers in minutes, build code on powerful servers—all while keeping source code and data secure behind your firewall.
#### Official documentation link: https://coder.com/docs/v2/latest/install/install.sh
### Coder Install on Ubuntu 20.04 LTS
To install, run:

    # This will automatically use supported package managers when available
    curl -fsSL https://coder.com/install.sh | sh

### System packages
If you've installed Coder via a system package Coder, you can configure the server by setting the following variables in /etc/coder.d/coder.env:

    # String. Specifies the external URL (HTTP/S) to access Coder.
    CODER_ACCESS_URL=https://coder.example.com
    
    # String. Address to serve the API and dashboard.
    CODER_HTTP_ADDRESS=0.0.0.0:3000
    
    # String. The URL of a PostgreSQL database to connect to. If empty, PostgreSQL binaries
    # will be downloaded from Maven (https://repo1.maven.org/maven2) and store all
    # data in the config root. Access the built-in database with "coder server postgres-builtin-url".
    CODER_PG_CONNECTION_URL=
    
    # Boolean. Specifies if TLS will be enabled.
    CODER_TLS_ENABLE=
    
    # If CODER_TLS_ENABLE=true, also set:
    CODER_TLS_ADDRESS=0.0.0.0:3443
    
    # String. Specifies the path to the certificate for TLS. It requires a PEM-encoded file.
    # To configure the listener to use a CA certificate, concatenate the primary
    # certificate and the CA certificate together. The primary certificate should
    # appear first in the combined file.
    CODER_TLS_CERT_FILE=
    
    # String. Specifies the path to the private key for the certificate. It requires a
    # PEM-encoded file.
    CODER_TLS_KEY_FILE=
    
# To run Coder as a system service on the host:

    # Use systemd to start Coder now and on reboot
    sudo systemctl enable --now coder 
    # View the logs to ensure a successful start
    journalctl -u coder.service -b
    
##### To restart Coder after applying system changes:
    sudo systemctl restart coder
    
### After installing, use the in-terminal instructions to start the Coder
* By default, the Coder server runs on http://127.0.0.1:3000
* Open your web browser and type your IP with 3000 port you will get Coder Web Interface.

# Now Install Code-Server to run the following command below:
    curl -fsSL https://code-server.dev/install.sh | sh
##### Debian, Ubuntu
The standalone arm64 .deb does not support Ubuntu 16.04 or earlier. Please upgrade or build with npm.

    curl -fOL https://github.com/coder/code-server/releases/download/v$VERSION/code-server_${VERSION}_amd64.deb
    sudo dpkg -i code-server_${VERSION}_amd64.deb
    sudo systemctl enable --now code-server@$USER
Now visit http://127.0.0.1:8080. Your password is in ~/.config/code-server/config.yaml
