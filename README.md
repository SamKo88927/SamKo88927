# Sam Ko

Senior Software Engineer in Taipei. I build production AI infrastructure: enterprise AI agent platforms, speech and
meeting-intelligence pipelines, and the multi-tenant APIs and billing behind them.

**Now** · Senior engineer on GNTC, Dcard's enterprise AI product line. I own the meeting transcription stack end to
end, lead projects from design doc to rollout, and stay first-line on-call for what I ship.

**What I work on**
- **AI agent platforms**: agent runtime, tool calling, MCP connectors, streaming, time-to-first-token tuning.
- **Speech pipelines**: live and final transcription, speech detection with ONNX models on Kubernetes, resumable
  recording uploads.
- **Platform and billing**: multi-tenant APIs with OAuth, usage metering, Stripe billing and credit ledgers.
- **Reliability**: Postgres query planning, queues (BullMQ, Pub/Sub, SQS), Terraform, on-call and root-cause fixes.

**On the side** · Embodied AI on real hardware: modified RoArm-M3 robot arms, camera-based vision, MuJoCo
simulation and agent-native control.

## Featured

### [roarm-mcp](https://github.com/SamKo88927/roarm-mcp)

[![PyPI](https://img.shields.io/pypi/v/roarm-mcp)](https://pypi.org/project/roarm-mcp/)
[![CI](https://github.com/SamKo88927/roarm-mcp/actions/workflows/ci.yml/badge.svg)](https://github.com/SamKo88927/roarm-mcp/actions/workflows/ci.yml)

An MCP server that lets LLM agents drive a Waveshare RoArm-M3 robot arm. Every motion is planned and checked in
MuJoCo by a safety layer the agent cannot bypass; a refused command returns a reason code and the nearest safe pose,
so the model can correct itself. On PyPI (`uvx roarm-mcp`) and in the official MCP Registry.

<a href="https://github.com/SamKo88927/roarm-mcp"><img src="https://raw.githubusercontent.com/SamKo88927/roarm-mcp/main/docs/media/demo.gif" alt="roarm-mcp demo: a simulated RoArm-M3 moves to checked targets and refuses unsafe ones" width="560"></a>

### [mjguard](https://github.com/SamKo88927/mjguard)

[![PyPI](https://img.shields.io/pypi/v/mjguard)](https://pypi.org/project/mjguard/)
[![CI](https://github.com/SamKo88927/mjguard/actions/workflows/ci.yml/badge.svg)](https://github.com/SamKo88927/mjguard/actions/workflows/ci.yml)

The safety layer from roarm-mcp, generalised to **any MuJoCo-modelled arm**. Language models refuse unsafe requests
in chat but comply once they hold a robot's tools; mjguard puts the check below the model. A small TOML config names
the MJCF, joints and tool frame; every motion is planned and every waypoint checked against the robot's own model.
Ships 13 tested presets, from the LeRobot SO-ARM100 to the UR10e and Franka Panda (`uvx mjguard serve so_arm100`).

<a href="https://github.com/SamKo88927/mjguard"><img src="https://raw.githubusercontent.com/SamKo88927/mjguard/main/docs/media/demo.gif" alt="mjguard demo: a simulated Franka Panda refuses a move into the table and an out-of-reach move, then follows the suggested safe point" width="480"></a>

## Stack

TypeScript · Python · Node.js · Postgres · Redis · GCP · AWS · Kubernetes · Terraform · ONNX · MuJoCo

[LinkedIn](https://www.linkedin.com/in/samko-pfm/)
