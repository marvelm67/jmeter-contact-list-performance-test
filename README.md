# Contact List App — JMeter Performance Testing

Performance testing project untuk Contact List API menggunakan Apache JMeter 5.6.3.

## API Target

**Base URL:** `https://thinking-tester-contact-list.herokuapp.com`  
**Dokumentasi API:** [Postman Documentation](https://documenter.getpostman.com/view/4012288/TzK2bEa8)

### Endpoint yang Diuji

| Method | Endpoint | Deskripsi |
|--------|----------|-----------|
| POST | `/users` | Register user (mendapatkan Bearer Token) |
| POST | `/contacts` | Membuat contact baru |
| GET | `/contacts` | Mendapatkan semua contacts |
| GET | `/contacts/{id}` | Mendapatkan contact by ID |
| PUT | `/contacts/{id}` | Update contact (full update) |
| PATCH | `/contacts/{id}` | Partial update contact |
| DELETE | `/contacts/{id}` | Hapus contact |

## Skenario Test

### 1. Load Testing
- **Virtual Users:** 50
- **Ramp-up Period:** 10 detik
- **Loop Count:** 5
- **Tujuan:** Mengukur performa API di bawah beban normal

### 2. Stress Testing
- **Virtual Users:** 200
- **Ramp-up Period:** 20 detik
- **Loop Count:** 3
- **Tujuan:** Mengukur batas maksimum API di bawah beban tinggi

## Struktur File

```
├── ContactList_Performance_Test.jmx   # JMeter Test Plan
├── testdata.csv                        # Test data (20 baris)
├── results.jtl                         # Raw results
├── html-report/                        # HTML report (buka index.html di browser)
│   └── index.html
├── Laporan_Performance_Testing.pdf     # Laporan analisis PDF
└── README.md
```

## Cara Menjalankan

### Via CLI
```bash
cd /path/to/project
jmeter -t ContactList_Performance_Test.jmx -n -l results.jtl -e -o html-report
```

### Via GUI
```bash
jmeter -t ContactList_Performance_Test.jmx
```

## Hasil Test

| Metrik | Nilai |
|--------|-------|
| Total Requests | 5,101 |
| Error Rate | 0.00% |
| Mean Response Time | 2,374 ms |
| Throughput | 45.6 req/sec |

## Tools

- **Apache JMeter 5.6.3**
- **Java 22.0.2**
- **GitHub** (repository ini)

## Video Recording

Video recording tersedia terpisah di Google Drive (link pada laporan PDF).
