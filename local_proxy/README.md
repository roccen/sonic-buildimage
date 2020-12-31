Use apt-cache-ng to save time and network bandwidth

docker build -t eg_apt_cacher_ng .
docker run -d -p 3142:3142 --name test_apt_cacher_ng eg_apt_cacher_ng

export http_proxy=http://`ifconfig docker0|grep 'inet\ '|cut -d ' ' -f 10`:3142

Also a remote proxy, such as ss could be configured with iptables as transparent proxy as gateway, to accelerate outside download
