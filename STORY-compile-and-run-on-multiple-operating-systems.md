# CASE: develop a opengl 3d app and test it

Define a repository on a server.
Check it out
compile on this machine (if you run script on multiple you can build update on all

    # let's define a ssh account to place git reposiotries
    repo_server = git_repos_on_ssh_host("user@host/repos")

    # let's define / create a git repository to work with
    repo = git_repo(repo_server, "3d_app")

    # let's connect to a server to communicate changes to all devices
    master = master_server("IP", "username", "password", "3d_app_project")

    fs = checkout_location(repo, master)o

    action {
        build:  ("all" | "this") => ..
        launch: ("all" | "this") => ..
    }
