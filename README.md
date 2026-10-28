# India-Stocks-1831-1860-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 1831 to 1860)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-1831-1860-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (1831 to 1860)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 1831 | `ORIRAIL` | Oriental Rail Infrastructure Limited | `ORIRAIL.NS` |
| 1832 | `ORISSAMINE` | The Orissa Minerals Development Company Limited | `ORISSAMINE.NS` |
| 1833 | `ORKLAINDIA` | Orkla India Limited | `ORKLAINDIA.NS` |
| 1834 | `ORTINGLOBE` | ORTIN GLOBAL LIMITED | `ORTINGLOBE.NS` |
| 1835 | `OSIAHYPER` | Osia Hyper Retail Limited | `OSIAHYPER.NS` |
| 1836 | `OSWALAGRO` | Oswal Agro Mills Limited | `OSWALAGRO.NS` |
| 1837 | `OSWALGREEN` | Oswal Greentech Limited | `OSWALGREEN.NS` |
| 1838 | `OSWALPUMPS` | Oswal Pumps Limited | `OSWALPUMPS.NS` |
| 1839 | `OSWALSEEDS` | ShreeOswal Seeds And Chemicals Limited | `OSWALSEEDS.NS` |
| 1840 | `PACEDIGITK` | Pace Digitek Limited | `PACEDIGITK.NS` |
| 1841 | `PACIFICI` | Pacific Industries Limited | `PACIFICI.NS` |
| 1842 | `PAISALO` | Paisalo Digital Limited | `PAISALO.NS` |
| 1843 | `PAKKA` | PAKKA LIMITED | `PAKKA.NS` |
| 1844 | `PALASHSECU` | Palash Securities Limited | `PALASHSECU.NS` |
| 1845 | `PALREDTEC` | Palred Technologies Limited | `PALREDTEC.NS` |
| 1846 | `PANACEABIO` | Panacea Biotec Limited | `PANACEABIO.NS` |
| 1847 | `PANACHE` | Panache Digilife Limited | `PANACHE.NS` |
| 1848 | `PANAMAPET` | Panama Petrochem Limited | `PANAMAPET.NS` |
| 1849 | `PANCHMAHQ` | Panchmahal Steel Limited | `PANCHMAHQ.NS` |
| 1850 | `PANORAMA` | Panorama Studios International Limited | `PANORAMA.NS` |
| 1851 | `PANSARI` | Pansari Developers Limited | `PANSARI.NS` |
| 1852 | `PAR` | Par Drugs And Chemicals Limited | `PAR.NS` |
| 1853 | `PARACABLES` | Paramount Communications Limited | `PARACABLES.NS` |
| 1854 | `PARAGMILK` | Parag Milk Foods Limited | `PARAGMILK.NS` |
| 1855 | `PARAS` | Paras Defence and Space Technologies Limited | `PARAS.NS` |
| 1856 | `PARASHLTH` | Paras Healthcare Limited | `PARASHLTH.NS` |
| 1857 | `PARASPETRO` | Paras Petrofils Limited | `PARASPETRO.NS` |
| 1858 | `PARIN` | Parin Enterprises Limited | `PARIN.NS` |
| 1859 | `PARKHOSPS` | Park Medi World Limited | `PARKHOSPS.NS` |
| 1860 | `PARKHOTELS` | Apeejay Surrendra Park Hotels Limited | `PARKHOTELS.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream ORIRAIL 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-1831-1860-Historical-Data/main/ORIRAIL/1m/2026/10/ORIRAIL_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
