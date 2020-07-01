# vt-cloud

Step 1 : SSH vao master :
ip master = 54.87.252.223
ssh -i master.pem ubuntu@54.87.252.223

Step 2: chạy playbook cài đặt trên 2 node  
 ansible-playbook node1.yml -i inventory -vv
 ansible-playbook node2.yml -i inventory -vv

Step 3:SSH vào các worker xem kết quả container được tạo hay chưa ? 
ssh -i ansible.pem ubuntu@52.91.136.80
ssh -i ansible.pem ubuntu@3.90.83.58

Step 4 : User docker swarm để tạo network ảo :
ip master =  54.87.252.223
sudo docker swarm init --advertise-addr 54.87.252.223
Sau đó dùng token generate được chạy trên 2 node worker để join

Check network trên master : docker info 


