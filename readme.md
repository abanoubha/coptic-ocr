# Coptic OCR

Coptic is the final stage of ancient egyptian language.

## resources

- [Train Tesseract OCR - AbanoubHA | GitHub](https://github.com/abanoubha/train-tesseract-ocr)
- [tessdata Coptic - Shreeshrii | GitHub](https://github.com/Shreeshrii/tessdata_coptic)
- [CopticOCR - KELLIA | GitHub](https://github.com/KELLIA/CopticOCR/tree/master)
- [Noto Sans Coptic | Google Fonts](https://fonts.google.com/noto/specimen/Noto+Sans+Coptic)
- [all models of languages officially supported/trained by Tesseract-OCR](https://tesseract-ocr.github.io/tessdoc/Data-Files.html)
- [Agpeya (.pdf) in Coptic, English and Arabic | Google Drive](https://drive.google.com/file/d/1ICJSAjJO0sTq0PkPOwp8TCbYuwU1eDx0/view)
- [Optical character recognition of typeset Coptic text with neural networks | DSH](https://academic.oup.com/dsh/article/34/Supplement_1/i135/5476096)
- [Optical Character Recognition for Coptic fonts (.pdf) | acm](https://dl.acm.org/doi/pdf/10.1145/3322905.3322931)

## how to add support for Coptic in tesseract OCR ?

asked [phind/chatgpt](https://www.phind.com/), and here is the answer.

To add support for Coptic in Tesseract OCR, you would need to train Tesseract with a dataset that includes Coptic script. However, as of the time of writing, Tesseract does not officially support the Coptic script.

To train Tesseract with a new language, you would need to follow these steps:

1. __Prepare your training data__: You need a dataset that includes Coptic text and corresponding images. The dataset should be large enough and representative of the text you want Tesseract to recognize. The text should be in UTF-8 format and the images should be clear and high-resolution.
2. __Train Tesseract with the new language__: Tesseract can be trained to recognize new languages using the `tesstrain` tool. The `tesstrain` tool is used to train Tesseract using synthetic images created using a UTF-8 training text and Unicode fonts to render the text. However, training from scanned images and transcription is supported via tesstrain makefile 7.
3. __Generate a new traineddata file__: After training, a new `.traineddata` file will be generated. This file contains the trained model and should be placed in the `tessdata` directory of your Tesseract installation.
4. __Use the new traineddata file__: You can now use the new traineddata file to recognize Coptic text. You would need to specify the Coptic language code (e.g., 'cop') when running Tesseract 4.

Here is an example of how to use the new traineddata file:

```sh
tesseract image.png output -l cop
```

Please note that the training process can be time-consuming and requires significant computational resources. Also, the quality of the OCR results depends on the quality of the training data and the training process.

If you are not able to train Tesseract with Coptic text, you might consider using a different OCR tool that supports Coptic, or requesting that the Tesseract community add support for Coptic.

## About this repo

This is an experiment to create an acceptable Coptic OCR model. The main repo for Coptic OCR is [here](https://github.com/abanoubha/coptic-ocr)
