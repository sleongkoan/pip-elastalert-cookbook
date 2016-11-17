require 'cookstyle'
require 'rubocop/rake_task'

RuboCop::RakeTask.new do |task|
  task.options << '--display-cop-names'
end

task :foodcritic do
  if Gem::Version.new('1.9.2') <= Gem::Version.new(RUBY_VERSION.dup)
    sh 'foodcritic . --epic-fail correctness -X test/'
  else
    puts "WARN: foodcritic run is skipped as Ruby #{RUBY_VERSION} is < 1.9.2."
  end
end

task style: [:rubocop, :foodcritic]
