# Example Usage

```
export GITHUB_TOKEN=<token>
```

Install and clone modules

```
bundle config set path '.bundle/gems/'
bundle install
bundle exec rake git:clone_managed_modules
```

Copy managed files

```
find modules_pdksync -mindepth 1 -maxdepth 1 -type d -exec cp -r -v ./managed_files/.* {}/ \;
```

Run commands

```
bundle exec rake 'pdksync:run_a_command[pdk update --template-ref 3.3.0]'
bundle exec rake 'pdksync:run_a_command[pdk update]'
bundle exec rake 'pdksync:run_a_command[pdk test unit]'
```

Commit

```
bundle exec rake 'git:create_commit[pdk-update,"Update PDK to 3.3.0"]'
bundle exec rake 'git:push'
bundle exec rake 'git:create_pr["PDK update"]'
```
