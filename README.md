python-animeface
================

python-animeface はアニメ顔検出ライブラリ AnimeFace を Python から呼び出すためのライブラリです。

AnimeFace 本体については公式サイトを参照してください:

http://anime.udp.jp/imager-animeface.html


pip によるインストール
----------------------

バージョン 1.1 より、Linux/x86_64 環境ではビルド済みバイナリを使えるようになりました。
以下のコマンドでインストールできます。

    # pip install animeface


手動でのインストール
--------------------

### AnimeFace 本体のインストール

公式サイトから nvxs-1.0.2.tar.gz をダウンロードして展開後、インストールしてください。

    $ cd third_party/nvxs-1.0.2
    $ ./configure
    $ make
    $ sudo make install

### python-animeface のインストール

    $ python setup.py build
    $ sudo python setup.py install


使用法
------

    >>> import animeface
    >>> import PIL.Image
    >>> im = PIL.Image.open('/path/to/image.jpg')
    >>> faces = animeface.detect(im)
    >>> faces
    [<animeface.Face likelihood=0.998505 face=<pos=(158, 126; 127, 127)> skin=<color=(252, 239, 232)> hair=<color=(89, 120, 165)> left_eye=<pos=(235, 148; 36, 32), color=(204, 68, 101)> right_eye=<pos=(235, 148; 36, 32), color=(141, 46, 67)> mouth=<pos=(224, 213; 18, 10)> nose=<pos=(222, 199)> chin=<pos=(236, 240)> ]
    >>> fp = faces[0].face.pos
    >>> print fp.x, fp.y, fp.width, fp.height
    158 126 127 127

インターフェースの詳細は animeface/__init__.py を参照してください。


ライセンス
---------

python-animeface は Apache License にて提供されます。

http://www.apache.org/licenses/LICENSE-2.0.html

なお、元の AnimeFace ライブラリは NYSL で提供されています。
