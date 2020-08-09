
1. Thêm bộ gõ vào Manjaro

Gõ tiếng việt Arch Linux
https://tinhte.vn/thread/huong-dan-anh-em-linux-go-tieng-viet.3104698/

Arch Linux có 3 câu lệnh, xong thì restart máy

git clone https://aur.archlinux.org/ibus-bamboo.git 
cd ibus-bamboo 
makepkg -si

Sau đó mở Ibus Preferences-> Input Method   -> Thêm vào bàn phím 

2. Super user root
sudo passwd root
New password: 
Retype new password:
su root

//chay file
sudo ./xampp-linux-x64-7.4.7-0-installer.run

3. Cài xampp
https://www.wikihow.com/Install-XAMPP-on-Linux

Thư mục htdocs : opt/lamp/htdocs . Đặt thư mục cần thêm mới ở đây.
Cấp quyền administor cho thư mục trong Manjaro (Arch)
cd /opt/lampp
sudo chmod 777 -R htdocs

5./ Chạy start xampp trong linux
sudo /opt/lampp/lampp start

5.//Cài Sublime Text
https://snapcraft.io/install/sublime-text/manjaro

6./ Xoá thư mục cứng đầu
sudo chmod 777 /home/icarus/trunk

7./ Lavarel trong Manjaro
Khởi tạo Lavarel 
Link : https://forum.manjaro.org/t/definitive-guide-to-install-laravel/36846
Sửa lỗi permissions, chạy câu lệnh sudo chmod 777 -R /storage
