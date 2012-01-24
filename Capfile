server "jail0145.vps.exonetric.net", :web

after :deploy, 'apache:restart'

desc 'Copy the config files to the server using rsync'
task :deploy do
  run "rm /home/chrisroos/www-config/*"
  system "rsync -av *.config chrisroos@jail0145.vps.exonetric.net:/home/chrisroos/www-config/"
end

namespace :apache do
  desc 'Restart apache'
  task :restart do
    sudo 'apachectl restart'
  end
end