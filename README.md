Question : The Nautilus Application development team has finished development of one of the applications and it is ready for deployment. It is a guestbook application that will be used to manage entries for guests/visitors. As per discussion with the DevOps team, they have finalized the infrastructure that will be deployed on Kubernetes cluster. Below you can find more details about it.

BACK-END TIER

1. Create a deployment named redis-master for Redis master.

a.) Replicas count should be 1.

b.) Container name should be master-redis-devops and it should use image redis.

c.) Request resources as CPU should be 100m and Memory should be 100Mi.
d.) Container port should be redis default port i.e 6379.
2. Create a service named redis-master for Redis master. Port and targetPort should be Redis default port i.e 6379.

3. Create another deployment named redis-slave for Redis slave.

a.) Replicas count should be 2.

b.) Container name should be slave-redis-devops and it should use gcr.io/google_samples/gb-redisslave:v3 image.

c.) Requests resources as CPU should be 100m and Memory should be 100Mi.

d.) Define an environment variable named GET_HOSTS_FROM and its value should be dns.

e.) Container port should be Redis default port i.e 6379.

4. Create another service named redis-slave. It should use Redis default port i.e 6379.

FRONT END TIER

1. Create a deployment named frontend.

a.) Replicas count should be 3.

b.) Container name should be php-redis-devops and it should use gcr.io/google-samples/gb-frontend:v4 image.

c.) Request resources as CPU should be 100m and Memory should be 100Mi.
d.) Define an environment variable named as GET_HOSTS_FROM and its value should be dns.

e.) Container port should be 80.

2. Create a service named frontend. Its type should be NodePort, port should be 80 and its nodePort should be 30009.

Finally, you can check the guestbook app by clicking on + button in the top left corner and Select port to view on Host 1 then enter your nodePort.

You can use any labels as per your choice.
