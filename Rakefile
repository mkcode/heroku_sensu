require "bundler/gem_tasks"
require "rspec/core/rake_task"

RSpec::Core::RakeTask.new(:spec)

task :default => :spec

WIZARDVAN_REPO_URL = 'git@github.com:opower/sensu-metrics-relay.git'
WIZARDVAN_VENDOR_PATH = 'vendor/wizardvan'

desc 'Update to ref (default: master) the wizardvan gem subtree in vendor.'
task :update_wizardvan, [:ref] do |task, args|
  ref = args[:ref] ? args[:ref] : 'master'
  command = "git subtree pull --prefix #{WIZARDVAN_VENDOR_PATH}"
  command += " #{WIZARDVAN_REPO_URL} #{ref} --squash"
  puts "\n=> `#{command}`\n\n"
  system(command)
end
