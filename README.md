1. Compare the application logs before and after you exposed it as a Service.
Try to open the app several times while the proxy into the Service is running.
What do you see in the logs? Does the number of logs increase each time you open the app?

    #### Jawab:
    Sebelum aplikasi diekspos sebagai Service, log yang dihasilkan terutama berasal dari pod aplikasi itu sendiri, mencakup pesan startup, penanganan permintaan HTTP, dan pesan kesalahan. 
    ![Mencoba GET](mencoba-get.png)
    Ya, jumlah log akan bertambah setiap kali aplikasi dibuka karena setiap akses melalui Service menghasilkan permintaan baru yang dicatat oleh aplikasi.

2. Notice that there are two versions of `kubectl get` invocation during this tutorial section.
The first does not have any option, while the latter has `-n` option with value set to `kube-system`.
What is the purpose of the `-n` option and why did the output not list the pods/services that you explicitly created?

    #### Jawab:
    Ketika Kita menggunakan perintah kubectl get tanpa opsi -n, perintah ini akan default ke namespace default, menampilkan sumber daya di namespace tersebut. Namun, dengan menggunakan opsi -n, Kita dapat menentukan namespace yang berbeda untuk menanyakan sumber daya, misalnya kubectl get pods -n kube-system akan menampilkan pod di namespace kube-system, yang merupakan namespace khusus untuk komponen sistem Kubernetes. 