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

detections, recognitions, confidences = reader.readtext(blank_frame)

#detections - list of bbox coordinates of detected texts. 
#Format - (topLeft, topRight, bottomLeft, bottomRight)

#recognitions - list of the text in that bbox

#confidences - list of the probablities/confidences of each bbox
```

That it! You now have the output. All you have to do is to clean the output however you want and you are done. No image preprocessing and all that hassle required XD.

## Example Output

<img src="https://github.com/Chaitanya-Thombare/Optical-Character-Detection-and-Recognition/blob/main/Images%20and%20Output/OCR9.jpg" width="400">

<img src="https://github.com/Chaitanya-Thombare/Optical-Character-Detection-and-Recognition/blob/main/Images%20and%20Output/PDF_image.jpg" width="400">

Raw Text - THE//CEe//MAGAZINE//TECH//ISSUE//INSPIRING THE BUSINESS WORLD//30//INSPIRE//PAGES ON//SIR JAMES DYSON://BUILDING A//THE #1 SECRET TO//WORKFORCE//HIS SUCCESS//FOR THE FUTURE//YUVAL NOAH HARARI://EDUCATION IN THE//AGE OF AI//DR MICHIO KAKU://HIS VISION FOR//FROM BEES//TOMORROW//TO BEZOS//PROTECTING//HUMANKIND//FROM THE RISE//OF THE ROBOTS//ELON//MUSK//THE EXTRAORDINARY//CORPORATE DISRUPTER//{//3//AND BREATHE//3//THE WORLD'S BEST SPAS

I have applied some algorithms to this for sequencing the recognitions to form sentences so that they actually mean something. Originally detections are just in sequence such that top left is first and bottom right is last, which is fine for one paragraph, but when texts are in coloums like in IEEE papers or Newspapers, that recognitions wont make any sense after a point. So those algorithms are applied.


Sequenced Text - "CEe//INSPIRING THE BUSINESS WORLD//INSPIRE//SIR JAMES DYSON://THE #1 SECRET TO//HIS SUCCESS//YUVAL NOAH HARARI://EDUCATION IN THE//AGE OF AI//DR MICHIO KAKU://HIS VISION FOR//TOMORROW//{//3//3//MAGAZINE//ELON//MUSK//THE EXTRAORDINARY//CORPORATE DISRUPTER//MAGAZINE//ELON//MUSK//THE EXTRAORDINARY//CORPORATE DISRUPTER"


Final Text - CEe INSPIRING THE BUSINESS WORLD INSPIRE SIR JAMES DYSON: THE #1 SECRET TO HIS SUCCESS YUVAL NOAH HARARI: EDUCATION IN THE AGE OF AI DR MICHIO KAKU: HIS VISION FOR TOMORROW { 3 3 MAGAZINE ELON MUSK THE EXTRAORDINARY CORPORATE DISRUPTER MAGAZINE ELON MUSK THE EXTRAORDINARY CORPORATE DISRUPTER


## End
This is not the end of this repository. I would learn other things and put them here. I have used EAST Model and Pytesseract, and did not get satisfactory results. So I switched to this. 
