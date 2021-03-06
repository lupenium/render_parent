# encoding: utf-8

require 'rubygems'
require 'bundler'
begin
  Bundler.setup(:default, :development)
rescue Bundler::BundlerError => e
  $stderr.puts e.message
  $stderr.puts "Run `bundle install` to install missing gems"
  exit e.status_code
end
require 'rake'

require 'jeweler'
Jeweler::Tasks.new do |gem|
  # gem is a Gem::Specification... see http://docs.rubygems.org/read/chapter/20 for more options
  gem.name = "render_parent"
  gem.homepage = "http://github.com/MayamaTakesh/render_parent"
  gem.license = "MIT"
  gem.summary = %Q{Adds Rails "render :parent" helper, which renders template with the same name as current but higher on the view path}
  gem.description = %Q{This version fixes render_collection}
  gem.email = "anton.argirov@gmail.com"
  gem.authors = ["Anton Argirov", "MayamaTakeshi"]
  gem.files = Dir.glob('lib/**/*.rb') + %w(.document Gemfile LICENSE.txt README.rdoc Rakefile VERSION)
  # dependencies defined in Gemfile
end
Jeweler::RubygemsDotOrgTasks.new

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
end

task :default => :test

require 'rdoc/task'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "render_parent #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
