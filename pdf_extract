"""
A simple Python program that extracts information from a PDF.

"""

import PyPDF2
import requests

url = "http://www.pdf995.com/samples/pdf.pdf"

customHeaders = {'user-agent' : 'Mozilla/5.0 (Windows NT 6.1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/41.0.2228.0 Safari/537.36;',
            'from': 'Pete Cooper pcooper19@gmail.com'}


response = requests.get(url, headers = customHeaders)

pdf_file = response.text
global pdf_file

def extract_information(pdf_file):
    with open(pdf_file, 'rb') as f:
        pdf = PdfFileReader(f)
        information = pdf.getDocumentInfo()
        number_of_pages = pdf.getNumPages()

    txt = f"""
    Information about {pdf_file}: 

    Author: {information.author}
    Creator: {information.creator}
    Producer: {information.producer}
    Subject: {information.subject}
    Title: {information.title}
    Number of pages: {number_of_pages}
    """

    print(txt)
    return information

extract_information(pdf_file)
