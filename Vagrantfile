Vagrant.require_version ">= 1.6.0"
VAGRANTFILE_API_VERSION = "2"
ENV['VAGRANT_DEFAULT_PROVIDER'] = 'docker'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # mounted diesen (.) Ordner nach /vagrant im Container
  # sprich man müsste hier einen /www Ornder nach /var/bla/bla mounten, wo halt nginx web inhalte ausliefert
  config.vm.synced_folder "./app", "/usr/share/nginx/html/unterordner", disabled: false

  config.vm.provider "docker" do |docker|
    docker.vagrant_vagrantfile = "host/Vagrantfile"
    docker.build_dir = "./docker"
    docker.name = 'my-nginx'
    docker.ports = ['80:80']
  end
end
