{
    "_comment": "DO NOT EDIT: FILE GENERATED AUTOMATICALLY BY PTERODACTYL PANEL - PTERODACTYL.IO",
    "meta": {
        "version": "PTDL_v2",
        "update_url": null
    },
    "exported_at": "2024-12-19T00:00:00+00:00",
    "name": "Bash Shell Generic",
    "author": "your-email@example.com",
    "description": "A generic bash shell environment.\r\n\r\nThis egg runs bash scripts. It allows for execution of user-provided shell scripts and commands.",
    "features": null,
    "docker_images": {
        "Ubuntu 22.04": "ghcr.io/parkervcp/yolks:ubuntu_22_04",
        "Ubuntu 20.04": "ghcr.io/parkervcp/yolks:ubuntu_20_04",
        "Alpine 3.18": "ghcr.io/parkervcp/yolks:alpine_3_18"
    },
    "file_denylist": [],
    "startup": "# Start the shell session with a custom script or default to bash\r\nif [[ -f /home/container/start.sh ]]; then\r\n    bash /home/container/start.sh\r\nelse\r\n    bash\r\nfi",
    "config": {
        "files": "{}",
        "startup": "{\r\n    \"done\": [\r\n        \"Bash shell is running.\"\r\n    ]\r\n}",
        "logs": "{}",
        "stop": "^C"
    },
    "scripts": {
        "installation": {
            "script": "#!/bin/bash\r\n# Bash Shell Environment Setup\r\n#\r\n# Server Files: /mnt/server\r\napt update\r\napt install -y bash curl git unzip\r\n\r\n# Optionally install additional tools\r\nif [[ ! -z ${ADDITIONAL_TOOLS} ]]; then\r\n    apt install -y ${ADDITIONAL_TOOLS}\r\nfi\r\n\r\n# Set up working directory\r\nmkdir -p /mnt/server\r\ncd /mnt/server\r\n\r\n# Clone any git repo if GIT_ADDRESS is provided\r\nif [[ ! -z ${GIT_ADDRESS} ]]; then\r\n    git clone ${GIT_ADDRESS} .\r\nfi\r\n\r\necho \"Installation complete\"\r\nexit 0",
            "container": "ubuntu:22.04",
            "entrypoint": "bash"
        }
    },
    "variables": [
        {
            "name": "Git Repo Address",
            "description": "GitHub Repo to clone\r\n\r\nI.E. https://github.com/yourname/repo_name",
            "env_variable": "GIT_ADDRESS",
            "default_value": "",
            "user_viewable": true,
            "user_editable": true,
            "rules": "nullable|string",
            "field_type": "text"
        },
        {
            "name": "Additional Tools",
            "description": "Comma-separated list of tools to install (e.g., curl, vim, htop).",
            "env_variable": "ADDITIONAL_TOOLS",
            "default_value": "",
            "user_viewable": true,
            "user_editable": true,
            "rules": "nullable|string",
            "field_type": "text"
        },
        {
            "name": "User Upload Files",
            "description": "If you want to upload custom files for your environment.",
            "env_variable": "USER_UPLOAD",
            "default_value": "0",
            "user_viewable": true,
            "user_editable": true,
            "rules": "required|boolean",
            "field_type": "text"
        },
        {
            "name": "Auto Update",
            "description": "Auto-update the repository on startup when a GitHub repository is used.",
            "env_variable": "AUTO_UPDATE",
            "default_value": "0",
            "user_viewable": true,
            "user_editable": true,
            "rules": "required|boolean",
            "field_type": "text"
        }
    ]
}
