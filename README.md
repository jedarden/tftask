# tftask

> **Archived reference:** this repository is a one-off compatibility image for
> GalleyBytes Terraform Operator. It has no releases, supported registry image,
> or active deployment pipeline. Build it locally if you need to reproduce it.

`tftask` packages Terraform 1.9.8 with the task entrypoint expected by the
[GalleyBytes Terraform Operator](https://github.com/GalleyBytes/terraform-operator).
It was created after the upstream project stopped publishing task images for
newer Terraform versions.

## Build

```bash
docker build --build-arg TF_IMAGE=1.9.8 -t tftask:1.9.8 .
```

The image also includes the upstream task entrypoint, `kubectl`, and
`irsa-tokengen`. It is intended for an existing Terraform Operator deployment;
this repository does not include an operator installation or a standalone
command-line interface.

## Upstream attribution

`entrypoint/entrypoint.cpp` and `usersetup` are byte-identical copies from
[`GalleyBytes/terraform-operator-tasks`](https://github.com/GalleyBytes/terraform-operator-tasks/tree/master/images).
The upstream project and this derivative are licensed under Apache-2.0. See
[LICENSE](LICENSE).

---

*This GitHub repo is a read-only mirror of git.ardenone.com/jedarden/tftask — issues and PRs are welcome here either way.*

