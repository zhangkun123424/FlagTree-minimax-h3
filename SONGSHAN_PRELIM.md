# FlagTree HCU compiler overlay for MiniMax-H3

This branch carries the three compiler files from the gfx936 AOT build overlay. They target the installed FlagTree wheel `0.7.0+hcu3.6` for Python 3.10. That wheel's metadata names flagos-ai/FlagTree as its upstream. The wheel metadata does not record its Git commit.

In an isolated Python 3.10 AOT environment with the exact wheel and the platform's Hygon DTK, overlay the files on the installed `triton` package:

| File in this branch | Destination within site-packages |
| --- | --- |
| `compile.py` | `triton/tools/compile.py` |
| `cache.py` | `triton/runtime/cache.py` |
| `compiler_hcu.py` | `triton/backends/hcu/compiler_hcu.py` |

The NineToothed competition branch contains the TimestepEmbedding AOT entry point. This overlay was used to prepare AOT kernels. The final FL2VA run loaded the resulting AOT package.
