# Robo
import os
import PyPDF2

folder = r'C:\Users\Catatau\Desktop\teste'

for filename in os.listdir(folder):
    if filename.endswith('.pdf'):
        with open(os.path.join(folder, filename), 'rb') as pdf_file:
            pdf_reader = PyPDF2.PdfReader(pdf_file)
            pdf_title = pdf_reader.metadata.get('/Title')
        os.rename(os.path.join(filename), pdf_title)
        os.rename(os.path.join(filename), pdf_title)
else:
    print(f"Não foi possível obter o título do arquivo {filename}")
