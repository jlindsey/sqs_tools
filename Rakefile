desc "Install the tools"
task :install do
  require 'fileutils'

  print "Install to where? [/usr/local/bin] "
  path = $stdin.gets.strip
  path = "/usr/local/bin" if path.empty?

  Dir.glob('bin/*').each do |file|
    source = File.expand_path(file, File.dirname(__FILE__))
    dest = File.join(path, File.basename(file))

    puts "Copy #{file} -> #{dest}"
    FileUtils.cp source, dest
    FileUtils.chmod 0755, dest
  end
end

task :default => :install

