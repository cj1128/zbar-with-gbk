# ZBar with GBK and UTF8 Support

Modify `zbar-0.10` to add GBK support, and remove SJIS.

## Compile Library

- configure

    ```bash
    $ ./configure --disable-video --without-xshm --without-xv --without-jpeg --without-imagemagick --without-gtk --without-python --without-qt --prefix=/tmp/local
    ```

- make and install

    ```bash
    $ make
    $ make install
    ```

Now we get our new zbar library at `/tmp/local`.

## Compile Test Code

```bash
$ gcc -I/tmp/local/include -L/tmp/local/lib -lzbar -lpng test_zbar.c -o test_zbar
$ ./test_zbar ./test.png
decoded QR-Code symbol "你好"
```
