[![MseeP.ai Security Assessment Badge](https://mseep.net/pr/stoyky-mitre-attack-mcp-badge.png)](https://mseep.ai/app/stoyky-mitre-attack-mcp)

<h1 align="center">
  <br>
  MITRE ATT&CK MCP Server
  <br>
</h1>

<h4 align="center">A Model-Context Protocol server for the MITRE ATT&CK knowledge base</h4>

<p align="center">
  <a href="#key-features">Key Features</a> •
  <a href="#installation">Installation</a> •
  <a href="#how-to-use">How To Use</a> •
  <a href="#use-cases">Use Cases</a> •
  <a href="#credits">Credits</a>
</p>

## Key Features

* 50+ Tools for MITRE ATT&CK Querying
  * Comprehensive access to the MITRE ATT&CK knowledge base through structured API tools
* Automatic ATT&CK Navigator Layer Generation
  * Generate visual representations of techniques used by threat actors
* Threat Actor and Malware Attribution
  * Query relationships between malware, threat actors, and techniques
* Technique Overlap Analysis
  * Compare techniques used by different threat actors or malware families

## Installation

To clone and run this server, you'll need [Git](https://git-scm.com), [Python](https://www.python.org/), and [PipX](https://github.com/pypa/pipx) installed on your computer.

1. Ensure Git, Python, and PipX have been installed using their official respective installation instructions for Windows/Mac/Linux
2. Install the MCP Server using PipX
   
```bash
pipx install git+https://github.com/stoyky/mitre-attack-mcp
```

## How To Use

### Configure with Claude AI Desktop

1. Open Claude's MCP server configuration file.

#### Windows

```
C:\Users\[YourUsername]\AppData\Roaming\Claude\claude_desktop_config.json
# or
C:\Users\[YourUsername]\AppData\Local\AnthropicClaude\claude_desktop_config.json
```

#### Linux / Mac

```bash
~/.config/Claude/claude_desktop_config.json
```

2. Add the following to that file if it doesn't already exist. If it already exists, merge the two JSON structures accordingly.

```json
{
  "mcpServers": {
    "mitre-attack": {
      "command": "mitre-attack-mcp",
      "args": [
      ]
    }
  }
}
```

**Note**: By default the MCP server stores the mitre-related data in the current users default cache directory. You can specify a custom data directory to use with the following config:

```json
{
  "mcpServers": {
    "mitre-attack": {
      "command": "mitre-attack-mcp",
      "args": [
        "--data-dir",
        "<path-to-data-dir>"
      ]
    }
  }
}
```

## Changelog

* v1.0.2 - Now installable via PipX on Windows, Mac, and Linux. "data directory" argument is now optional and will use the default cache directory if omitted.
* v1.0.0 - Initial release
* V1.0.1 - Improved robustness of layer metadata generation and error handling in layer generation function

## Use Cases

* Query for detailed information about specific malware, tactics, or techniques
* Discover relationships between threat actors and their tools
* Generate visual ATT&CK Navigator layers for threat analysis
* Find campaign overlaps between different threat actors
* Identify common techniques used by multiple malware families

Please see my [blog](https://www.remyjaspers.com/blog/mitre_attack_mcp_server/) for more information and examples.

## Credits

* [MITRE ATT&CK](https://attack.mitre.org/) - Knowledge base of adversary tactics and techniques
* [MITRE ATT&CK Python](https://github.com/mitre-attack/mitreattack-python) - Python library to interact with the knowledge base
* [ATT&CK Navigator](https://github.com/mitre-attack/attack-navigator) - Tool for visualizing ATT&CK matrices
* [Anthropic](https://www.anthropic.com/) - Developers of the Model-Context Protocol

---

> Created by [Remy Jaspers](https://github.com/stoyky)
