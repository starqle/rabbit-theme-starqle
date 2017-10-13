require "rabbit/task/theme"

spec = nil
Rabbit::Task::Theme.new do |task|
  task.required_rabbit_version = ">= 2.2.0"
  spec = task.spec
end

desc "Tag the current version"
task :tag do
  sh("git", "tag", "-a", "-m", "Publish #{spec.version}", spec.version.to_s)
  sh("git", "push", "--tags")
end
