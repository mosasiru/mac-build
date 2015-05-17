■設定
　Dock: dockの位置を左に, 自動的に隠す
　セキュリティ：１時間後にパスワード要求
　キーボード：F1,F2などを標準のファンクションキーとして利用
　トラックパッド：タップでクリック
    日付：日時を表示
    iCloud signin

■chrome install
　docに追加
chrome login

■テクストエディット
　docに追加

■evernote DL
  => これみる

■iterm2をDL
設定をもってきてPreference => General で import: com.googlecode.iterm2.plist

■karabiner DL
以下のコマンドで設定をexportし、bashで実行

18:47 yusuke.enomoto@mosa$ /Applications/Karabiner.app/Contents/Library/bin/karabiner export [~]
#!/bin/sh

cli=/Applications/Karabiner.app/Contents/Library/bin/karabiner

$cli set repeat.wait 20
/bin/echo -n .
$cli set repeat.initial_wait 150
/bin/echo -n .
$cli set remap.jis_commandR2commandR_toggle_kana_eisuu 1
/bin/echo -n .
$cli set remap.jis_kana2return 1
/bin/echo -n .
$cli set remap.jis_eisuu2escape 1
/bin/echo -n .
å/bin/echo

■Xcode
app storeからいれる
sudo xcodebuild -license

■brew
 ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
○cask
  brew install caskroom/cask/brew-cask

■google IME
  brew cask install google-japanese-ime
  http://qiita.com/hkusu/items/159e0ff07441ae2ec1fa にしたがって設定
  saikidou

■Andisble
brew install python
brew install ansible

mkdir .macbook-provisioning
cd .macbook-provisioning/

<!--echo 'localhost' > hosts-->
<!--vim localhost.yml-->
symlink this repos files!!


HOMEBREW_CASK_OPTS="--appdir=/Applications"  ansible-playbook -i hosts -vv localhost.yml

■mackup
mackup restore

■その他
・line apps
・push bullet


■perl

plenv install 5.18.2  --notest -j `/usr/bin/getconf _NPROCESSORS_ONLN`
plenv install-cpanm
cpanm --reinstall App::cpanminus
cpanm App::cpanoutdated
plenv rehash
cpan-outdated | cpanm -nq

■mysql
git clone git://github.com/kamipo/mysql-build.git ~/mysql-build
mkdir -p ~/opt/mysql
mysql-build 5.6.16 ~/opt/mysql/5.6.16 q4m-0.9.14

■sandbox

cpanm MySQL::Sandbox
make_sandbox 5.6.16
cd ~/sandboxes/msb_5_6_16
./use < ~/opt/mysql/5.6.16/support-files/install-q4m.sql