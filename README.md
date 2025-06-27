# Rojo-Project-Boilerplate

A fully managed [Rojo](https://github.com/rojo-rbx/rojo) project boilerplate for Roblox development.

## Getting Started

This project uses Rojo’s fully managed workflow. All source files are organized in the `src/` directory and mapped to Roblox services using [`default.project.json`](default.project.json).

### Prerequisites

- [Roblox Studio](https://www.roblox.com/create)
- [Rojo](https://rojo.space/) (install via [GitHub Releases](https://github.com/rojo-rbx/rojo/releases) or with a package manager)
- (Optional) [Visual Studio Code](https://code.visualstudio.com/) for editing

### Project Structure

- `src/` — Source files organized by Roblox service (e.g., `Lighting`, `Workspace`, `ReplicatedStorage`, etc.)
- [`default.project.json`](default.project.json) — Rojo project configuration mapping `src/` to Roblox services
- [`sourcemap.json`](sourcemap.json) — (Generated) Source mapping for debugging
- `.gitignore` — Ignores build and lock files
- `Rojo-Project-Boilerplate.rbxlx` — The generated Roblox place file

### Workflow

#### 1. Build the Place File

Before running or serving the project, you must build the place file from source:

```sh
rojo build -o "Rojo-Project-Boilerplate.rbxlx"
```

This command compiles the contents of `src/` into a Roblox Studio place file.

#### 2. Open in Roblox Studio

- Open `Rojo-Project-Boilerplate.rbxlx` in Roblox Studio.

#### 3. Start Rojo Server

To enable live syncing between your code and Roblox Studio, run:

```sh
rojo serve
```

- This will watch your files and sync changes to the open place in Studio.
- Make sure the place open in Studio matches the one you built.
- Lastly, open the Rojo plugin on the studio and make sure the port number is similar to the one in `default.project.json` and hit connect.

#### 4. Edit and Sync

- Make changes to files in `src/`.
- Rojo will automatically sync changes to Studio while `rojo serve` is running.

#### 5. Exporting/Publishing

- When ready to publish or share, rebuild the place file with `rojo build` to ensure all changes are included.

### Additional Notes

- **Adding Scripts/Assets:** Place new scripts or assets in the appropriate `src/` subfolder. Update `default.project.json` if you add new services or folders.
- **Module Scripts:** Shared code should go in `src/ReplicatedStorage/Modules/`.
- **Server Scripts:** Place server-only scripts in `src/ServerScriptService/`.
- **Client Scripts:** Place client-only scripts in `src/StarterPlayerScripts/`.

### Troubleshooting

- If changes aren’t appearing in Studio, ensure you have run `rojo build` and are running `rojo serve`.
- Check that the place file open in Studio matches the output from `rojo build`.

### Resources

- [Rojo Documentation](https://rojo.space/docs)
- [Roblox Developer Hub](https://create.roblox.com/docs)

---

MIT License — see [`LICENSE`](LICENSE) for details.
