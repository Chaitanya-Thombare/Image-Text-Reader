# OCR-Text_Extraction
---
## Introduction
This repository is to detect and recognize text in the images. For now, this repository uses EasyOCR, which provides very good results, both in detection and recognition. I would be adding other models for detection and recognition as I go on learning about them.

## Installation and Usage of EasyOCR
```
!pip install easyocr
```
```
#These packages are to convert PDF to Images

!pip install pdf2image
!sudo apt-get install poppler-utils
```

Using EasyOCR is very easy. Its just these two commands to get detections, recognitions and confidences.
```
#Initialize Reader Object of easyocr 
reader = easyocr.Reader(['en'])

bbox, text, probablity = reader.readtext(blank_frame)
```

That it! You now have the output. All you have to do is to clean the output however you want and you are done. No image preprocessing and all that hassle required XD.

## Examples


## Conclusion
This is not the end of this repository. I would learn other things and put them here. I have used EAST Model and Pytesseract, and did not get satisfactory results. So I switched to this.
