# Deadcheat

A small browser userscript experiment for learning about browser scripting, WebGL hooks, and debugging in a VM.

> This project is meant as a learning tool and experimentation sandbox. It is not intended to be a functional cheat for any live game or to bypass anti-cheat systems.

## Overview

This repo started as a curiosity project to understand how browser-based graphics APIs and injected scripts behave in practice. The goal was to explore:

- how userscripts interact with the page
- how WebGL contexts are created and used
- how shader and program metadata can be inspected
- how browser behavior changes under VM-based or software-rendered environments

## Status

The project is currently a personal experiment rather than a polished tool or end-user product.

- It was tested in a Linux VM
- It was not built for production use
- It does not target a specific game or live service
- It is not guaranteed to work in all browsers or environments

## Running it

Use a browser that supports userscript managers such as Tampermonkey or Violentmonkey.

1. Open the script file in the repo.
2. Install it as a userscript.
3. Load a page matching the script's URL rules.
4. Watch the console and browser behavior for debugging output.

## Issue encountered in the VM

While testing in a Linux VM, I ran into a rendering issue related to browser GPU acceleration. The browser was failing in a way that suggested the visual pipeline was not behaving correctly in the VM environment.

After trying a few fixes, the workaround that worked was:

```bash
brave-browser --enable-unsafe-swiftshader
```

This forces Brave to fall back to software rendering via SwiftShader instead of using hardware acceleration. It is useful for debugging in constrained environments like virtual machines.

## Notes

- This is not a serious or production-grade project.
- It was created as a learning exercise and debugging experiment.
- It should be treated as a sandbox, not as a real gameplay tool.

## License

This project is currently marked under the `lotus` license tag in the userscript metadata.

## Final note

This repository exists mainly as an experiment in browser behavior and debugging, not as a reliable or supported utility. If you want to continue building on it, the best next step is to treat it as a research project and keep the scope focused on learning and debugging rather than production usage.
