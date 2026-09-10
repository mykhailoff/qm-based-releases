# qm-based — releases

Windows builds of **qm-based**, a read-only accessibility tool for a qmBase
quality-management tenant. The source lives in a private repository; this one
holds nothing but release binaries.

It is public for one reason: an installed copy has to be able to fetch its own
updates without a credential, and a credential shipped inside a distributed
binary is a published credential.

## Downloads

Each release carries two Windows builds:

| File | Use |
| --- | --- |
| `qm-based-<version>-setup.exe` | Installer. Updates itself in the background and applies them when you close the app. |
| `qm-based-<version>-portable.exe` | Single file, no install, no admin. Cannot update itself — it tells you when a newer version exists. |

Prefer the installer unless you specifically need to run it without installing.

`latest.yml` and the `.blockmap` files are how the installer finds and downloads
updates. Ignore them; they are not for humans.

## Notes

- Builds are **not code-signed**, so Windows SmartScreen will warn on first run.
- The app does nothing without a login to its qmBase tenant.
- Releases tagged `-dev` are test builds and are marked as prereleases. The
  updater ignores them.
