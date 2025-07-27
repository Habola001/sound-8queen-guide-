# 🧠 Soundness Layer Guide – Step-by-Step

A simplified walkthrough to help you complete the Soundness Layer proof and submission using `soundness-cli`. This guide is beginner-friendly and based on a real submission flow.

---

## ✅ Step 1: Clone the Repo

```bash
git clone https://github.com/soundxyz/soundness
cd soundness
```

---

## 🔧 Step 2: Install Dependencies

```bash
npm install
```

---

## ⚙️ Step 3: Build the Project

```bash
npm run build
```

---

## 🎮 Step 4: Run a Soundness Game (Example: 8queens)

```bash
npx soundness game -g 8queens -a 0000000000000000 -b 11111111111111111111111111111111
```

> 💡 This generates a proof and commitment string.

---

## 🔑 Step 5: Add a Key

```bash
soundness-cli keys add --key-name sound
```

> ⌨️ When prompted for a password, press **Enter** (leave it blank).

---

## 📤 Step 6: Submit Proof to the Soundness Chain

If you don’t know what to fill in, **just copy your values** from the result you got after completing the Soundness game-7 command or Walrus.

Paste them into ChatGPT using the format below.

---

### 🧪 Example Command Format

```bash
soundness-cli send --proof-file="<your-proof-blob-id>" --game "<game-name>" --key-name sound --proving-system ligetron -d '{
  "program": "<path-to-your-wasm-file>",
  "shader-path": "<path-to-your-shader-folder>",
  "packing": 8192,
  "private-indices": [1, 2],
  "args": [
    {"str": "<input_1>"},
    {"str": "<input_2>"},
    {"str": "<your-public-key>"},
    {"str": "<your-commitment-string>"}
  ]
}'
```

---

## 🧠 Don't Know What to Fill In?

If you're confused by the command or not sure what to put:

✅ Copy your values from the result you got after completing the sound game-7 command or from Walrus.

🧠 Paste them into ChatGPT using the command format above.

⚡ Get a ready-to-run command back instantly!

📸 *(Insert example images of your Walrus result or CLI result here)*

---

## ✅ Demo Example (Safe Version)

```bash
soundness-cli send --proof-file="xxxxxx" --game "8queens" --key-name sound --proving-system ligetron -d '{"program": "../sdk/build/examples/8queen.wasm", "shader-path": "../shader", "packing": 8192, "private-indices": [1, 2], "args": [{"str": "0000000000000000"}, {"str": "11111111111111111111111111111111"}, {"str": "<your-public-key>"}, {"str": "<your-commitment-string>"}]}'
```

---

## ✅ Notes

- You can view the official guide: https://github.com/soundxyz/soundness
- You can use ChatGPT to help build and check your commands
- Keep your public key and commitment secure

---

## 🙌 Credit

Guide inspired by real test runs by contributors.
