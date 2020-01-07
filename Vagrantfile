
required_plugins = %w(vagrant-vbguest vagrant-timezone)

plugins_to_install = required_plugins.select { |plugin| not Vagrant.has_plugin? plugin }
if not plugins_to_install.empty?
  puts "Installing plugins: #{plugins_to_install.join(' ')}"
  if system "vagrant plugin install #{plugins_to_install.join(' ')}"
    exec "vagrant #{ARGV.join(' ')}"
  else
    abort "Installation of one or more plugins has failed! Aborting..."
  end
end

Vagrant.configure("2") do |config|

  config.vm.box = "debian/buster64"

  if defined?(VagrantVbguest::Installers::Debian)
    require_relative 'box/requisites'
    config.vbguest.installer = Utility::DebianCustom
  end

  if ENV['VAGRANT_FIRST_RUN'] == 'TRUE'
    config.vbguest.auto_update = false
    config.vm.synced_folder ".", "/vagrant", disabled: true
  else
    config.vm.synced_folder ".", "/vagrant", type: "virtualbox"
  end

  config.vm.network "forwarded_port", guest: 4000, host: 4000

  if Vagrant.has_plugin?("vagrant-timezone")
    config.timezone.value = :host
  end
  
  config.vm.provision :shell, path: "box/provisioner.sh"

  config.vm.provision :shell, path: "box/run.sh", run: 'always'
end
