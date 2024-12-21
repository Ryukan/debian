Doc: https://medium.com/@bigdsdojo/utilizing-nvidia-gpu-for-specific-applications-on-linux-a-simple-script-approach-6bb122cc5b3c


Creare file:

/usr/local/bin/nc-run


#!/bin/bash

# Check if at least one argument is provided
if [[ $# -lt 1 ]]; then
    echo "Usage: $0 <program> [arguments]"
    exit 1
fi

# Get the program name and the arguments
program=$1
shift  # Shift the arguments to remove the first one
arguments="$@"

# Run the program with the NVIDIA GPU
__NV_PRIME_RENDER_OFFLOAD=1 __GLX_VENDOR_LIBRARY_NAME=nvidia $program $arguments



chmod +x /usr/local/bin/nc-run

Modificare il file .desktop

/usr/share/applications/....

Esempio:
#Exec=/usr/bin/vmware %U
Exec=/usr/local/bin/nv-run /usr/bin/vmware %U



Per vedere se effettivamente usa Nvidia
controllare nvidia-smi