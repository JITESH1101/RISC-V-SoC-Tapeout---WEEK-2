# VSDBabySoC Simulation & Synthesis Flow

# Project Structure

Here is my project Structure of the directory where i used all the simulations and synthesis


  - ``src/include/ ``- Contains header files (*.vh) with necessary macros or parameter definitions.
  - ``src/module/ ``- Contains Verilog files for each module in the SoC design.
  - ``output/ ``- Directory where compiled outputs and simulation files will be generated.


```
.
├── images
│   ├── centralized_avsddac.png
│   ├── inside_dac.png
│   ├── inside_pll.png
│   ├── openlane_flow.png
│   ├── physical_design.png
│   ├── post_routing_sim.png
│   ├── post_synth_sim.png
│   ├── pre_synth_sim.png
│   ├── rvmyth_layout.png
│   ├── selected_dac.png
│   ├── selected_pll.png
│   ├── vsdbabysoc_block_diagram.png
│   └── vsdbabysoc_layout.png
├── LICENSE
├── Makefile
├── output
│   ├── post_synth_sim
│   │   ├── post_synth_sim.out
│   │   └── post_synth_sim.vcd
│   └── pre_synth_sim
│       ├── pre_synth_sim.out
│       └── pre_synth_sim.vcd
├── README.md
├── sp_env
│   ├── bin
│   │   ├── activate
│   │   ├── activate.csh
│   │   ├── activate.fish
│   │   ├── Activate.ps1
│   │   ├── normalizer
│   │   ├── pip
│   │   ├── pip3
│   │   ├── pip3.12
│   │   ├── python -> python3
│   │   ├── python3 -> /usr/bin/python3
│   │   ├── python3.12 -> python3
│   │   └── sandpiper-saas
│   ├── include
│   │   └── python3.12
│   ├── lib
│   │   └── python3.12
│   │       └── site-packages
│   │           ├── argparse-1.4.0.dist-info
│   │           │   ├── DESCRIPTION.rst
│   │           │   ├── INSTALLER
│   │           │   ├── METADATA
│   │           │   ├── metadata.json
│   │           │   ├── RECORD
│   │           │   ├── top_level.txt
│   │           │   └── WHEEL
│   │           ├── argparse.py
│   │           ├── certifi
│   │           │   ├── cacert.pem
│   │           │   ├── core.py
│   │           │   ├── __init__.py
│   │           │   ├── __main__.py
│   │           │   ├── __pycache__
│   │           │   │   ├── core.cpython-312.pyc
│   │           │   │   ├── __init__.cpython-312.pyc
│   │           │   │   └── __main__.cpython-312.pyc
│   │           │   └── py.typed
│   │           ├── certifi-2025.8.3.dist-info
│   │           │   ├── INSTALLER
│   │           │   ├── licenses
│   │           │   │   └── LICENSE
│   │           │   ├── METADATA
│   │           │   ├── RECORD
│   │           │   ├── top_level.txt
│   │           │   └── WHEEL
│   │           ├── charset_normalizer
│   │           │   ├── api.py
│   │           │   ├── cd.py
│   │           │   ├── cli
│   │           │   │   ├── __init__.py
│   │           │   │   ├── __main__.py
│   │           │   │   └── __pycache__
│   │           │   │       ├── __init__.cpython-312.pyc
│   │           │   │       └── __main__.cpython-312.pyc
│   │           │   ├── constant.py
│   │           │   ├── __init__.py
│   │           │   ├── legacy.py
│   │           │   ├── __main__.py
│   │           │   ├── md.cpython-312-x86_64-linux-gnu.so
│   │           │   ├── md__mypyc.cpython-312-x86_64-linux-gnu.so
│   │           │   ├── md.py
│   │           │   ├── models.py
│   │           │   ├── __pycache__
│   │           │   │   ├── api.cpython-312.pyc
│   │           │   │   ├── cd.cpython-312.pyc
│   │           │   │   ├── constant.cpython-312.pyc
│   │           │   │   ├── __init__.cpython-312.pyc
│   │           │   │   ├── legacy.cpython-312.pyc
│   │           │   │   ├── __main__.cpython-312.pyc
│   │           │   │   ├── md.cpython-312.pyc
│   │           │   │   ├── models.cpython-312.pyc
│   │           │   │   ├── utils.cpython-312.pyc
│   │           │   │   └── version.cpython-312.pyc
│   │           │   ├── py.typed
│   │           │   ├── utils.py
│   │           │   └── version.py
│   │           ├── charset_normalizer-3.4.3.dist-info
│   │           │   ├── entry_points.txt
│   │           │   ├── INSTALLER
│   │           │   ├── licenses
│   │           │   │   └── LICENSE
│   │           │   ├── METADATA
│   │           │   ├── RECORD
│   │           │   ├── top_level.txt
│   │           │   └── WHEEL
│   │           ├── click
│   │           │   ├── _compat.py
│   │           │   ├── core.py
│   │           │   ├── decorators.py
│   │           │   ├── exceptions.py
│   │           │   ├── formatting.py
│   │           │   ├── globals.py
│   │           │   ├── __init__.py
│   │           │   ├── parser.py
│   │           │   ├── __pycache__
│   │           │   │   ├── _compat.cpython-312.pyc
│   │           │   │   ├── core.cpython-312.pyc
│   │           │   │   ├── decorators.cpython-312.pyc
│   │           │   │   ├── exceptions.cpython-312.pyc
│   │           │   │   ├── formatting.cpython-312.pyc
│   │           │   │   ├── globals.cpython-312.pyc
│   │           │   │   ├── __init__.cpython-312.pyc
│   │           │   │   ├── parser.cpython-312.pyc
│   │           │   │   ├── shell_completion.cpython-312.pyc
│   │           │   │   ├── termui.cpython-312.pyc
│   │           │   │   ├── _termui_impl.cpython-312.pyc
│   │           │   │   ├── testing.cpython-312.pyc
│   │           │   │   ├── _textwrap.cpython-312.pyc
│   │           │   │   ├── types.cpython-312.pyc
│   │           │   │   ├── _utils.cpython-312.pyc
│   │           │   │   ├── utils.cpython-312.pyc
│   │           │   │   └── _winconsole.cpython-312.pyc
│   │           │   ├── py.typed
│   │           │   ├── shell_completion.py
│   │           │   ├── _termui_impl.py
│   │           │   ├── termui.py
│   │           │   ├── testing.py
│   │           │   ├── _textwrap.py
│   │           │   ├── types.py
│   │           │   ├── _utils.py
│   │           │   ├── utils.py
│   │           │   └── _winconsole.py
│   │           ├── click-8.3.0.dist-info
│   │           │   ├── INSTALLER
│   │           │   ├── licenses
│   │           │   │   └── LICENSE.txt
│   │           │   ├── METADATA
│   │           │   ├── RECORD
│   │           │   ├── REQUESTED
│   │           │   └── WHEEL
│   │           ├── idna
│   │           │   ├── codec.py
│   │           │   ├── compat.py
│   │           │   ├── core.py
│   │           │   ├── idnadata.py
│   │           │   ├── __init__.py
│   │           │   ├── intranges.py
│   │           │   ├── package_data.py
│   │           │   ├── __pycache__
│   │           │   │   ├── codec.cpython-312.pyc
│   │           │   │   ├── compat.cpython-312.pyc
│   │           │   │   ├── core.cpython-312.pyc
│   │           │   │   ├── idnadata.cpython-312.pyc
│   │           │   │   ├── __init__.cpython-312.pyc
│   │           │   │   ├── intranges.cpython-312.pyc
│   │           │   │   ├── package_data.cpython-312.pyc
│   │           │   │   └── uts46data.cpython-312.pyc
│   │           │   ├── py.typed
│   │           │   └── uts46data.py
│   │           ├── idna-3.10.dist-info
│   │           │   ├── INSTALLER
│   │           │   ├── LICENSE.md
│   │           │   ├── METADATA
│   │           │   ├── RECORD
│   │           │   └── WHEEL
│   │           ├── path
│   │           │   ├── classes.py
│   │           │   ├── compat
│   │           │   │   ├── py38.py
│   │           │   │   └── __pycache__
│   │           │   │       └── py38.cpython-312.pyc
│   │           │   ├── __init__.py
│   │           │   ├── masks.py
│   │           │   ├── matchers.py
│   │           │   ├── __pycache__
│   │           │   │   ├── classes.cpython-312.pyc
│   │           │   │   ├── __init__.cpython-312.pyc
│   │           │   │   ├── masks.cpython-312.pyc
│   │           │   │   └── matchers.cpython-312.pyc
│   │           │   └── py.typed
│   │           ├── path-17.1.1.dist-info
│   │           │   ├── INSTALLER
│   │           │   ├── licenses
│   │           │   │   └── LICENSE
│   │           │   ├── METADATA
│   │           │   ├── RECORD
│   │           │   ├── top_level.txt
│   │           │   └── WHEEL
│   │           ├── pip
│   │           │   ├── __init__.py
│   │           │   ├── _internal
│   │           │   │   ├── build_env.py
│   │           │   │   ├── cache.py
│   │           │   │   ├── cli
│   │           │   │   │   ├── autocompletion.py
│   │           │   │   │   ├── base_command.py
│   │           │   │   │   ├── cmdoptions.py
│   │           │   │   │   ├── command_context.py
│   │           │   │   │   ├── __init__.py
│   │           │   │   │   ├── main_parser.py
│   │           │   │   │   ├── main.py
│   │           │   │   │   ├── parser.py
│   │           │   │   │   ├── progress_bars.py
│   │           │   │   │   ├── __pycache__
│   │           │   │   │   │   ├── autocompletion.cpython-312.pyc
│   │           │   │   │   │   ├── base_command.cpython-312.pyc
│   │           │   │   │   │   ├── cmdoptions.cpython-312.pyc
│   │           │   │   │   │   ├── command_context.cpython-312.pyc
│   │           │   │   │   │   ├── __init__.cpython-312.pyc
│   │           │   │   │   │   ├── main.cpython-312.pyc
│   │           │   │   │   │   ├── main_parser.cpython-312.pyc
│   │           │   │   │   │   ├── parser.cpython-312.pyc
│   │           │   │   │   │   ├── progress_bars.cpython-312.pyc
│   │           │   │   │   │   ├── req_command.cpython-312.pyc
│   │           │   │   │   │   ├── spinners.cpython-312.pyc
│   │           │   │   │   │   └── status_codes.cpython-312.pyc
│   │           │   │   │   ├── req_command.py
│   │           │   │   │   ├── spinners.py
│   │           │   │   │   └── status_codes.py
│   │           │   │   ├── commands
│   │           │   │   │   ├── cache.py
│   │           │   │   │   ├── check.py
│   │           │   │   │   ├── completion.py
│   │           │   │   │   ├── configuration.py
│   │           │   │   │   ├── debug.py
│   │           │   │   │   ├── download.py
│   │           │   │   │   ├── freeze.py
│   │           │   │   │   ├── hash.py
│   │           │   │   │   ├── help.py
│   │           │   │   │   ├── index.py
│   │           │   │   │   ├── __init__.py
│   │           │   │   │   ├── inspect.py
│   │           │   │   │   ├── install.py
│   │           │   │   │   ├── list.py
│   │           │   │   │   ├── __pycache__
│   │           │   │   │   │   ├── cache.cpython-312.pyc
│   │           │   │   │   │   ├── check.cpython-312.pyc
│   │           │   │   │   │   ├── completion.cpython-312.pyc
│   │           │   │   │   │   ├── configuration.cpython-312.pyc
│   │           │   │   │   │   ├── debug.cpython-312.pyc
│   │           │   │   │   │   ├── download.cpython-312.pyc
│   │           │   │   │   │   ├── freeze.cpython-312.pyc
│   │           │   │   │   │   ├── hash.cpython-312.pyc
│   │           │   │   │   │   ├── help.cpython-312.pyc
│   │           │   │   │   │   ├── index.cpython-312.pyc
│   │           │   │   │   │   ├── __init__.cpython-312.pyc
│   │           │   │   │   │   ├── inspect.cpython-312.pyc
│   │           │   │   │   │   ├── install.cpython-312.pyc
│   │           │   │   │   │   ├── list.cpython-312.pyc
│   │           │   │   │   │   ├── search.cpython-312.pyc
│   │           │   │   │   │   ├── show.cpython-312.pyc
│   │           │   │   │   │   ├── uninstall.cpython-312.pyc
│   │           │   │   │   │   └── wheel.cpython-312.pyc
│   │           │   │   │   ├── search.py
│   │           │   │   │   ├── show.py
│   │           │   │   │   ├── uninstall.py
│   │           │   │   │   └── wheel.py
│   │           │   │   ├── configuration.py
│   │           │   │   ├── distributions
│   │           │   │   │   ├── base.py
│   │           │   │   │   ├── __init__.py
│   │           │   │   │   ├── installed.py
│   │           │   │   │   ├── __pycache__
│   │           │   │   │   │   ├── base.cpython-312.pyc
│   │           │   │   │   │   ├── __init__.cpython-312.pyc
│   │           │   │   │   │   ├── installed.cpython-312.pyc
│   │           │   │   │   │   ├── sdist.cpython-312.pyc
│   │           │   │   │   │   └── wheel.cpython-312.pyc
│   │           │   │   │   ├── sdist.py
│   │           │   │   │   └── wheel.py
│   │           │   │   ├── exceptions.py
│   │           │   │   ├── index
│   │           │   │   │   ├── collector.py
│   │           │   │   │   ├── __init__.py
│   │           │   │   │   ├── package_finder.py
│   │           │   │   │   ├── __pycache__
│   │           │   │   │   │   ├── collector.cpython-312.pyc
│   │           │   │   │   │   ├── __init__.cpython-312.pyc
│   │           │   │   │   │   ├── package_finder.cpython-312.pyc
│   │           │   │   │   │   └── sources.cpython-312.pyc
│   │           │   │   │   └── sources.py
│   │           │   │   ├── __init__.py
│   │           │   │   ├── locations
│   │           │   │   │   ├── base.py
│   │           │   │   │   ├── _distutils.py
│   │           │   │   │   ├── __init__.py
│   │           │   │   │   ├── __pycache__
│   │           │   │   │   │   ├── base.cpython-312.pyc
│   │           │   │   │   │   ├── _distutils.cpython-312.pyc
│   │           │   │   │   │   ├── __init__.cpython-312.pyc
│   │           │   │   │   │   └── _sysconfig.cpython-312.pyc
│   │           │   │   │   └── _sysconfig.py
│   │           │   │   ├── main.py
│   │           │   │   ├── metadata
│   │           │   │   │   ├── base.py
│   │           │   │   │   ├── importlib
│   │           │   │   │   │   ├── _compat.py
│   │           │   │   │   │   ├── _dists.py
│   │           │   │   │   │   ├── _envs.py
│   │           │   │   │   │   ├── __init__.py
│   │           │   │   │   │   └── __pycache__
│   │           │   │   │   │       ├── _compat.cpython-312.pyc
│   │           │   │   │   │       ├── _dists.cpython-312.pyc
│   │           │   │   │   │       ├── _envs.cpython-312.pyc
│   │           │   │   │   │       └── __init__.cpython-312.pyc
│   │           │   │   │   ├── __init__.py
│   │           │   │   │   ├── _json.py
│   │           │   │   │   ├── pkg_resources.py
│   │           │   │   │   └── __pycache__
│   │           │   │   │       ├── base.cpython-312.pyc
│   │           │   │   │       ├── __init__.cpython-312.pyc
│   │           │   │   │       ├── _json.cpython-312.pyc
│   │           │   │   │       └── pkg_resources.cpython-312.pyc
│   │           │   │   ├── models
│   │           │   │   │   ├── candidate.py
│   │           │   │   │   ├── direct_url.py
│   │           │   │   │   ├── format_control.py
│   │           │   │   │   ├── index.py
│   │           │   │   │   ├── __init__.py
│   │           │   │   │   ├── installation_report.py
│   │           │   │   │   ├── link.py
│   │           │   │   │   ├── __pycache__
│   │           │   │   │   │   ├── candidate.cpython-312.pyc
│   │           │   │   │   │   ├── direct_url.cpython-312.pyc
│   │           │   │   │   │   ├── format_control.cpython-312.pyc
│   │           │   │   │   │   ├── index.cpython-312.pyc
│   │           │   │   │   │   ├── __init__.cpython-312.pyc
│   │           │   │   │   │   ├── installation_report.cpython-312.pyc
│   │           │   │   │   │   ├── link.cpython-312.pyc
│   │           │   │   │   │   ├── scheme.cpython-312.pyc
│   │           │   │   │   │   ├── search_scope.cpython-312.pyc
│   │           │   │   │   │   ├── selection_prefs.cpython-312.pyc
│   │           │   │   │   │   ├── target_python.cpython-312.pyc
│   │           │   │   │   │   └── wheel.cpython-312.pyc
│   │           │   │   │   ├── scheme.py
│   │           │   │   │   ├── search_scope.py
│   │           │   │   │   ├── selection_prefs.py
│   │           │   │   │   ├── target_python.py
│   │           │   │   │   └── wheel.py
│   │           │   │   ├── network
│   │           │   │   │   ├── auth.py
│   │           │   │   │   ├── cache.py
│   │           │   │   │   ├── download.py
│   │           │   │   │   ├── __init__.py
│   │           │   │   │   ├── lazy_wheel.py
│   │           │   │   │   ├── __pycache__
│   │           │   │   │   │   ├── auth.cpython-312.pyc
│   │           │   │   │   │   ├── cache.cpython-312.pyc
│   │           │   │   │   │   ├── download.cpython-312.pyc
│   │           │   │   │   │   ├── __init__.cpython-312.pyc
│   │           │   │   │   │   ├── lazy_wheel.cpython-312.pyc
│   │           │   │   │   │   ├── session.cpython-312.pyc
│   │           │   │   │   │   ├── utils.cpython-312.pyc
│   │           │   │   │   │   └── xmlrpc.cpython-312.pyc
│   │           │   │   │   ├── session.py
│   │           │   │   │   ├── utils.py
│   │           │   │   │   └── xmlrpc.py
│   │           │   │   ├── operations
│   │           │   │   │   ├── build
│   │           │   │   │   │   ├── build_tracker.py
│   │           │   │   │   │   ├── __init__.py
│   │           │   │   │   │   ├── metadata_editable.py
│   │           │   │   │   │   ├── metadata_legacy.py
│   │           │   │   │   │   ├── metadata.py
│   │           │   │   │   │   ├── __pycache__
│   │           │   │   │   │   │   ├── build_tracker.cpython-312.pyc
│   │           │   │   │   │   │   ├── __init__.cpython-312.pyc
│   │           │   │   │   │   │   ├── metadata.cpython-312.pyc
│   │           │   │   │   │   │   ├── metadata_editable.cpython-312.pyc
│   │           │   │   │   │   │   ├── metadata_legacy.cpython-312.pyc
│   │           │   │   │   │   │   ├── wheel.cpython-312.pyc
│   │           │   │   │   │   │   ├── wheel_editable.cpython-312.pyc
│   │           │   │   │   │   │   └── wheel_legacy.cpython-312.pyc
│   │           │   │   │   │   ├── wheel_editable.py
│   │           │   │   │   │   ├── wheel_legacy.py
│   │           │   │   │   │   └── wheel.py
│   │           │   │   │   ├── check.py
│   │           │   │   │   ├── freeze.py
│   │           │   │   │   ├── __init__.py
│   │           │   │   │   ├── install
│   │           │   │   │   │   ├── editable_legacy.py
│   │           │   │   │   │   ├── __init__.py
│   │           │   │   │   │   ├── __pycache__
│   │           │   │   │   │   │   ├── editable_legacy.cpython-312.pyc
│   │           │   │   │   │   │   ├── __init__.cpython-312.pyc
│   │           │   │   │   │   │   └── wheel.cpython-312.pyc
│   │           │   │   │   │   └── wheel.py
│   │           │   │   │   ├── prepare.py
│   │           │   │   │   └── __pycache__
│   │           │   │   │       ├── check.cpython-312.pyc
│   │           │   │   │       ├── freeze.cpython-312.pyc
│   │           │   │   │       ├── __init__.cpython-312.pyc
│   │           │   │   │       └── prepare.cpython-312.pyc
│   │           │   │   ├── __pycache__
│   │           │   │   │   ├── build_env.cpython-312.pyc
│   │           │   │   │   ├── cache.cpython-312.pyc
│   │           │   │   │   ├── configuration.cpython-312.pyc
│   │           │   │   │   ├── exceptions.cpython-312.pyc
│   │           │   │   │   ├── __init__.cpython-312.pyc
│   │           │   │   │   ├── main.cpython-312.pyc
│   │           │   │   │   ├── pyproject.cpython-312.pyc
│   │           │   │   │   ├── self_outdated_check.cpython-312.pyc
│   │           │   │   │   └── wheel_builder.cpython-312.pyc
│   │           │   │   ├── pyproject.py
│   │           │   │   ├── req
│   │           │   │   │   ├── constructors.py
│   │           │   │   │   ├── __init__.py
│   │           │   │   │   ├── __pycache__
│   │           │   │   │   │   ├── constructors.cpython-312.pyc
│   │           │   │   │   │   ├── __init__.cpython-312.pyc
│   │           │   │   │   │   ├── req_file.cpython-312.pyc
│   │           │   │   │   │   ├── req_install.cpython-312.pyc
│   │           │   │   │   │   ├── req_set.cpython-312.pyc
│   │           │   │   │   │   └── req_uninstall.cpython-312.pyc
│   │           │   │   │   ├── req_file.py
│   │           │   │   │   ├── req_install.py
│   │           │   │   │   ├── req_set.py
│   │           │   │   │   └── req_uninstall.py
│   │           │   │   ├── resolution
│   │           │   │   │   ├── base.py
│   │           │   │   │   ├── __init__.py
│   │           │   │   │   ├── legacy
│   │           │   │   │   │   ├── __init__.py
│   │           │   │   │   │   ├── __pycache__
│   │           │   │   │   │   │   ├── __init__.cpython-312.pyc
│   │           │   │   │   │   │   └── resolver.cpython-312.pyc
│   │           │   │   │   │   └── resolver.py
│   │           │   │   │   ├── __pycache__
│   │           │   │   │   │   ├── base.cpython-312.pyc
│   │           │   │   │   │   └── __init__.cpython-312.pyc
│   │           │   │   │   └── resolvelib
│   │           │   │   │       ├── base.py
│   │           │   │   │       ├── candidates.py
│   │           │   │   │       ├── factory.py
│   │           │   │   │       ├── found_candidates.py
│   │           │   │   │       ├── __init__.py
│   │           │   │   │       ├── provider.py
│   │           │   │   │       ├── __pycache__
│   │           │   │   │       │   ├── base.cpython-312.pyc
│   │           │   │   │       │   ├── candidates.cpython-312.pyc
│   │           │   │   │       │   ├── factory.cpython-312.pyc
│   │           │   │   │       │   ├── found_candidates.cpython-312.pyc
│   │           │   │   │       │   ├── __init__.cpython-312.pyc
│   │           │   │   │       │   ├── provider.cpython-312.pyc
│   │           │   │   │       │   ├── reporter.cpython-312.pyc
│   │           │   │   │       │   ├── requirements.cpython-312.pyc
│   │           │   │   │       │   └── resolver.cpython-312.pyc
│   │           │   │   │       ├── reporter.py
│   │           │   │   │       ├── requirements.py
│   │           │   │   │       └── resolver.py
│   │           │   │   ├── self_outdated_check.py
│   │           │   │   ├── utils
│   │           │   │   │   ├── appdirs.py
│   │           │   │   │   ├── compatibility_tags.py
│   │           │   │   │   ├── compat.py
│   │           │   │   │   ├── datetime.py
│   │           │   │   │   ├── deprecation.py
│   │           │   │   │   ├── direct_url_helpers.py
│   │           │   │   │   ├── egg_link.py
│   │           │   │   │   ├── encoding.py
│   │           │   │   │   ├── entrypoints.py
│   │           │   │   │   ├── filesystem.py
│   │           │   │   │   ├── filetypes.py
│   │           │   │   │   ├── glibc.py
│   │           │   │   │   ├── hashes.py
│   │           │   │   │   ├── __init__.py
│   │           │   │   │   ├── _jaraco_text.py
│   │           │   │   │   ├── logging.py
│   │           │   │   │   ├── _log.py
│   │           │   │   │   ├── misc.py
│   │           │   │   │   ├── models.py
│   │           │   │   │   ├── packaging.py
│   │           │   │   │   ├── __pycache__
│   │           │   │   │   │   ├── appdirs.cpython-312.pyc
│   │           │   │   │   │   ├── compat.cpython-312.pyc
│   │           │   │   │   │   ├── compatibility_tags.cpython-312.pyc
│   │           │   │   │   │   ├── datetime.cpython-312.pyc
│   │           │   │   │   │   ├── deprecation.cpython-312.pyc
│   │           │   │   │   │   ├── direct_url_helpers.cpython-312.pyc
│   │           │   │   │   │   ├── egg_link.cpython-312.pyc
│   │           │   │   │   │   ├── encoding.cpython-312.pyc
│   │           │   │   │   │   ├── entrypoints.cpython-312.pyc
│   │           │   │   │   │   ├── filesystem.cpython-312.pyc
│   │           │   │   │   │   ├── filetypes.cpython-312.pyc
│   │           │   │   │   │   ├── glibc.cpython-312.pyc
│   │           │   │   │   │   ├── hashes.cpython-312.pyc
│   │           │   │   │   │   ├── __init__.cpython-312.pyc
│   │           │   │   │   │   ├── _jaraco_text.cpython-312.pyc
│   │           │   │   │   │   ├── _log.cpython-312.pyc
│   │           │   │   │   │   ├── logging.cpython-312.pyc
│   │           │   │   │   │   ├── misc.cpython-312.pyc
│   │           │   │   │   │   ├── models.cpython-312.pyc
│   │           │   │   │   │   ├── packaging.cpython-312.pyc
│   │           │   │   │   │   ├── setuptools_build.cpython-312.pyc
│   │           │   │   │   │   ├── subprocess.cpython-312.pyc
│   │           │   │   │   │   ├── temp_dir.cpython-312.pyc
│   │           │   │   │   │   ├── unpacking.cpython-312.pyc
│   │           │   │   │   │   ├── urls.cpython-312.pyc
│   │           │   │   │   │   ├── virtualenv.cpython-312.pyc
│   │           │   │   │   │   └── wheel.cpython-312.pyc
│   │           │   │   │   ├── setuptools_build.py
│   │           │   │   │   ├── subprocess.py
│   │           │   │   │   ├── temp_dir.py
│   │           │   │   │   ├── unpacking.py
│   │           │   │   │   ├── urls.py
│   │           │   │   │   ├── virtualenv.py
│   │           │   │   │   └── wheel.py
│   │           │   │   ├── vcs
│   │           │   │   │   ├── bazaar.py
│   │           │   │   │   ├── git.py
│   │           │   │   │   ├── __init__.py
│   │           │   │   │   ├── mercurial.py
│   │           │   │   │   ├── __pycache__
│   │           │   │   │   │   ├── bazaar.cpython-312.pyc
│   │           │   │   │   │   ├── git.cpython-312.pyc
│   │           │   │   │   │   ├── __init__.cpython-312.pyc
│   │           │   │   │   │   ├── mercurial.cpython-312.pyc
│   │           │   │   │   │   ├── subversion.cpython-312.pyc
│   │           │   │   │   │   └── versioncontrol.cpython-312.pyc
│   │           │   │   │   ├── subversion.py
│   │           │   │   │   └── versioncontrol.py
│   │           │   │   └── wheel_builder.py
│   │           │   ├── __main__.py
│   │           │   ├── __pip-runner__.py
│   │           │   ├── __pycache__
│   │           │   │   ├── __init__.cpython-312.pyc
│   │           │   │   ├── __main__.cpython-312.pyc
│   │           │   │   └── __pip-runner__.cpython-312.pyc
│   │           │   ├── py.typed
│   │           │   └── _vendor
│   │           │       ├── cachecontrol
│   │           │       │   ├── adapter.py
│   │           │       │   ├── cache.py
│   │           │       │   ├── caches
│   │           │       │   │   ├── file_cache.py
│   │           │       │   │   ├── __init__.py
│   │           │       │   │   ├── __pycache__
│   │           │       │   │   │   ├── file_cache.cpython-312.pyc
│   │           │       │   │   │   ├── __init__.cpython-312.pyc
│   │           │       │   │   │   └── redis_cache.cpython-312.pyc
│   │           │       │   │   └── redis_cache.py
│   │           │       │   ├── _cmd.py
│   │           │       │   ├── controller.py
│   │           │       │   ├── filewrapper.py
│   │           │       │   ├── heuristics.py
│   │           │       │   ├── __init__.py
│   │           │       │   ├── __pycache__
│   │           │       │   │   ├── adapter.cpython-312.pyc
│   │           │       │   │   ├── cache.cpython-312.pyc
│   │           │       │   │   ├── _cmd.cpython-312.pyc
│   │           │       │   │   ├── controller.cpython-312.pyc
│   │           │       │   │   ├── filewrapper.cpython-312.pyc
│   │           │       │   │   ├── heuristics.cpython-312.pyc
│   │           │       │   │   ├── __init__.cpython-312.pyc
│   │           │       │   │   ├── serialize.cpython-312.pyc
│   │           │       │   │   └── wrapper.cpython-312.pyc
│   │           │       │   ├── serialize.py
│   │           │       │   └── wrapper.py
│   │           │       ├── certifi
│   │           │       │   ├── cacert.pem
│   │           │       │   ├── core.py
│   │           │       │   ├── __init__.py
│   │           │       │   ├── __main__.py
│   │           │       │   └── __pycache__
│   │           │       │       ├── core.cpython-312.pyc
│   │           │       │       ├── __init__.cpython-312.pyc
│   │           │       │       └── __main__.cpython-312.pyc
│   │           │       ├── chardet
│   │           │       │   ├── big5freq.py
│   │           │       │   ├── big5prober.py
│   │           │       │   ├── chardistribution.py
│   │           │       │   ├── charsetgroupprober.py
│   │           │       │   ├── charsetprober.py
│   │           │       │   ├── cli
│   │           │       │   │   ├── chardetect.py
│   │           │       │   │   ├── __init__.py
│   │           │       │   │   └── __pycache__
│   │           │       │   │       ├── chardetect.cpython-312.pyc
│   │           │       │   │       └── __init__.cpython-312.pyc
│   │           │       │   ├── codingstatemachinedict.py
│   │           │       │   ├── codingstatemachine.py
│   │           │       │   ├── cp949prober.py
│   │           │       │   ├── enums.py
│   │           │       │   ├── escprober.py
│   │           │       │   ├── escsm.py
│   │           │       │   ├── eucjpprober.py
│   │           │       │   ├── euckrfreq.py
│   │           │       │   ├── euckrprober.py
│   │           │       │   ├── euctwfreq.py
│   │           │       │   ├── euctwprober.py
│   │           │       │   ├── gb2312freq.py
│   │           │       │   ├── gb2312prober.py
│   │           │       │   ├── hebrewprober.py
│   │           │       │   ├── __init__.py
│   │           │       │   ├── jisfreq.py
│   │           │       │   ├── johabfreq.py
│   │           │       │   ├── johabprober.py
│   │           │       │   ├── jpcntx.py
│   │           │       │   ├── langbulgarianmodel.py
│   │           │       │   ├── langgreekmodel.py
│   │           │       │   ├── langhebrewmodel.py
│   │           │       │   ├── langhungarianmodel.py
│   │           │       │   ├── langrussianmodel.py
│   │           │       │   ├── langthaimodel.py
│   │           │       │   ├── langturkishmodel.py
│   │           │       │   ├── latin1prober.py
│   │           │       │   ├── macromanprober.py
│   │           │       │   ├── mbcharsetprober.py
│   │           │       │   ├── mbcsgroupprober.py
│   │           │       │   ├── mbcssm.py
│   │           │       │   ├── metadata
│   │           │       │   │   ├── __init__.py
│   │           │       │   │   ├── languages.py
│   │           │       │   │   └── __pycache__
│   │           │       │   │       ├── __init__.cpython-312.pyc
│   │           │       │   │       └── languages.cpython-312.pyc
│   │           │       │   ├── __pycache__
│   │           │       │   │   ├── big5freq.cpython-312.pyc
│   │           │       │   │   ├── big5prober.cpython-312.pyc
│   │           │       │   │   ├── chardistribution.cpython-312.pyc
│   │           │       │   │   ├── charsetgroupprober.cpython-312.pyc
│   │           │       │   │   ├── charsetprober.cpython-312.pyc
│   │           │       │   │   ├── codingstatemachine.cpython-312.pyc
│   │           │       │   │   ├── codingstatemachinedict.cpython-312.pyc
│   │           │       │   │   ├── cp949prober.cpython-312.pyc
│   │           │       │   │   ├── enums.cpython-312.pyc
│   │           │       │   │   ├── escprober.cpython-312.pyc
│   │           │       │   │   ├── escsm.cpython-312.pyc
│   │           │       │   │   ├── eucjpprober.cpython-312.pyc
│   │           │       │   │   ├── euckrfreq.cpython-312.pyc
│   │           │       │   │   ├── euckrprober.cpython-312.pyc
│   │           │       │   │   ├── euctwfreq.cpython-312.pyc
│   │           │       │   │   ├── euctwprober.cpython-312.pyc
│   │           │       │   │   ├── gb2312freq.cpython-312.pyc
│   │           │       │   │   ├── gb2312prober.cpython-312.pyc
│   │           │       │   │   ├── hebrewprober.cpython-312.pyc
│   │           │       │   │   ├── __init__.cpython-312.pyc
│   │           │       │   │   ├── jisfreq.cpython-312.pyc
│   │           │       │   │   ├── johabfreq.cpython-312.pyc
│   │           │       │   │   ├── johabprober.cpython-312.pyc
│   │           │       │   │   ├── jpcntx.cpython-312.pyc
│   │           │       │   │   ├── langbulgarianmodel.cpython-312.pyc
│   │           │       │   │   ├── langgreekmodel.cpython-312.pyc
│   │           │       │   │   ├── langhebrewmodel.cpython-312.pyc
│   │           │       │   │   ├── langhungarianmodel.cpython-312.pyc
│   │           │       │   │   ├── langrussianmodel.cpython-312.pyc
│   │           │       │   │   ├── langthaimodel.cpython-312.pyc
│   │           │       │   │   ├── langturkishmodel.cpython-312.pyc
│   │           │       │   │   ├── latin1prober.cpython-312.pyc
│   │           │       │   │   ├── macromanprober.cpython-312.pyc
│   │           │       │   │   ├── mbcharsetprober.cpython-312.pyc
│   │           │       │   │   ├── mbcsgroupprober.cpython-312.pyc
│   │           │       │   │   ├── mbcssm.cpython-312.pyc
│   │           │       │   │   ├── resultdict.cpython-312.pyc
│   │           │       │   │   ├── sbcharsetprober.cpython-312.pyc
│   │           │       │   │   ├── sbcsgroupprober.cpython-312.pyc
│   │           │       │   │   ├── sjisprober.cpython-312.pyc
│   │           │       │   │   ├── universaldetector.cpython-312.pyc
│   │           │       │   │   ├── utf1632prober.cpython-312.pyc
│   │           │       │   │   ├── utf8prober.cpython-312.pyc
│   │           │       │   │   └── version.cpython-312.pyc
│   │           │       │   ├── resultdict.py
│   │           │       │   ├── sbcharsetprober.py
│   │           │       │   ├── sbcsgroupprober.py
│   │           │       │   ├── sjisprober.py
│   │           │       │   ├── universaldetector.py
│   │           │       │   ├── utf1632prober.py
│   │           │       │   ├── utf8prober.py
│   │           │       │   └── version.py
│   │           │       ├── colorama
│   │           │       │   ├── ansi.py
│   │           │       │   ├── ansitowin32.py
│   │           │       │   ├── initialise.py
│   │           │       │   ├── __init__.py
│   │           │       │   ├── __pycache__
│   │           │       │   │   ├── ansi.cpython-312.pyc
│   │           │       │   │   ├── ansitowin32.cpython-312.pyc
│   │           │       │   │   ├── __init__.cpython-312.pyc
│   │           │       │   │   ├── initialise.cpython-312.pyc
│   │           │       │   │   ├── win32.cpython-312.pyc
│   │           │       │   │   └── winterm.cpython-312.pyc
│   │           │       │   ├── tests
│   │           │       │   │   ├── ansi_test.py
│   │           │       │   │   ├── ansitowin32_test.py
│   │           │       │   │   ├── initialise_test.py
│   │           │       │   │   ├── __init__.py
│   │           │       │   │   ├── isatty_test.py
│   │           │       │   │   ├── __pycache__
│   │           │       │   │   │   ├── ansi_test.cpython-312.pyc
│   │           │       │   │   │   ├── ansitowin32_test.cpython-312.pyc
│   │           │       │   │   │   ├── __init__.cpython-312.pyc
│   │           │       │   │   │   ├── initialise_test.cpython-312.pyc
│   │           │       │   │   │   ├── isatty_test.cpython-312.pyc
│   │           │       │   │   │   ├── utils.cpython-312.pyc
│   │           │       │   │   │   └── winterm_test.cpython-312.pyc
│   │           │       │   │   ├── utils.py
│   │           │       │   │   └── winterm_test.py
│   │           │       │   ├── win32.py
│   │           │       │   └── winterm.py
│   │           │       ├── distlib
│   │           │       │   ├── compat.py
│   │           │       │   ├── database.py
│   │           │       │   ├── index.py
│   │           │       │   ├── __init__.py
│   │           │       │   ├── locators.py
│   │           │       │   ├── manifest.py
│   │           │       │   ├── markers.py
│   │           │       │   ├── metadata.py
│   │           │       │   ├── __pycache__
│   │           │       │   │   ├── compat.cpython-312.pyc
│   │           │       │   │   ├── database.cpython-312.pyc
│   │           │       │   │   ├── index.cpython-312.pyc
│   │           │       │   │   ├── __init__.cpython-312.pyc
│   │           │       │   │   ├── locators.cpython-312.pyc
│   │           │       │   │   ├── manifest.cpython-312.pyc
│   │           │       │   │   ├── markers.cpython-312.pyc
│   │           │       │   │   ├── metadata.cpython-312.pyc
│   │           │       │   │   ├── resources.cpython-312.pyc
│   │           │       │   │   ├── scripts.cpython-312.pyc
│   │           │       │   │   ├── util.cpython-312.pyc
│   │           │       │   │   ├── version.cpython-312.pyc
│   │           │       │   │   └── wheel.cpython-312.pyc
│   │           │       │   ├── resources.py
│   │           │       │   ├── scripts.py
│   │           │       │   ├── util.py
│   │           │       │   ├── version.py
│   │           │       │   └── wheel.py
│   │           │       ├── distro
│   │           │       │   ├── distro.py
│   │           │       │   ├── __init__.py
│   │           │       │   ├── __main__.py
│   │           │       │   └── __pycache__
│   │           │       │       ├── distro.cpython-312.pyc
│   │           │       │       ├── __init__.cpython-312.pyc
│   │           │       │       └── __main__.cpython-312.pyc
│   │           │       ├── idna
│   │           │       │   ├── codec.py
│   │           │       │   ├── compat.py
│   │           │       │   ├── core.py
│   │           │       │   ├── idnadata.py
│   │           │       │   ├── __init__.py
│   │           │       │   ├── intranges.py
│   │           │       │   ├── package_data.py
│   │           │       │   ├── __pycache__
│   │           │       │   │   ├── codec.cpython-312.pyc
│   │           │       │   │   ├── compat.cpython-312.pyc
│   │           │       │   │   ├── core.cpython-312.pyc
│   │           │       │   │   ├── idnadata.cpython-312.pyc
│   │           │       │   │   ├── __init__.cpython-312.pyc
│   │           │       │   │   ├── intranges.cpython-312.pyc
│   │           │       │   │   ├── package_data.cpython-312.pyc
│   │           │       │   │   └── uts46data.cpython-312.pyc
│   │           │       │   └── uts46data.py
│   │           │       ├── __init__.py
│   │           │       ├── msgpack
│   │           │       │   ├── exceptions.py
│   │           │       │   ├── ext.py
│   │           │       │   ├── fallback.py
│   │           │       │   ├── __init__.py
│   │           │       │   └── __pycache__
│   │           │       │       ├── exceptions.cpython-312.pyc
│   │           │       │       ├── ext.cpython-312.pyc
│   │           │       │       ├── fallback.cpython-312.pyc
│   │           │       │       └── __init__.cpython-312.pyc
│   │           │       ├── packaging
│   │           │       │   ├── __about__.py
│   │           │       │   ├── __init__.py
│   │           │       │   ├── _manylinux.py
│   │           │       │   ├── markers.py
│   │           │       │   ├── _musllinux.py
│   │           │       │   ├── __pycache__
│   │           │       │   │   ├── __about__.cpython-312.pyc
│   │           │       │   │   ├── __init__.cpython-312.pyc
│   │           │       │   │   ├── _manylinux.cpython-312.pyc
│   │           │       │   │   ├── markers.cpython-312.pyc
│   │           │       │   │   ├── _musllinux.cpython-312.pyc
│   │           │       │   │   ├── requirements.cpython-312.pyc
│   │           │       │   │   ├── specifiers.cpython-312.pyc
│   │           │       │   │   ├── _structures.cpython-312.pyc
│   │           │       │   │   ├── tags.cpython-312.pyc
│   │           │       │   │   ├── utils.cpython-312.pyc
│   │           │       │   │   └── version.cpython-312.pyc
│   │           │       │   ├── requirements.py
│   │           │       │   ├── specifiers.py
│   │           │       │   ├── _structures.py
│   │           │       │   ├── tags.py
│   │           │       │   ├── utils.py
│   │           │       │   └── version.py
│   │           │       ├── pkg_resources
│   │           │       │   ├── __init__.py
│   │           │       │   └── __pycache__
│   │           │       │       └── __init__.cpython-312.pyc
│   │           │       ├── platformdirs
│   │           │       │   ├── android.py
│   │           │       │   ├── api.py
│   │           │       │   ├── __init__.py
│   │           │       │   ├── macos.py
│   │           │       │   ├── __main__.py
│   │           │       │   ├── __pycache__
│   │           │       │   │   ├── android.cpython-312.pyc
│   │           │       │   │   ├── api.cpython-312.pyc
│   │           │       │   │   ├── __init__.cpython-312.pyc
│   │           │       │   │   ├── macos.cpython-312.pyc
│   │           │       │   │   ├── __main__.cpython-312.pyc
│   │           │       │   │   ├── unix.cpython-312.pyc
│   │           │       │   │   ├── version.cpython-312.pyc
│   │           │       │   │   └── windows.cpython-312.pyc
│   │           │       │   ├── unix.py
│   │           │       │   ├── version.py
│   │           │       │   └── windows.py
│   │           │       ├── __pycache__
│   │           │       │   ├── __init__.cpython-312.pyc
│   │           │       │   ├── six.cpython-312.pyc
│   │           │       │   └── typing_extensions.cpython-312.pyc
│   │           │       ├── pygments
│   │           │       │   ├── cmdline.py
│   │           │       │   ├── console.py
│   │           │       │   ├── filter.py
│   │           │       │   ├── filters
│   │           │       │   │   ├── __init__.py
│   │           │       │   │   └── __pycache__
│   │           │       │   │       └── __init__.cpython-312.pyc
│   │           │       │   ├── formatter.py
│   │           │       │   ├── formatters
│   │           │       │   │   ├── bbcode.py
│   │           │       │   │   ├── groff.py
│   │           │       │   │   ├── html.py
│   │           │       │   │   ├── img.py
│   │           │       │   │   ├── __init__.py
│   │           │       │   │   ├── irc.py
│   │           │       │   │   ├── latex.py
│   │           │       │   │   ├── _mapping.py
│   │           │       │   │   ├── other.py
│   │           │       │   │   ├── pangomarkup.py
│   │           │       │   │   ├── __pycache__
│   │           │       │   │   │   ├── bbcode.cpython-312.pyc
│   │           │       │   │   │   ├── groff.cpython-312.pyc
│   │           │       │   │   │   ├── html.cpython-312.pyc
│   │           │       │   │   │   ├── img.cpython-312.pyc
│   │           │       │   │   │   ├── __init__.cpython-312.pyc
│   │           │       │   │   │   ├── irc.cpython-312.pyc
│   │           │       │   │   │   ├── latex.cpython-312.pyc
│   │           │       │   │   │   ├── _mapping.cpython-312.pyc
│   │           │       │   │   │   ├── other.cpython-312.pyc
│   │           │       │   │   │   ├── pangomarkup.cpython-312.pyc
│   │           │       │   │   │   ├── rtf.cpython-312.pyc
│   │           │       │   │   │   ├── svg.cpython-312.pyc
│   │           │       │   │   │   ├── terminal256.cpython-312.pyc
│   │           │       │   │   │   └── terminal.cpython-312.pyc
│   │           │       │   │   ├── rtf.py
│   │           │       │   │   ├── svg.py
│   │           │       │   │   ├── terminal256.py
│   │           │       │   │   └── terminal.py
│   │           │       │   ├── __init__.py
│   │           │       │   ├── lexer.py
│   │           │       │   ├── lexers
│   │           │       │   │   ├── __init__.py
│   │           │       │   │   ├── _mapping.py
│   │           │       │   │   ├── __pycache__
│   │           │       │   │   │   ├── __init__.cpython-312.pyc
│   │           │       │   │   │   ├── _mapping.cpython-312.pyc
│   │           │       │   │   │   └── python.cpython-312.pyc
│   │           │       │   │   └── python.py
│   │           │       │   ├── __main__.py
│   │           │       │   ├── modeline.py
│   │           │       │   ├── plugin.py
│   │           │       │   ├── __pycache__
│   │           │       │   │   ├── cmdline.cpython-312.pyc
│   │           │       │   │   ├── console.cpython-312.pyc
│   │           │       │   │   ├── filter.cpython-312.pyc
│   │           │       │   │   ├── formatter.cpython-312.pyc
│   │           │       │   │   ├── __init__.cpython-312.pyc
│   │           │       │   │   ├── lexer.cpython-312.pyc
│   │           │       │   │   ├── __main__.cpython-312.pyc
│   │           │       │   │   ├── modeline.cpython-312.pyc
│   │           │       │   │   ├── plugin.cpython-312.pyc
│   │           │       │   │   ├── regexopt.cpython-312.pyc
│   │           │       │   │   ├── scanner.cpython-312.pyc
│   │           │       │   │   ├── sphinxext.cpython-312.pyc
│   │           │       │   │   ├── style.cpython-312.pyc
│   │           │       │   │   ├── token.cpython-312.pyc
│   │           │       │   │   ├── unistring.cpython-312.pyc
│   │           │       │   │   └── util.cpython-312.pyc
│   │           │       │   ├── regexopt.py
│   │           │       │   ├── scanner.py
│   │           │       │   ├── sphinxext.py
│   │           │       │   ├── style.py
│   │           │       │   ├── styles
│   │           │       │   │   ├── __init__.py
│   │           │       │   │   └── __pycache__
│   │           │       │   │       └── __init__.cpython-312.pyc
│   │           │       │   ├── token.py
│   │           │       │   ├── unistring.py
│   │           │       │   └── util.py
│   │           │       ├── pyparsing
│   │           │       │   ├── actions.py
│   │           │       │   ├── common.py
│   │           │       │   ├── core.py
│   │           │       │   ├── diagram
│   │           │       │   │   ├── __init__.py
│   │           │       │   │   └── __pycache__
│   │           │       │   │       └── __init__.cpython-312.pyc
│   │           │       │   ├── exceptions.py
│   │           │       │   ├── helpers.py
│   │           │       │   ├── __init__.py
│   │           │       │   ├── __pycache__
│   │           │       │   │   ├── actions.cpython-312.pyc
│   │           │       │   │   ├── common.cpython-312.pyc
│   │           │       │   │   ├── core.cpython-312.pyc
│   │           │       │   │   ├── exceptions.cpython-312.pyc
│   │           │       │   │   ├── helpers.cpython-312.pyc
│   │           │       │   │   ├── __init__.cpython-312.pyc
│   │           │       │   │   ├── results.cpython-312.pyc
│   │           │       │   │   ├── testing.cpython-312.pyc
│   │           │       │   │   ├── unicode.cpython-312.pyc
│   │           │       │   │   └── util.cpython-312.pyc
│   │           │       │   ├── results.py
│   │           │       │   ├── testing.py
│   │           │       │   ├── unicode.py
│   │           │       │   └── util.py
│   │           │       ├── pyproject_hooks
│   │           │       │   ├── _compat.py
│   │           │       │   ├── _impl.py
│   │           │       │   ├── __init__.py
│   │           │       │   ├── _in_process
│   │           │       │   │   ├── __init__.py
│   │           │       │   │   ├── _in_process.py
│   │           │       │   │   └── __pycache__
│   │           │       │   │       ├── __init__.cpython-312.pyc
│   │           │       │   │       └── _in_process.cpython-312.pyc
│   │           │       │   └── __pycache__
│   │           │       │       ├── _compat.cpython-312.pyc
│   │           │       │       ├── _impl.cpython-312.pyc
│   │           │       │       └── __init__.cpython-312.pyc
│   │           │       ├── requests
│   │           │       │   ├── adapters.py
│   │           │       │   ├── api.py
│   │           │       │   ├── auth.py
│   │           │       │   ├── certs.py
│   │           │       │   ├── compat.py
│   │           │       │   ├── cookies.py
│   │           │       │   ├── exceptions.py
│   │           │       │   ├── help.py
│   │           │       │   ├── hooks.py
│   │           │       │   ├── __init__.py
│   │           │       │   ├── _internal_utils.py
│   │           │       │   ├── models.py
│   │           │       │   ├── packages.py
│   │           │       │   ├── __pycache__
│   │           │       │   │   ├── adapters.cpython-312.pyc
│   │           │       │   │   ├── api.cpython-312.pyc
│   │           │       │   │   ├── auth.cpython-312.pyc
│   │           │       │   │   ├── certs.cpython-312.pyc
│   │           │       │   │   ├── compat.cpython-312.pyc
│   │           │       │   │   ├── cookies.cpython-312.pyc
│   │           │       │   │   ├── exceptions.cpython-312.pyc
│   │           │       │   │   ├── help.cpython-312.pyc
│   │           │       │   │   ├── hooks.cpython-312.pyc
│   │           │       │   │   ├── __init__.cpython-312.pyc
│   │           │       │   │   ├── _internal_utils.cpython-312.pyc
│   │           │       │   │   ├── models.cpython-312.pyc
│   │           │       │   │   ├── packages.cpython-312.pyc
│   │           │       │   │   ├── sessions.cpython-312.pyc
│   │           │       │   │   ├── status_codes.cpython-312.pyc
│   │           │       │   │   ├── structures.cpython-312.pyc
│   │           │       │   │   ├── utils.cpython-312.pyc
│   │           │       │   │   └── __version__.cpython-312.pyc
│   │           │       │   ├── sessions.py
│   │           │       │   ├── status_codes.py
│   │           │       │   ├── structures.py
│   │           │       │   ├── utils.py
│   │           │       │   └── __version__.py
│   │           │       ├── resolvelib
│   │           │       │   ├── compat
│   │           │       │   │   ├── collections_abc.py
│   │           │       │   │   ├── __init__.py
│   │           │       │   │   └── __pycache__
│   │           │       │   │       ├── collections_abc.cpython-312.pyc
│   │           │       │   │       └── __init__.cpython-312.pyc
│   │           │       │   ├── __init__.py
│   │           │       │   ├── providers.py
│   │           │       │   ├── __pycache__
│   │           │       │   │   ├── __init__.cpython-312.pyc
│   │           │       │   │   ├── providers.cpython-312.pyc
│   │           │       │   │   ├── reporters.cpython-312.pyc
│   │           │       │   │   ├── resolvers.cpython-312.pyc
│   │           │       │   │   └── structs.cpython-312.pyc
│   │           │       │   ├── reporters.py
│   │           │       │   ├── resolvers.py
│   │           │       │   └── structs.py
│   │           │       ├── rich
│   │           │       │   ├── abc.py
│   │           │       │   ├── align.py
│   │           │       │   ├── ansi.py
│   │           │       │   ├── bar.py
│   │           │       │   ├── box.py
│   │           │       │   ├── cells.py
│   │           │       │   ├── _cell_widths.py
│   │           │       │   ├── color.py
│   │           │       │   ├── color_triplet.py
│   │           │       │   ├── columns.py
│   │           │       │   ├── console.py
│   │           │       │   ├── constrain.py
│   │           │       │   ├── containers.py
│   │           │       │   ├── control.py
│   │           │       │   ├── default_styles.py
│   │           │       │   ├── diagnose.py
│   │           │       │   ├── _emoji_codes.py
│   │           │       │   ├── emoji.py
│   │           │       │   ├── _emoji_replace.py
│   │           │       │   ├── errors.py
│   │           │       │   ├── _export_format.py
│   │           │       │   ├── _extension.py
│   │           │       │   ├── _fileno.py
│   │           │       │   ├── file_proxy.py
│   │           │       │   ├── filesize.py
│   │           │       │   ├── highlighter.py
│   │           │       │   ├── __init__.py
│   │           │       │   ├── _inspect.py
│   │           │       │   ├── json.py
│   │           │       │   ├── jupyter.py
│   │           │       │   ├── layout.py
│   │           │       │   ├── live.py
│   │           │       │   ├── live_render.py
│   │           │       │   ├── logging.py
│   │           │       │   ├── _log_render.py
│   │           │       │   ├── _loop.py
│   │           │       │   ├── __main__.py
│   │           │       │   ├── markup.py
│   │           │       │   ├── measure.py
│   │           │       │   ├── _null_file.py
│   │           │       │   ├── padding.py
│   │           │       │   ├── pager.py
│   │           │       │   ├── palette.py
│   │           │       │   ├── _palettes.py
│   │           │       │   ├── panel.py
│   │           │       │   ├── _pick.py
│   │           │       │   ├── pretty.py
│   │           │       │   ├── progress_bar.py
│   │           │       │   ├── progress.py
│   │           │       │   ├── prompt.py
│   │           │       │   ├── protocol.py
│   │           │       │   ├── __pycache__
│   │           │       │   │   ├── abc.cpython-312.pyc
│   │           │       │   │   ├── align.cpython-312.pyc
│   │           │       │   │   ├── ansi.cpython-312.pyc
│   │           │       │   │   ├── bar.cpython-312.pyc
│   │           │       │   │   ├── box.cpython-312.pyc
│   │           │       │   │   ├── cells.cpython-312.pyc
│   │           │       │   │   ├── _cell_widths.cpython-312.pyc
│   │           │       │   │   ├── color.cpython-312.pyc
│   │           │       │   │   ├── color_triplet.cpython-312.pyc
│   │           │       │   │   ├── columns.cpython-312.pyc
│   │           │       │   │   ├── console.cpython-312.pyc
│   │           │       │   │   ├── constrain.cpython-312.pyc
│   │           │       │   │   ├── containers.cpython-312.pyc
│   │           │       │   │   ├── control.cpython-312.pyc
│   │           │       │   │   ├── default_styles.cpython-312.pyc
│   │           │       │   │   ├── diagnose.cpython-312.pyc
│   │           │       │   │   ├── _emoji_codes.cpython-312.pyc
│   │           │       │   │   ├── emoji.cpython-312.pyc
│   │           │       │   │   ├── _emoji_replace.cpython-312.pyc
│   │           │       │   │   ├── errors.cpython-312.pyc
│   │           │       │   │   ├── _export_format.cpython-312.pyc
│   │           │       │   │   ├── _extension.cpython-312.pyc
│   │           │       │   │   ├── _fileno.cpython-312.pyc
│   │           │       │   │   ├── file_proxy.cpython-312.pyc
│   │           │       │   │   ├── filesize.cpython-312.pyc
│   │           │       │   │   ├── highlighter.cpython-312.pyc
│   │           │       │   │   ├── __init__.cpython-312.pyc
│   │           │       │   │   ├── _inspect.cpython-312.pyc
│   │           │       │   │   ├── json.cpython-312.pyc
│   │           │       │   │   ├── jupyter.cpython-312.pyc
│   │           │       │   │   ├── layout.cpython-312.pyc
│   │           │       │   │   ├── live.cpython-312.pyc
│   │           │       │   │   ├── live_render.cpython-312.pyc
│   │           │       │   │   ├── logging.cpython-312.pyc
│   │           │       │   │   ├── _log_render.cpython-312.pyc
│   │           │       │   │   ├── _loop.cpython-312.pyc
│   │           │       │   │   ├── __main__.cpython-312.pyc
│   │           │       │   │   ├── markup.cpython-312.pyc
│   │           │       │   │   ├── measure.cpython-312.pyc
│   │           │       │   │   ├── _null_file.cpython-312.pyc
│   │           │       │   │   ├── padding.cpython-312.pyc
│   │           │       │   │   ├── pager.cpython-312.pyc
│   │           │       │   │   ├── palette.cpython-312.pyc
│   │           │       │   │   ├── _palettes.cpython-312.pyc
│   │           │       │   │   ├── panel.cpython-312.pyc
│   │           │       │   │   ├── _pick.cpython-312.pyc
│   │           │       │   │   ├── pretty.cpython-312.pyc
│   │           │       │   │   ├── progress_bar.cpython-312.pyc
│   │           │       │   │   ├── progress.cpython-312.pyc
│   │           │       │   │   ├── prompt.cpython-312.pyc
│   │           │       │   │   ├── protocol.cpython-312.pyc
│   │           │       │   │   ├── _ratio.cpython-312.pyc
│   │           │       │   │   ├── region.cpython-312.pyc
│   │           │       │   │   ├── repr.cpython-312.pyc
│   │           │       │   │   ├── rule.cpython-312.pyc
│   │           │       │   │   ├── scope.cpython-312.pyc
│   │           │       │   │   ├── screen.cpython-312.pyc
│   │           │       │   │   ├── segment.cpython-312.pyc
│   │           │       │   │   ├── spinner.cpython-312.pyc
│   │           │       │   │   ├── _spinners.cpython-312.pyc
│   │           │       │   │   ├── _stack.cpython-312.pyc
│   │           │       │   │   ├── status.cpython-312.pyc
│   │           │       │   │   ├── style.cpython-312.pyc
│   │           │       │   │   ├── styled.cpython-312.pyc
│   │           │       │   │   ├── syntax.cpython-312.pyc
│   │           │       │   │   ├── table.cpython-312.pyc
│   │           │       │   │   ├── terminal_theme.cpython-312.pyc
│   │           │       │   │   ├── text.cpython-312.pyc
│   │           │       │   │   ├── theme.cpython-312.pyc
│   │           │       │   │   ├── themes.cpython-312.pyc
│   │           │       │   │   ├── _timer.cpython-312.pyc
│   │           │       │   │   ├── traceback.cpython-312.pyc
│   │           │       │   │   ├── tree.cpython-312.pyc
│   │           │       │   │   ├── _win32_console.cpython-312.pyc
│   │           │       │   │   ├── _windows.cpython-312.pyc
│   │           │       │   │   ├── _windows_renderer.cpython-312.pyc
│   │           │       │   │   └── _wrap.cpython-312.pyc
│   │           │       │   ├── _ratio.py
│   │           │       │   ├── region.py
│   │           │       │   ├── repr.py
│   │           │       │   ├── rule.py
│   │           │       │   ├── scope.py
│   │           │       │   ├── screen.py
│   │           │       │   ├── segment.py
│   │           │       │   ├── spinner.py
│   │           │       │   ├── _spinners.py
│   │           │       │   ├── _stack.py
│   │           │       │   ├── status.py
│   │           │       │   ├── styled.py
│   │           │       │   ├── style.py
│   │           │       │   ├── syntax.py
│   │           │       │   ├── table.py
│   │           │       │   ├── terminal_theme.py
│   │           │       │   ├── text.py
│   │           │       │   ├── theme.py
│   │           │       │   ├── themes.py
│   │           │       │   ├── _timer.py
│   │           │       │   ├── traceback.py
│   │           │       │   ├── tree.py
│   │           │       │   ├── _win32_console.py
│   │           │       │   ├── _windows.py
│   │           │       │   ├── _windows_renderer.py
│   │           │       │   └── _wrap.py
│   │           │       ├── six.py
│   │           │       ├── tenacity
│   │           │       │   ├── after.py
│   │           │       │   ├── _asyncio.py
│   │           │       │   ├── before.py
│   │           │       │   ├── before_sleep.py
│   │           │       │   ├── __init__.py
│   │           │       │   ├── nap.py
│   │           │       │   ├── __pycache__
│   │           │       │   │   ├── after.cpython-312.pyc
│   │           │       │   │   ├── _asyncio.cpython-312.pyc
│   │           │       │   │   ├── before.cpython-312.pyc
│   │           │       │   │   ├── before_sleep.cpython-312.pyc
│   │           │       │   │   ├── __init__.cpython-312.pyc
│   │           │       │   │   ├── nap.cpython-312.pyc
│   │           │       │   │   ├── retry.cpython-312.pyc
│   │           │       │   │   ├── stop.cpython-312.pyc
│   │           │       │   │   ├── tornadoweb.cpython-312.pyc
│   │           │       │   │   ├── _utils.cpython-312.pyc
│   │           │       │   │   └── wait.cpython-312.pyc
│   │           │       │   ├── retry.py
│   │           │       │   ├── stop.py
│   │           │       │   ├── tornadoweb.py
│   │           │       │   ├── _utils.py
│   │           │       │   └── wait.py
│   │           │       ├── tomli
│   │           │       │   ├── __init__.py
│   │           │       │   ├── _parser.py
│   │           │       │   ├── __pycache__
│   │           │       │   │   ├── __init__.cpython-312.pyc
│   │           │       │   │   ├── _parser.cpython-312.pyc
│   │           │       │   │   ├── _re.cpython-312.pyc
│   │           │       │   │   └── _types.cpython-312.pyc
│   │           │       │   ├── _re.py
│   │           │       │   └── _types.py
│   │           │       ├── truststore
│   │           │       │   ├── _api.py
│   │           │       │   ├── __init__.py
│   │           │       │   ├── _macos.py
│   │           │       │   ├── _openssl.py
│   │           │       │   ├── __pycache__
│   │           │       │   │   ├── _api.cpython-312.pyc
│   │           │       │   │   ├── __init__.cpython-312.pyc
│   │           │       │   │   ├── _macos.cpython-312.pyc
│   │           │       │   │   ├── _openssl.cpython-312.pyc
│   │           │       │   │   ├── _ssl_constants.cpython-312.pyc
│   │           │       │   │   └── _windows.cpython-312.pyc
│   │           │       │   ├── _ssl_constants.py
│   │           │       │   └── _windows.py
│   │           │       ├── typing_extensions.py
│   │           │       ├── urllib3
│   │           │       │   ├── _collections.py
│   │           │       │   ├── connectionpool.py
│   │           │       │   ├── connection.py
│   │           │       │   ├── contrib
│   │           │       │   │   ├── _appengine_environ.py
│   │           │       │   │   ├── appengine.py
│   │           │       │   │   ├── __init__.py
│   │           │       │   │   ├── ntlmpool.py
│   │           │       │   │   ├── __pycache__
│   │           │       │   │   │   ├── appengine.cpython-312.pyc
│   │           │       │   │   │   ├── _appengine_environ.cpython-312.pyc
│   │           │       │   │   │   ├── __init__.cpython-312.pyc
│   │           │       │   │   │   ├── ntlmpool.cpython-312.pyc
│   │           │       │   │   │   ├── pyopenssl.cpython-312.pyc
│   │           │       │   │   │   ├── securetransport.cpython-312.pyc
│   │           │       │   │   │   └── socks.cpython-312.pyc
│   │           │       │   │   ├── pyopenssl.py
│   │           │       │   │   ├── _securetransport
│   │           │       │   │   │   ├── bindings.py
│   │           │       │   │   │   ├── __init__.py
│   │           │       │   │   │   ├── low_level.py
│   │           │       │   │   │   └── __pycache__
│   │           │       │   │   │       ├── bindings.cpython-312.pyc
│   │           │       │   │   │       ├── __init__.cpython-312.pyc
│   │           │       │   │   │       └── low_level.cpython-312.pyc
│   │           │       │   │   ├── securetransport.py
│   │           │       │   │   └── socks.py
│   │           │       │   ├── exceptions.py
│   │           │       │   ├── fields.py
│   │           │       │   ├── filepost.py
│   │           │       │   ├── __init__.py
│   │           │       │   ├── packages
│   │           │       │   │   ├── backports
│   │           │       │   │   │   ├── __init__.py
│   │           │       │   │   │   ├── makefile.py
│   │           │       │   │   │   ├── __pycache__
│   │           │       │   │   │   │   ├── __init__.cpython-312.pyc
│   │           │       │   │   │   │   ├── makefile.cpython-312.pyc
│   │           │       │   │   │   │   └── weakref_finalize.cpython-312.pyc
│   │           │       │   │   │   └── weakref_finalize.py
│   │           │       │   │   ├── __init__.py
│   │           │       │   │   ├── __pycache__
│   │           │       │   │   │   ├── __init__.cpython-312.pyc
│   │           │       │   │   │   └── six.cpython-312.pyc
│   │           │       │   │   └── six.py
│   │           │       │   ├── poolmanager.py
│   │           │       │   ├── __pycache__
│   │           │       │   │   ├── _collections.cpython-312.pyc
│   │           │       │   │   ├── connection.cpython-312.pyc
│   │           │       │   │   ├── connectionpool.cpython-312.pyc
│   │           │       │   │   ├── exceptions.cpython-312.pyc
│   │           │       │   │   ├── fields.cpython-312.pyc
│   │           │       │   │   ├── filepost.cpython-312.pyc
│   │           │       │   │   ├── __init__.cpython-312.pyc
│   │           │       │   │   ├── poolmanager.cpython-312.pyc
│   │           │       │   │   ├── request.cpython-312.pyc
│   │           │       │   │   ├── response.cpython-312.pyc
│   │           │       │   │   └── _version.cpython-312.pyc
│   │           │       │   ├── request.py
│   │           │       │   ├── response.py
│   │           │       │   ├── util
│   │           │       │   │   ├── connection.py
│   │           │       │   │   ├── __init__.py
│   │           │       │   │   ├── proxy.py
│   │           │       │   │   ├── __pycache__
│   │           │       │   │   │   ├── connection.cpython-312.pyc
│   │           │       │   │   │   ├── __init__.cpython-312.pyc
│   │           │       │   │   │   ├── proxy.cpython-312.pyc
│   │           │       │   │   │   ├── queue.cpython-312.pyc
│   │           │       │   │   │   ├── request.cpython-312.pyc
│   │           │       │   │   │   ├── response.cpython-312.pyc
│   │           │       │   │   │   ├── retry.cpython-312.pyc
│   │           │       │   │   │   ├── ssl_.cpython-312.pyc
│   │           │       │   │   │   ├── ssl_match_hostname.cpython-312.pyc
│   │           │       │   │   │   ├── ssltransport.cpython-312.pyc
│   │           │       │   │   │   ├── timeout.cpython-312.pyc
│   │           │       │   │   │   ├── url.cpython-312.pyc
│   │           │       │   │   │   └── wait.cpython-312.pyc
│   │           │       │   │   ├── queue.py
│   │           │       │   │   ├── request.py
│   │           │       │   │   ├── response.py
│   │           │       │   │   ├── retry.py
│   │           │       │   │   ├── ssl_match_hostname.py
│   │           │       │   │   ├── ssl_.py
│   │           │       │   │   ├── ssltransport.py
│   │           │       │   │   ├── timeout.py
│   │           │       │   │   ├── url.py
│   │           │       │   │   └── wait.py
│   │           │       │   └── _version.py
│   │           │       ├── vendor.txt
│   │           │       └── webencodings
│   │           │           ├── __init__.py
│   │           │           ├── labels.py
│   │           │           ├── mklabels.py
│   │           │           ├── __pycache__
│   │           │           │   ├── __init__.cpython-312.pyc
│   │           │           │   ├── labels.cpython-312.pyc
│   │           │           │   ├── mklabels.cpython-312.pyc
│   │           │           │   ├── tests.cpython-312.pyc
│   │           │           │   └── x_user_defined.cpython-312.pyc
│   │           │           ├── tests.py
│   │           │           └── x_user_defined.py
│   │           ├── pip-24.0.dist-info
│   │           │   ├── AUTHORS.txt
│   │           │   ├── entry_points.txt
│   │           │   ├── INSTALLER
│   │           │   ├── LICENSE.txt
│   │           │   ├── METADATA
│   │           │   ├── RECORD
│   │           │   ├── REQUESTED
│   │           │   ├── top_level.txt
│   │           │   └── WHEEL
│   │           ├── __pycache__
│   │           │   └── argparse.cpython-312.pyc
│   │           ├── pyyaml-6.0.3.dist-info
│   │           │   ├── INSTALLER
│   │           │   ├── licenses
│   │           │   │   └── LICENSE
│   │           │   ├── METADATA
│   │           │   ├── RECORD
│   │           │   ├── REQUESTED
│   │           │   ├── top_level.txt
│   │           │   └── WHEEL
│   │           ├── requests
│   │           │   ├── adapters.py
│   │           │   ├── api.py
│   │           │   ├── auth.py
│   │           │   ├── certs.py
│   │           │   ├── compat.py
│   │           │   ├── cookies.py
│   │           │   ├── exceptions.py
│   │           │   ├── help.py
│   │           │   ├── hooks.py
│   │           │   ├── __init__.py
│   │           │   ├── _internal_utils.py
│   │           │   ├── models.py
│   │           │   ├── packages.py
│   │           │   ├── __pycache__
│   │           │   │   ├── adapters.cpython-312.pyc
│   │           │   │   ├── api.cpython-312.pyc
│   │           │   │   ├── auth.cpython-312.pyc
│   │           │   │   ├── certs.cpython-312.pyc
│   │           │   │   ├── compat.cpython-312.pyc
│   │           │   │   ├── cookies.cpython-312.pyc
│   │           │   │   ├── exceptions.cpython-312.pyc
│   │           │   │   ├── help.cpython-312.pyc
│   │           │   │   ├── hooks.cpython-312.pyc
│   │           │   │   ├── __init__.cpython-312.pyc
│   │           │   │   ├── _internal_utils.cpython-312.pyc
│   │           │   │   ├── models.cpython-312.pyc
│   │           │   │   ├── packages.cpython-312.pyc
│   │           │   │   ├── sessions.cpython-312.pyc
│   │           │   │   ├── status_codes.cpython-312.pyc
│   │           │   │   ├── structures.cpython-312.pyc
│   │           │   │   ├── utils.cpython-312.pyc
│   │           │   │   └── __version__.cpython-312.pyc
│   │           │   ├── sessions.py
│   │           │   ├── status_codes.py
│   │           │   ├── structures.py
│   │           │   ├── utils.py
│   │           │   └── __version__.py
│   │           ├── requests-2.32.5.dist-info
│   │           │   ├── INSTALLER
│   │           │   ├── licenses
│   │           │   │   └── LICENSE
│   │           │   ├── METADATA
│   │           │   ├── RECORD
│   │           │   ├── top_level.txt
│   │           │   └── WHEEL
│   │           ├── sandpiper
│   │           │   ├── __init__.py
│   │           │   ├── __main__.py
│   │           │   └── __pycache__
│   │           │       ├── __init__.cpython-312.pyc
│   │           │       └── __main__.cpython-312.pyc
│   │           ├── sandpiper_saas-1.1.0.dist-info
│   │           │   ├── entry_points.txt
│   │           │   ├── INSTALLER
│   │           │   ├── LICENSE.md
│   │           │   ├── METADATA
│   │           │   ├── RECORD
│   │           │   ├── REQUESTED
│   │           │   ├── top_level.txt
│   │           │   └── WHEEL
│   │           ├── urllib3
│   │           │   ├── _base_connection.py
│   │           │   ├── _collections.py
│   │           │   ├── connectionpool.py
│   │           │   ├── connection.py
│   │           │   ├── contrib
│   │           │   │   ├── emscripten
│   │           │   │   │   ├── connection.py
│   │           │   │   │   ├── emscripten_fetch_worker.js
│   │           │   │   │   ├── fetch.py
│   │           │   │   │   ├── __init__.py
│   │           │   │   │   ├── __pycache__
│   │           │   │   │   │   ├── connection.cpython-312.pyc
│   │           │   │   │   │   ├── fetch.cpython-312.pyc
│   │           │   │   │   │   ├── __init__.cpython-312.pyc
│   │           │   │   │   │   ├── request.cpython-312.pyc
│   │           │   │   │   │   └── response.cpython-312.pyc
│   │           │   │   │   ├── request.py
│   │           │   │   │   └── response.py
│   │           │   │   ├── __init__.py
│   │           │   │   ├── __pycache__
│   │           │   │   │   ├── __init__.cpython-312.pyc
│   │           │   │   │   ├── pyopenssl.cpython-312.pyc
│   │           │   │   │   └── socks.cpython-312.pyc
│   │           │   │   ├── pyopenssl.py
│   │           │   │   └── socks.py
│   │           │   ├── exceptions.py
│   │           │   ├── fields.py
│   │           │   ├── filepost.py
│   │           │   ├── http2
│   │           │   │   ├── connection.py
│   │           │   │   ├── __init__.py
│   │           │   │   ├── probe.py
│   │           │   │   └── __pycache__
│   │           │   │       ├── connection.cpython-312.pyc
│   │           │   │       ├── __init__.cpython-312.pyc
│   │           │   │       └── probe.cpython-312.pyc
│   │           │   ├── __init__.py
│   │           │   ├── poolmanager.py
│   │           │   ├── __pycache__
│   │           │   │   ├── _base_connection.cpython-312.pyc
│   │           │   │   ├── _collections.cpython-312.pyc
│   │           │   │   ├── connection.cpython-312.pyc
│   │           │   │   ├── connectionpool.cpython-312.pyc
│   │           │   │   ├── exceptions.cpython-312.pyc
│   │           │   │   ├── fields.cpython-312.pyc
│   │           │   │   ├── filepost.cpython-312.pyc
│   │           │   │   ├── __init__.cpython-312.pyc
│   │           │   │   ├── poolmanager.cpython-312.pyc
│   │           │   │   ├── _request_methods.cpython-312.pyc
│   │           │   │   ├── response.cpython-312.pyc
│   │           │   │   └── _version.cpython-312.pyc
│   │           │   ├── py.typed
│   │           │   ├── _request_methods.py
│   │           │   ├── response.py
│   │           │   ├── util
│   │           │   │   ├── connection.py
│   │           │   │   ├── __init__.py
│   │           │   │   ├── proxy.py
│   │           │   │   ├── __pycache__
│   │           │   │   │   ├── connection.cpython-312.pyc
│   │           │   │   │   ├── __init__.cpython-312.pyc
│   │           │   │   │   ├── proxy.cpython-312.pyc
│   │           │   │   │   ├── request.cpython-312.pyc
│   │           │   │   │   ├── response.cpython-312.pyc
│   │           │   │   │   ├── retry.cpython-312.pyc
│   │           │   │   │   ├── ssl_.cpython-312.pyc
│   │           │   │   │   ├── ssl_match_hostname.cpython-312.pyc
│   │           │   │   │   ├── ssltransport.cpython-312.pyc
│   │           │   │   │   ├── timeout.cpython-312.pyc
│   │           │   │   │   ├── url.cpython-312.pyc
│   │           │   │   │   ├── util.cpython-312.pyc
│   │           │   │   │   └── wait.cpython-312.pyc
│   │           │   │   ├── request.py
│   │           │   │   ├── response.py
│   │           │   │   ├── retry.py
│   │           │   │   ├── ssl_match_hostname.py
│   │           │   │   ├── ssl_.py
│   │           │   │   ├── ssltransport.py
│   │           │   │   ├── timeout.py
│   │           │   │   ├── url.py
│   │           │   │   ├── util.py
│   │           │   │   └── wait.py
│   │           │   └── _version.py
│   │           ├── urllib3-2.5.0.dist-info
│   │           │   ├── INSTALLER
│   │           │   ├── licenses
│   │           │   │   └── LICENSE.txt
│   │           │   ├── METADATA
│   │           │   ├── RECORD
│   │           │   └── WHEEL
│   │           ├── _yaml
│   │           │   ├── __init__.py
│   │           │   └── __pycache__
│   │           │       └── __init__.cpython-312.pyc
│   │           └── yaml
│   │               ├── composer.py
│   │               ├── constructor.py
│   │               ├── cyaml.py
│   │               ├── dumper.py
│   │               ├── emitter.py
│   │               ├── error.py
│   │               ├── events.py
│   │               ├── __init__.py
│   │               ├── loader.py
│   │               ├── nodes.py
│   │               ├── parser.py
│   │               ├── __pycache__
│   │               │   ├── composer.cpython-312.pyc
│   │               │   ├── constructor.cpython-312.pyc
│   │               │   ├── cyaml.cpython-312.pyc
│   │               │   ├── dumper.cpython-312.pyc
│   │               │   ├── emitter.cpython-312.pyc
│   │               │   ├── error.cpython-312.pyc
│   │               │   ├── events.cpython-312.pyc
│   │               │   ├── __init__.cpython-312.pyc
│   │               │   ├── loader.cpython-312.pyc
│   │               │   ├── nodes.cpython-312.pyc
│   │               │   ├── parser.cpython-312.pyc
│   │               │   ├── reader.cpython-312.pyc
│   │               │   ├── representer.cpython-312.pyc
│   │               │   ├── resolver.cpython-312.pyc
│   │               │   ├── scanner.cpython-312.pyc
│   │               │   ├── serializer.cpython-312.pyc
│   │               │   └── tokens.cpython-312.pyc
│   │               ├── reader.py
│   │               ├── representer.py
│   │               ├── resolver.py
│   │               ├── scanner.py
│   │               ├── serializer.py
│   │               ├── tokens.py
│   │               └── _yaml.cpython-312-x86_64-linux-gnu.so
│   ├── lib64 -> lib
│   └── pyvenv.cfg
├── src
│   ├── gds
│   │   ├── avsddac.gds
│   │   └── avsdpll.gds
│   ├── gls_model
│   │   ├── primitives.v
│   │   └── sky130_fd_sc_hd.v
│   ├── include
│   │   ├── sandpiper_gen.vh
│   │   ├── sandpiper.vh
│   │   ├── sp_default.vh
│   │   └── sp_verilog.vh
│   ├── layout_conf
│   │   ├── rvmyth
│   │   │   ├── config.tcl
│   │   │   └── pin_order.cfg
│   │   └── vsdbabysoc
│   │       ├── config.tcl
│   │       ├── macro.cfg
│   │       └── pin_order.cfg
│   ├── lef
│   │   ├── avsddac.lef
│   │   └── avsdpll.lef
│   ├── lib
│   │   ├── avsddac.lib
│   │   ├── avsdpll.lib
│   │   └── sky130_fd_sc_hd__tt_025C_1v80.lib
│   ├── module
│   │   ├── avsddac.v
│   │   ├── avsdpll.v
│   │   ├── clk_gate.v
│   │   ├── primitives.v
│   │   ├── pseudo_rand_gen.sv
│   │   ├── pseudo_rand.sv
│   │   ├── rvmyth_gen.v
│   │   ├── rvmyth.tlv
│   │   ├── rvmyth.v
│   │   ├── sky130_fd_sc_hd.v
│   │   ├── testbench.rvmyth.post-routing.v
│   │   ├── testbench.v
│   │   ├── vsdbabysoc.synth.v
│   │   └── vsdbabysoc.v
│   ├── script
│   │   ├── sta.conf
│   │   ├── verilog_to_lib.pl
│   │   └── yosys.ys
│   └── sdc
│       ├── vsdbabysoc_layout.sdc
│       └── vsdbabysoc_synthesis.sdc
└── vsdbabysoc.synth.v

194 directories, 1387 files
```
Here the structure might look lengthy but most of the files are part of `` sp_env`` directory which we will be creating and defining soon.
The simplified or minimized form of the structure is as follows

<img width="2829" height="2498" alt="project_structure" src="https://github.com/user-attachments/assets/27e2d8de-d58f-43d0-a214-b057d8dc6884" />

to get this structure or for the rtl files of ``VSDBabySoc`` use the following command in linux terminal

```
git clone https://github.com/manili/VSDBabySoC.git
```
now lets go into the directory and check if the files are available

<img width="1231" height="269" alt="rtl_files" src="https://github.com/user-attachments/assets/624e6c98-0ee9-40f7-96ed-64904a6268ac" />

these are the rtl files or modules of the SoC, we will  simulate and check their functionality

But we see that the ``rvmyth.tlv`` file is in ``.tlv`` format, but for synthesis ``.tlv`` format isnt supported. 

# TLV to Verilog Conversion for RVMYTH

Initially, you will see only the rvmyth.tlv file inside src/module/, since the RVMYTH core is written in TL-Verilog. To convert it into a .v file for simulation, follow the steps below:

```
# Step 1: Install python3-venv 

sudo apt update
sudo apt install python3-venv python3-pip

# Step 2: Create and activate a virtual environment

cd VSDBabySoC/
python3 -m venv sp_env
source sp_env/bin/activate

# Step 3: Install SandPiper-SaaS inside the virtual environment

pip install pyyaml click sandpiper-saas

# Step 4: Convert rvmyth.tlv to Verilog

sandpiper-saas -i ./src/module/*.tlv -o rvmyth.v --bestsv --noline -p verilog --outdir ./src/module/
```

Now that we got the verilog file for this too, lets proceed with simulations

# Pre-Synthesis Simulation Flow

- We will simulate the RTL using Iverilog and verify its functionality before synthesis
- Macro: -DPRE_SYNTH_SIM
- the outputs of the simulation are stored in the ``output/pre_synth_sim/pre_Synth_sim.out`` and ``output/pre_synth_sim/pre_Synth_sim.vcd``
- ``.out`` is used to finish simulation and write the output into ``.vcd`` file
- ``.vcd`` file is used to check the output waveform in ``gtkwave`` tool

The following command is used to run simulation of the code with all the modules included 

``
iverilog -o output/pre_synth_sim/pre_synth_sim.out   -DPRE_SYNTH_SIM   -I src/include   -I src/module   src/module/testbench.v
``

the following is the terminal log of the entire simulation flow

<img width="3568" height="984" alt="presynthesis_log" src="https://github.com/user-attachments/assets/8ee8b8a3-bb3c-4de2-a919-dc6fbee1b801" />

Now by looking at the waveform , we see the following 

<img width="3974" height="1755" alt="pre_synth_sim" src="https://github.com/user-attachments/assets/5801ae0c-7e9c-4b76-ab09-ab0f9121b4c2" />

<img width="3974" height="1755" alt="pre_synth_sim_zoom" src="https://github.com/user-attachments/assets/4cd75758-06ed-460f-8aba-a528f8980498" />

the above plotted waveform is on clk , reset , output of design , DAC signal and output of DAC.

this waveform can be used as reference behaviour of the RTL of ``VSDBABYSOC``

# Synthesis Flow

Now that we have the Pre-synthesis simulation done , we are going to use ``Yosys`` tool to perform synthesis

The purpose of doing synthesis is to get the netlist of the design and perform GLS or post synthesis Simulation to check if the design is having good behaviour even after synthesis

The following are the steps to perform synthesis for this Soc Design

- To invoke Yosys tool

```
Yosys
```

- To read the library files

```
read_liberty -lib /home/jitesh/SOC/sky130RTLDesignAndSynthesisWorkshop/lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_liberty -lib src/lib/avsddac.lib
 
read_liberty -lib src/lib/avsdpll.lib

read_liberty -lib src/lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```

- To read the verilog files
  
```
read_verilog  -sv -I src/include/ -I src/module/ src/module/vsdbabysoc.v src/module/clk_gate.v src/module/rvmyth.v
```

- To define the top module for synthesis

```
synth -top vsdbabysoc
```

<img width="1685" height="1810" alt="Screenshot from 2025-10-04 12-20-50" src="https://github.com/user-attachments/assets/27c433e2-2692-426c-8d46-a10cd10820ed" />

<img width="2109" height="2247" alt="Screenshot from 2025-10-04 12-21-04" src="https://github.com/user-attachments/assets/62f3937e-05b5-44d9-9085-d624d774b9d3" />

- To map the dff with the library file

```
dfflibmap -liberty /home/jitesh/SOC/sky130RTLDesignAndSynthesisWorkshop/lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```

- To run the synthesis

```
abc -liberty src/lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```

- To write the netlist

```
write_verilog vsdbabysoc.synth.v
```

- To check the visual representation of the netlist

```
show vsdbabysoc
```

<img width="3963" height="752" alt="vsdbabysoc_show" src="https://github.com/user-attachments/assets/838f951b-6a95-4743-a0cc-5d559ff58391" />


Now that the synthesis is done , lets verify if its functionality is same for post synthesis simulation too.

# Post Synthesis Simulation Flow

- Here we will compile the netlist along with the standard cells from the library with Iverilog
- Macro: -DPOST_SYNTH_SIM
- the outputs of the simulation are stored in the ``output/post_synth_sim/post_Synth_sim.out`` and ``output/post_synth_sim/post_Synth_sim.vcd``
- ``.out`` is used to finish simulation and write the output into ``.vcd`` file
- ``.vcd`` file is used to check the output waveform in ``gtkwave`` tool

Before we start this simulation, to avoid errors , we have to copy and paste ``primitives.v`` and  ``sky130_fd_sc_hd.v`` in ``src/module`` . This is so because the testbench file will include these two files into simulation here , if these files are not placed here , the compiler might throw errors of misssing or file found when simulation is done.

Now the command to run post synthesis simulation is as follows

```
iverilog -o output/post_synth_sim/post_synth_sim.out -DPOST_SYNTH_SIM  -I src/include/ -I src/module/ src/module/testbench.v
```

The following is terminal log of the simulation flow done 

<img width="3573" height="774" alt="post_synth_log" src="https://github.com/user-attachments/assets/2bb5c780-f1d7-4045-9baa-77c8da96ab66" />

By looking at the waveform , same signals are plotted here too as we did with pre-synthesis simulation and we notce that the behaviour is same.

<img width="3973" height="1452" alt="post_synthesis_gtkwave" src="https://github.com/user-attachments/assets/563f7e15-a22d-4e09-9067-b41de4d9070b" />

<img width="3973" height="1452" alt="post_synth_gtkwave_zoom" src="https://github.com/user-attachments/assets/44e553e0-c383-4949-9c47-3579b0ba94a0" />












