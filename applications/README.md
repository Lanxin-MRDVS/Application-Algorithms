# Applications

[Documentation Home](../README.md) / Applications

Each application uses a stable, lowercase folder name and the same internal structure. Developers can enter any folder and immediately locate the overview, technical documentation, and version history.

| Folder | Public name | Runtime | Documentation | Releases |
| --- | --- | --- | --- | --- |
| [`depalletizing/`](depalletizing/) | Depalletizing | AW3 | [Deployment guide](depalletizing/docs/deployment-guide.md) | [History](depalletizing/releases/README.md) |
| [`pallet-docking/`](pallet-docking/) | Pallet Docking | PalletPro today; AW3 target | [User guide](pallet-docking/docs/user-guide.md) | [History](pallet-docking/releases/README.md) |
| [`volume-measurement/`](volume-measurement/) | Volume Measurement | AW3 target | [Overview](volume-measurement/README.md) | [History](volume-measurement/releases/README.md) |
| [`slot-monitoring/`](slot-monitoring/) | Slot Monitoring | AW3 target | [User guide](slot-monitoring/docs/user-guide.md) | [History](slot-monitoring/releases/README.md) |
| [`obstacle-avoidance/`](obstacle-avoidance/) | Obstacle Avoidance | Camera application | [Deployment guide](obstacle-avoidance/docs/deployment-guide.md) | [History](obstacle-avoidance/releases/README.md) |

## Required structure

```text
<application>/
├── README.md       # User and developer entry page
├── docs/
│   ├── README.md   # Documentation index
│   └── ...         # Deployment, API, protocol, and user guides
└── releases/       # Release index plus one note per published version
```

Application-specific screenshots belong under that application's `docs/images/` directory. Shared brand graphics belong in the repository-level `assets/` directory. Installers and upgrade packages belong in GitHub Releases and are linked from the release index; they are never committed to the Git tree.
