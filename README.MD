# KDMapper

Intel `iqvw64e.sys` sürücüsündeki açığı kullanarak imzasız kernel sürücülerini belleğe manuel olarak map'leyen araç.

## Uyumluluk

**Windows 10 1607** — **Windows 11 24H2 26100.3915** arası test edilmiş ✓

## Kullanım

```
kdmapper.exe driver.sys [parametreler]
```

### Parametreler

| Parametre | Açıklama |
|---|---|
| `--copy-header` | Sürücü header kopyalamayı etkinleştir |
| `--free` | Ayrılan belleği otomatik serbest bırak |
| `--indPages` | Bağımsız sayfalara map'le |
| `--PassAllocationPtr` | Tahsis pointer'ını ilk parametre olarak geçir |
| `--offsetsPath "Yol"` | Özel offset dosya yolu belirt (varsayılan: `.\offsets.ini`) |
| `--dontUpdateOffsets` | Offset dosyasını güncellemeden çalıştır |

## Notlar

- `DISABLE_OUTPUT` tanımı ekleyerek tüm konsol çıktılarını kapatabilirsiniz
- HelloWorld örneğindeki gibi özel entry point kullanılması önerilir
- PDB offset tabanlı derleme kullanılıyorsa offset dosyasının güncel olduğundan emin olun

## Yapı

```
kdmapper/        — ana proje
HelloWorld/      — örnek sürücü
HelloWorld.sys   — derlenmiş örnek
DbgHelp/         — debug yardımcı
SymbolsFromPDB/  — PDB offset çıkarma
```
