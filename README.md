# AI Sales Brochure Generator

Generator brosur penjualan otomatis berbasis AI yang membuat brosur perusahaan dari website menggunakan Local LLM melalui Ollama.

---

## Deskripsi Proyek

AI Sales Brochure Generator adalah project Python yang melakukan scraping pada website perusahaan, memilih halaman-halaman penting secara otomatis menggunakan Large Language Model (LLM), lalu menghasilkan brosur marketing profesional dalam format Markdown.

Project ini menunjukkan implementasi nyata dari:

* Web Scraping Pipeline
* Prompt Engineering
* Structured JSON Output
* Multi-Step LLM Workflow
* Streaming Response Rendering

---

## Fitur Utama

* Mengambil seluruh link dari website perusahaan
* Memilih halaman relevan secara otomatis menggunakan AI (About, Careers, Company Info, dll)
* Mengambil isi konten dari halaman-halaman penting
* Menghasilkan brosur marketing otomatis
* Menampilkan output secara streaming real-time di Jupyter Notebook
* Struktur kode modular dan mudah dikembangkan

---

## Tech Stack

* Python 3.10+
* Jupyter Notebook
* Ollama
* Llama 3.2
* BeautifulSoup / Requests
* Python Dotenv

---

## Arsitektur Project

```text id="u4eiyd"
Input URL Website Perusahaan
            ↓
Scrape Seluruh Link Website
            ↓
LLM Memilih Link Relevan
            ↓
Scrape Isi Halaman Penting
            ↓
LLM Generate Brosur
            ↓
Output Markdown
```

---

## Instalasi

### 1. Clone Repository

```bash id="p9l7pw"
git clone https://github.com/username/ai-sales-brochure-generator.git
cd ai-sales-brochure-generator
```

---

### 2. Buat Virtual Environment

```bash id="rwz34n"
python -m venv venv
source venv/bin/activate
```

Untuk Windows:

```bash id="h9e5zx"
venv\Scripts\activate
```

---

### 3. Install Dependencies

```bash id="dhr2b0"
pip install -r requirements.txt
```

---

## Setup Ollama

Install Ollama melalui website resmi:

https://ollama.com/

Lalu download model yang digunakan:

```bash id="wpgmn9"
ollama pull llama3.2
```

Pastikan server Ollama berjalan sebelum notebook dijalankan.

---

## Konfigurasi Environment Variable

Buat file `.env`:

```env id="vqv6q2"
OLLAMA_API_KEY=your_optional_key_here
```

> Catatan: Untuk penggunaan Ollama lokal, API Key biasanya tidak diperlukan.
> Variabel ini disediakan agar project mudah diupgrade ke cloud API di masa depan.

---

## Cara Menjalankan Project

Jalankan Jupyter Notebook:

```bash id="2bgnui"
jupyter notebook
```

Buka file:

```text id="sq34ol"
sales_brochure_generator.ipynb
```

Lalu jalankan seluruh cell.

---

## Contoh Penggunaan

```python id="1n4w0g"
create_brochure_company(
    "Fordive",
    "https://fordive.id/"
)
```

---

## Contoh Output

```markdown id="2p5dxn"
# Fordive

Fordive adalah perusahaan digital yang berfokus pada ...
...
```

---

## Pengembangan Selanjutnya

* Menggunakan smart chunking agar context lebih efisien
* Menambahkan retry mechanism untuk JSON invalid
* Support OpenAI / Gemini / Claude API
* Export brosur ke PDF / DOCX
* Menambahkan antarmuka web dengan Streamlit / Gradio

---

## Support Cloud API (Opsional)

Project ini dapat dengan mudah diubah untuk menggunakan API cloud seperti:

* OpenAI API
* Google Gemini API
* Anthropic Claude API
* DeepSeek API

### Contoh Integrasi OpenAI API

Install package:

```bash id="cv9vko"
pip install openai
```

Ganti:

```python id="g4t6mk"
response = ollama.chat(...)
```

Menjadi:

```python id="u4t1gk"
from openai import OpenAI

client = OpenAI(api_key="YOUR_API_KEY")

response = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=[
        {"role": "system", "content": "..."},
        {"role": "user", "content": "..."}
    ]
)
```

---



## Author
**ISADAD JHN**
GITHUB: https://github.com/IsadadJhn

