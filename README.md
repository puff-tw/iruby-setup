# IRuby 安裝指引 ( MAC 版本 )
假設已安裝完Ruby, 且是用 rbenv 作為版本管理工具

先裝 python 版本管理工具
--

```sh
brew update
brew doctor
brew install pyenv zeromq
```

修改Shell的環境變數
--
這邊是用 oh my zsh 的Shell 當範例, /Users/xxx/ 當中的xxx為你的帳號

```sh
echo 'export PYENV_ROOT=/usr/local/opt/pyenv' >> ~/.zshrc
echo 'export PATH="/Users/xxx/.rbenv/shims:/Users/xxx/.rbenv/shims:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'if command -v pyenv > /dev/null; then eval "$(pyenv init -)"; fi' >> ~/.zshrc
source ~/.zshrc
```

安裝 python
--

```sh
pyenv install 2.7.8
pyenv global 2.7.8
```

安裝 ipython
--

```sh
pip install --upgrade pip
pip install ipython pyzmq jinja2 tornado
pyenv rehash
```

安裝 iruby
--

```sh
gem install iruby pry
rbenv rehash
mkdir ~/.config
```

測試 iruby
--

```sh
iruby
#會進入 iruby 的console 大致上像一般 ruby console
```

```sh
cd test_folder
iruby notebook
#會開啟 iruby notebook 網頁, shift + enter 可執行你在上面輸入的命令
#感受一下 web 介面的編輯器，試著改別名及存檔，會存於你的當前目錄
```

DEMO
--
[簡單測試](http://nbviewer.ipython.org/github/puff-tw/iruby-setup/blob/master/example.ipynb)

你也可以在[nbviewer](http://nbviewer.ipython.org/) 分享你的筆記本
.ipynb 檔

心得
--
寫程式用的筆記本 ( 在你想要的目錄下執行 iruby notebook )
可在任意行數去做重覆執行 ( 執行命令 Shift + Enter )
