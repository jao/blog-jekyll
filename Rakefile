require 'lib/rack/jekyll/version'

task :default => :test

desc "Run all tests"
task :test do
  sh "ruby test/*.rb"
  sh "bacon -q -a"
  sh "cucumber -f progress features"
end
desc "Build gem"
task :build do
  sh "gem build rack-jekyll.gemspec"
end

desc "Install gem"
task :install do
  sh "sudo gem install rack-jekyll-#{Rack::Jekyll.version}.gem"
end

desc "Push to Gemcutter"
task :push do
  sh "gem push rack-jekyll-#{Rack::Jekyll.version}.gem"
end

desc "Clean up gem"
task :clean do
  sh "rm *.gem"
end

desc "Run demo"
task :demo do
  puts " ==> Starting demo: http://localhost:3000/"
  Dir.chdir("example") do
    sh "rackup -p 3000"
  end
end
