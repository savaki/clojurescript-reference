namespace :sass do
  desc 'compile the sass files'
  task :compile do
    run_command 'sass static/css/website.scss:static/css/website.css'
  end

  desc 'continuously compile the sass files'
  task :watch do
    run_command 'sass --watch static/css/website.scss:static/css/website.css'
  end
end

def run_command(command)
  puts command
  system(command) || raise("unable to execute command -> #{command}")
end