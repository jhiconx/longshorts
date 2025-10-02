[README.md](https://github.com/user-attachments/files/22666531/README.md)
# BTC/ETH Longs vs Shorts — Aggregated Dashboard

A simple Streamlit app that shows **aggregated long vs short** sentiment for **BTC** and **ETH** across **Binance USDⓈ‑M** and **Bybit (linear USDT)**, **weighted by USD open interest**.

### What you'll see
- Aggregated **Long %**, **Short %**, and **Long/Short Ratio**
- Per‑exchange breakdown (shares and OI, with weights)
- Auto‑refresh (default 30 seconds)

---

## Quick Deploy (Streamlit Community Cloud)
The easiest way to get a *shareable link* that works on your phone and computer.

1. Create a free GitHub account (if you don't have one).
2. Make a new repository and upload **these two files**:
   - `streamlit_app.py`
   - `requirements.txt`
3. Go to https://streamlit.io/cloud, sign in with GitHub, click **New app**.
4. Choose your repo and set the main file to `streamlit_app.py`, then **Deploy**.
5. Copy the app URL and open it on your phone or computer. *(On iPhone/Android, use “Add to Home Screen” to pin it.)*

---

## Alternative: Run on Replit (also easy)
1. Go to https://replit.com → **Create Repl** → choose **Python**.
2. Upload `streamlit_app.py` and `requirements.txt` to the project.
3. Open the shell and run:
   ```bash
   pip install -r requirements.txt
   python -m streamlit run streamlit_app.py --server.port $PORT --server.address 0.0.0.0
   ```
4. Click the web view link Replit shows; open it on your phone/computer.

---

## Run on your computer (optional)
If you prefer local:
```bash
pip install -r requirements.txt
streamlit run streamlit_app.py
```
Streamlit will open a browser window at `http://localhost:8501`. If you want to view it from your phone on the same Wi‑Fi, run:
```bash
streamlit run streamlit_app.py --server.address 0.0.0.0
```
Then visit `http://<your-computer-ip>:8501` on your phone.

---

### How it works
- Fetches **account long/short** ratios and **open interest** from public endpoints.
- Converts Bybit OI (coin units) to USD using the latest price.
- Aggregates per exchange using **USD OI** as weights.

**No API keys needed.**
