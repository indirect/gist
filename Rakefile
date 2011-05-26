require 'bundler/gem_tasks'

desc "Build standalone script and manpages"
task :build => [ :standalone, :build_man ]

desc "Build standalone script"
task :standalone => :load_gist do
  require 'gist/standalone'
  Gist::Standalone.save('gist')
end

desc "Build gist manual"
task :build_man do
  sh "ronn -br5 --organization=GITHUB --manual='Gist Manual' man/*.ron"
end

desc "Show gist manual"
task :man => :build_man do
  exec "man man/gist.1"
end

task :load_gist do
  $LOAD_PATH.unshift 'lib'
  require 'gist'
end
