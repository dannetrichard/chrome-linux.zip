# chrome-linux.zip【524617】

#puppeteer对应chromium版本524617（现在是2017.12.27）

查看版本在这里 
https://github.com/GoogleChrome/puppeteer/blob/master/package.json
下载地址在这里 
https://storage.googleapis.com/chromium-browser-snapshots/Linux_x64/524617/chrome-linux.zip


#【首先nodejs、npm】
~安装nodejs、npm（node官网的centos版教程 https://nodejs.org/en/download/package-manager/）
curl --silent --location https://rpm.nodesource.com/setup_8.x | sudo bash -
sudo yum -y install nodejs

#【安装无chromium版puppteer】
npm init
npm config set PUPPETEER_SKIP_CHROMIUM_DOWNLOAD true
npm i puppeteer

#【安装chromium】
1、建立目录node_modules/puppeteer/.local-chromium/linux-524617
2、下载chrome-linux.zip到上面目录
3、在目录里解压unzip chrome-linux.zip
4、安装chromium依赖【centos版本！！！】
yum install -y pango.x86_64 libXcomposite.x86_64 libXcursor.x86_64 libXdamage.x86_64 libXext.x86_64 libXi.x86_64 libXtst.x86_64 cups-libs.x86_64 libXScrnSaver.x86_64 libXrandr.x86_64 GConf2.x86_64 alsa-lib.x86_64 atk.x86_64 gtk3.x86_64 ipa-gothic-fonts xorg-x11-fonts-100dpi xorg-x11-fonts-75dpi xorg-x11-utils xorg-x11-fonts-cyrillic xorg-x11-fonts-Type1 xorg-x11-fonts-misc

#【完成】

#【centos】写代码时记住添加参数 const browser = await puppeteer.launch({ args: ['--no-sandbox', '--disable-setuid-sandbox'] });

