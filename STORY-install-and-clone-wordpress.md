This is the most simple recipe to start a well known Wordpress page:
Give it a name.
Starting to dream about distributed database and filesystem.
Of course if should run you need a local mysql/mariadb and your local filesystem.
So this illustrates the next level I'd call homeless following server >
serverless > homeless meaning no home reference by id/login/password and have
it copied cloned shared whatever. Could be distributed, could be managed by
central server.
Anyway once the Wordpress is setup and you want to work on a copy
The second block illustrates how it could look like


    How does it look like ?

      project = "wordpress site for company X"
      fs = new_distributed_fs(project)
      php = php_local_setup(fs)
      db = new_distributed_database(db
      wordpress = install_wordpress(fs, ghp, db)

      actions = {
        open_in_browser,
        open_shell,
        open_dev_editor
      }

    How does it look like if you want to create a story 'change website'?

      origin = "wordpress site for company X"
      story  = "add-feature"
      fs     = fork_fs(origin, story)
      db     = fork_db(origin, story)
      php    = php_local_setup(fs)
      wordpress = install_wordpress(fs, ghp, db)

      actions = {
        .. same as above plus
        update_from_upstream
        merge_back # well complicated if databse is touched
      }

    => Yeah Wordpress require MySQL which is not distributed. Imagining using
    online version of MySQL or a copy of mysql with a 'dump to my pc update'
    command is no brainer.
