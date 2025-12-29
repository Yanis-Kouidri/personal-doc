# Photo

## Automatialy crop pictures from a scan

### Install

```bash
sudo apt install imagemagick bc
```
Download [multicrop](http://www.fmwconcepts.com/imagemagick/downloadcounter.php?scriptname=multicrop&dirname=multicrop)

### Run

```bash
 ./multicrop -u 1 scan_pics.jpg extracted_pic.jpg
```

 It will generate `extracted_pic-000.jpg` `extracted_pic-001.jpg` ... depending of number of picture found in `scan_pics.jpg`.

 To run it on all scan in the current folder:


```bash
for f in *.jpg; do
    ./multicrop -u 1 "$f" "output/extracted_$f"
done
```

