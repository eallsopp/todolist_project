require 'rake/testtask'
require 'find'
require 'bundler/gem_tasks'

desc 'Say hello'
task :hello do 
    puts 'Hello there.  This is the hello task.'
end

task :test do
    sh 'ruby ./test/todolist_project_tests.rb'
end

desc 'run test'
task :default => :test

Rake::TestTask.new(:test) do |t|
    t.libs << 'test'
    t.libs << 'lib'
    t.test_files = FileList['test/**/*_tests.rb']
end

#list every file it the project except those that begin with .
#or those in a directory that start with .

desc 'Display inventory of all files'
task :inventory do 
  Find.find('.') do |name|
      next if name.include?('/.')
      puts name if File.file?(name)
  end
end

