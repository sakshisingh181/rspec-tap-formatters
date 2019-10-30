# frozen_string_literal: true

require 'bundler/setup'
require 'bundler/gem_tasks'
require 'rspec/core/rake_task'

desc 'Run Rubocop'
task :rubocop do
  sh 'bundle exec rubocop'
end

desc 'Run all examples'
RSpec::Core::RakeTask.new(:spec)

task default: %i[spec]