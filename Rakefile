require "bundler/gem_tasks"

require "rake/testtask"
Rake::TestTask.new(:test) do |t|
  t.libs << 'test'
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end

require "yardstick/rake/measurement"
Yardstick::Rake::Measurement.new do |measurement|
  measurement.output = "measurement/report.txt"
end

require "yardstick/rake/verify"
Yardstick::Rake::Verify.new do |verify|
  verify.require_exact_threshold = false
  verify.threshold = 55
end

task :default => :test
