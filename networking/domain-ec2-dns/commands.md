ssh -i "my-key.pem" ubuntu@ec2-ip-address
sudo apt update
sudo apt install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx
sudo systemctl status nginx
