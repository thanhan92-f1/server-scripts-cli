# Examples

Ready-to-run examples demonstrating `server-scripts-cli` features.

## 📁 Directory Structure

```
examples/
├── README.md                  # This file
├── manifest.example.yaml      # Sample manifest configuration
└── demo-scripts/              # 4 demonstration scripts
    ├── backup-example.sh
    ├── deploy-example.sh
    ├── health-check.sh
    └── monitoring-example.sh
```

## 🚀 Demo Scripts

| Script | Type | Description | Size |
|--------|------|-------------|------|
| [backup-example.sh](demo-scripts/backup-example.sh) | Admin | Scheduled backup with root privileges | 1.3K |
| [monitoring-example.sh](demo-scripts/monitoring-example.sh) | Report | System metrics collection | 1.1K |
| [health-check.sh](demo-scripts/health-check.sh) | Check | Service health validation | 1.2K |
| [deploy-example.sh](demo-scripts/deploy-example.sh) | Admin | Deployment automation | 1.4K |

## 📖 Usage

### 1. Clone Repository

```bash
git clone https://github.com/thanhan92-f1/server-scripts-cli
cd server-scripts-cli
```

### 2. Generate Manifest

```bash
./generate-manifest.sh
```

This creates `manifest.yaml` from YAML front-matter in `demo-scripts/`.

### 3. List Scripts

```bash
./ssc.sh list
```

Shows all demo scripts with metadata (type, status, category, timer).

### 4. Run Examples

```bash
# Run backup example (requires root)
./ssc.sh run backup-example

# Show monitoring script details
./ssc.sh info monitoring-example

# Execute health check
./ssc.sh run health-check
```

## 🔍 Script Details

### backup-example.sh

Demonstrates:
- `requires_root: true` - Sudo execution
- `type: admin` - Admin classification
- `deployment: systemd` - Timer-based scheduling
- Error handling and logging

### monitoring-example.sh

Demonstrates:
- `type: report` - Report generation
- `category: monitoring` - Categorization
- Metrics collection
- JSON output format

### health-check.sh

Demonstrates:
- `type: check` - Validation scripts
- `status: active` - Production status
- Service availability checks
- Exit codes (0=success, 1=failure)

### deploy-example.sh

Demonstrates:
- `type: admin` - Administrative tasks
- `category: deployment` - Deployment workflows
- Pre/post deployment hooks
- Rollback logic

## 📝 Example Manifest

See [manifest.example.yaml](manifest.example.yaml) for complete YAML structure:

```yaml
scripts:
  backup-example:
    path: examples/demo-scripts/backup-example.sh
    type: admin
    requires_root: true
    deployment: systemd
    service: backup-example.timer
    status: active
```

## 🎓 Learning Path

1. **Read Scripts**: Start with `monitoring-example.sh` (simplest)
2. **Understand YAML**: Check YAML front-matter in each script
3. **Generate Manifest**: Run `./generate-manifest.sh`
4. **Execute**: Try `./ssc.sh run monitoring-example`
5. **Customize**: Modify scripts for your use case

## 🔗 Additional Resources

- [MANIFEST_SCHEMA.md](../docs/MANIFEST_SCHEMA.md) - Complete YAML reference
- [SETUP.md](../docs/SETUP.md) - Installation guide
- [Main README](../README.md) - Project overview

## 💡 Contributing

Found a bug in examples? Want to add more demos? See [CONTRIBUTING.md](../CONTRIBUTING.md).

---

**Last Updated**: 2026-01-20
