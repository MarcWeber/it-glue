# godot_libc_dependency_pool_example

This challenge requires 
- godot headers.
- A godot plugin.
- A libvnc godotplugin which depends on scons.
and libvnc C library which itself depends on libpng and libjpg which on
Windows/Linux use Windows / configure+make tooling

      TODO:
        git_with_topic_branch = (repo) => git({repo, uploda_to: my_bare_location, story-branch-name: story_name })

      openssl      = git_with_topic_branch('x/libopenssl')
      libjpeg      = git_with_topic_branch('x/libjpeg')
      libpng       = git_with_topic_branch('x/libpng')

      godot_cpp_headers_4  = git:('x/libpng')
      godot_cpp_headers_3  = git:('x/libpng')

      godot_vnc_master = git_from_my_repo('xx', {initialize_from: 'github:a/b'})
      hack_on_godot_3_vnc = godot_vnc_master.worktree_branch('fix_godot_3_vnc')
      hack_on_godot_4_vnc = godot_vnc_master.worktree_branch('fix_godot_4_vnc')

      if (with_solver){

        packages = [
          autoconf(openssl, ...),
          cmake(libjpg, ...),
          cmake(libpng, ...),
          nixpkgs("scons")
        ]

        env_hack_on_godot_3 = solve(...)

        env_hack_on_godot_4 = solve(...)

        actions = {
          "info": info about paths etc ?
          build_all = ....
        }

      } else {

        packages = [
          autoconf(openssl, ...),
          cmake(libjpg, ...),
          cmake(libpng, ...),
          nixpkgs("scons")
        ]

        env_hack_on_godot_3 = solve(...)

        env_hack_on_godot_4 = solve(...)

        actions = {
          "info": info about paths etc ?
          // depending on what platform its run should be cross compiler ?
          // so need to offer / choose from cross compilers ?
          build_and_start_windows = ....
          build_and_start_linux = ....
          build_sync_pico4 = ....

          export_to_nixpkgs
          export_to_xmake
          export_to_conda
          export_to_brew
        }

      }

