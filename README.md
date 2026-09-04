# dex-robotics-skills

Codex skills for dexterous-hand retargeting, constrained teleoperation IK, impedance kp/kd tuning, and HIL evidence review.

## Included skills

- `dex-robotics-engineering`: natural-language router with four routes
- `dex-retargeting-debug`: MANUS/Wuji/Sharpa hand retargeting
- `dex-ik-design-debug`: FK, Jacobian, DLS, QP/CBF and virtual-wall IK
- `impedance-gain-tuning`: robot hand and arm kp/kd, PD/PID and impedance tuning

## Route priority

1. Evidence: HIL, real robot, physical safety, readiness
2. Retargeting: MANUS, Wuji, 21x3, 20 DOF, pinch, aperture, coordinates
3. IK: FK, Jacobian, DLS, QP, CBF, singularities, virtual walls
4. Gain: kp, kd, PD/PID, impedance, overshoot, settling and oscillation

Generic debugging uses the `diagnosing-bugs` workflow. New interfaces use `codebase-design` first. Regression tests use `tdd` after the public seam is confirmed.

## Install

Install all four skills:

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo C1TRuSovo831/dex-robotics-skills \
  --ref main \
  --path dex-retargeting-debug \
         dex-ik-design-debug \
         impedance-gain-tuning \
         dex-robotics-engineering
```

Install only the router:

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo C1TRuSovo831/dex-robotics-skills \
  --ref main \
  --path dex-robotics-engineering
```

## License

MIT
