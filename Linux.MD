
1. Thêm bộ gõ vào Manjaro <br/>

Gõ tiếng việt Arch Linux <br/>
https://tinhte.vn/thread/huong-dan-anh-em-linux-go-tieng-viet.3104698/

Arch Linux có 3 câu lệnh, xong thì restart máy<br/>

git clone https://aur.archlinux.org/ibus-bamboo.git <br/>
cd ibus-bamboo  <br/>
makepkg -si <br/>

Sau đó mở Ibus Preferences-> Input Method   -> Thêm vào bàn phím <br/>

2. Super user root <br/>
sudo passwd root <br/>
New password: <br/>
Retype new password: <br/>
su root <br/>

Chay file <br/>
sudo ./xampp-linux-x64-7.4.7-0-installer.run

3. Cài xampp <br/>
https://www.wikihow.com/Install-XAMPP-on-Linux <br/>

Thư mục htdocs : opt/lamp/htdocs . Đặt thư mục cần thêm mới ở đây. <br/>
Cấp quyền administor cho thư mục trong Manjaro (Arch) <br/>
cd /opt/lampp <br/>
sudo chmod 777 -R htdocs <br/>

5./ Chạy start xampp trong linux <br/>
sudo /opt/lampp/lampp start <br/>

5.//Cài Sublime Text <br/>
https://snapcraft.io/install/sublime-text/manjaro <br/>

6./ Xoá thư mục cứng đầu <br/>
sudo chmod 777 /home/icarus/trunk <br/>

7./ Lavarel trong Manjaro <br/>
Khởi tạo Lavarel  <br/>
Link : https://forum.manjaro.org/t/definitive-guide-to-install-laravel/36846 <br/>
Sửa lỗi permissions, chạy câu lệnh sudo chmod 777 -R /storage <br/>
