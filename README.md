# dex-robotics-skills

Codex skills for robotics diagnosis, inverse kinematics, motion retargeting, and control-response tuning across articulated models.

## Included skills

- `dex-robotics-engineering`: trace the failing layer across sensing, calibration, retargeting, IK, control, and execution
- `dex-retargeting-debug`: representation and frame contracts, morphology, calibration observability, task objectives, and contact intent
- `dex-ik-design-debug`: FK/Jacobians, constrained solving, reachability evidence, solution continuity, and virtual fixtures
- `impedance-gain-tuning`: PD/PID and impedance response with explicit loop, feedback, actuator, and load semantics

The existing invocation names remain stable. No particular device, vendor, landmark count, joint count, or coordinate convention is assumed.

## Workflow

Use the router when the failing layer is unclear; use a domain skill directly when it is known. Follow the actual source → estimate → task → proposal → command → feedback chain and validate the stage being changed. Runtime behavior, fault responses, clocks, and acceptance criteria come from the project's execution contract.

Shared references cover [execution contracts](dex-robotics-engineering/references/execution-contract.md), [replay validation](dex-robotics-engineering/references/replay-validation.md), and [calibration observability](dex-retargeting-debug/references/calibration-observability.md). Evidence claims stay within the scope established by source inspection, synthetic tests, replay, simulation, or physical measurements.

## Install

Install all four skills:

```bash
npx skills add C1TRuSovo831/dex-robotics-skills -g -y
```

Install the four skills together as sibling directories: domain skills link to shared references in `dex-robotics-engineering`.

If automatic discovery does not find all four directories, install them by
path with the Codex helper script:

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo C1TRuSovo831/dex-robotics-skills \
  --ref main \
  --path dex-retargeting-debug \
         dex-ik-design-debug \
         impedance-gain-tuning \
         dex-robotics-engineering
```

## Maintenance and validation

[Behavior cases and evaluation procedure](dex-robotics-engineering/tests/forward-evaluation.md) exercise routing and technical judgment without operating hardware. The [maintenance history](docs/approach-history.md) records the evaluated revision, actual responses, grading, and limitations. Frontmatter, UI metadata, file hashes, and relative links are checked separately; they do not constitute a behavioral evaluation or physical validation.

## License

MIT
