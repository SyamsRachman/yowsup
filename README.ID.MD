# Yowsup2 Python For Whatsapp

## Instalasi

1. Clone Repo 
```sh
  $ git clone https://github.com/tgalal/yowsup.git && cd yowsup
```

2. Edit yowsup/yowsup/env/env.py
```python
DEFAULT = "s40" #before
DEFAULT = "Android" #after
```
3. Edit yowsup/yowsup/env/env_android.py
```python
_MD5_CLASSES = "____"
_VERSION = "____"
```
untuk nilai md5 & version ambil disini **https://coderus.openrepos.net/whitesoft/whatsapp_scratch**

```json
{
  "a": "bDsdWi0yvVhqavctrvA4Sw==",
  "b": "PdA2DJyKoUrwLw1Bg6EIhzh502dF9noR9uFCllGk",
  "c": "1478194306452L",
  "d": "2.17.329",
  "e": "2.16.12",
  "f": "2.11.634",
  "g": "PdA2DJyKoUrwLw1Bg6EIhzh502dF9noR9uFCllGk",
  "h": "1478194472015L",
  "i": "PdA2DJyKoUrwLw1Bg6EIhzh502dF9noR9uFCllGk",
  "j": "1478194472015L"
}
```
4. Build dan install
```sh
$ python setup.py build && python setup.py install
```

**Note:** untuk yang menggunakan Virtualenv Python 
`$ pip install yowsup2` kemudian next di step ke-2 diatas (tapi cari dulu dimana letak .env)

### Registrasi Nomor Telepon
- bikin file config `vim yw.config` nama terserah 
- **Note :**  cc,mnc,mcc tergantung negara & provider bisa check disini `http://mcc-mnc.com/`
```
phone=nomorlo
cc=62
mnc=tergantungprovider
mcc=tergantungprovider
id=yourphoneImei<tidak disarankan>
password=<kosong dulu>
```
- `$ yowsup-cli registration --requestcode sms -c <pathconfig> -E android`
- `$ yowsup-cli registration --register 6digitcode <pathconfig> -E android`
- kembalian dalam bentuk json , ambil bagi pw dalam response json tersebut `{ pw: base6pass}`
- close Whatsapp di android , jgn pernah dibuka biar gk keciduk . kalau perlu uninstall aja :D
- nilai dari **{pw: base6}** simpan kedalam config yg dibuat bagian password
- `$ yowsup-cli demos -c <pathconfig> -s <nomor_doi> "Hello sayang" -E s40 #contoh ngirim pesan`
- `$ yowsup-cli demos -c <pathconfig> -y -E s40 #yowsup command line client , interactive ngecommand`

# SEKIAN

