# Digital Arabic — عربية رقمية

**A Left-to-Right Arabic Alphabet for Engineering and Computing**

**Version:** 1.0  
**Status:** Stable  
**Arabic name:** عربية رقمية  
**English name:** Digital Arabic  

---

## 1. Purpose

**Digital Arabic** is an alternative Arabic writing system designed for **engineering, software, and technical environments**.

It preserves **Arabic orthography and spelling** while removing structural properties of the traditional Arabic script that conflict with modern computing systems:

- right-to-left directionality
- contextual shaping
- positional glyph variants
- dependence on the Unicode Bidirectional Algorithm

Digital Arabic is **not**:
- a transliteration
- a phonetic alphabet
- a replacement for traditional Arabic writing

It is a **technical encoding** of Arabic, optimized for robustness, predictability, and interoperability.

---

## 2. Core Principles (Normative)

Digital Arabic follows these mandatory rules:

### 2.1 Left-to-right only
All characters have Unicode **Bidirectional Class = L**.  
No RTL characters, no bidi controls, no positional dependence.

### 2.2 One letter = one code point
- No joining
- No contextual shaping
- No positional variants

### 2.3 Arabic orthography preserved
Arabic spelling rules remain unchanged.

### 2.4 No vowel category
Arabic is treated as a **consonantal system**.

- Those are **letters**, not vowels: ا و ي
- They must be written where Arabic spelling requires them
- Shakl never replaces base letters

### 2.5 Explicit hamza
Hamza is a **full letter**.

- No carrier logic
- No positional rules
- No أ إ ؤ ئ
- Written exactly where hamza occurs

### 2.6 Engineering robustness
Digital Arabic must render identically in:

- terminals
- source code
- logs
- configuration files
- databases
- version control systems

---

## 3. Alphabet Inventory

Digital Arabic consists of **31 letters**:

- **28 Arabic letters**
- **1 hamza letter**
- **3 additional letters for loanwords**: P, G, V

Capitalization follows standard Latin conventions.

---

## 4. Alphabet Mapping (v1.0 — Final)

| Arabic | Name | Upper | Lower | Unicode |
|------|------|------|------|--------|
| ا | alif | A | a | U+0041 / U+0061 |
| ب | ba | B | b | U+0042 / U+0062 |
| ت | ta | T | t | U+0054 / U+0074 |
| ث | tha | Θ | θ | U+00DE / U+00FE |
| ج | jim | J | j | U+004A / U+006A |
| ح | ḥa | Շ | շ | U+0547 / U+0577 |
| خ | kha | X | x | U+0058 / U+0078 |
| د | dal | D | d | U+0044 / U+0064 |
| ذ | dhal | Ð | ð | U+00D0 / U+00F0 |
| ر | ra | R | r | U+0052 / U+0072 |
| ز | zay | Z | z | U+005A / U+007A |
| س | sin | S | s | U+0053 / U+0073 |
| ش | shin | C | c | U+0043 / U+0063 |
| ص | ṣad | Σ | σ | U+03A3 / U+03C3 |
| ض | ḍad | Δ | δ | U+0394 / U+03B4 |
| ط | ṭa | Φ | φ | U+03A6 / U+03C6 |
| ظ | ẓa | Ψ | ψ | U+03A8 / U+03C8 |
| ع | ʿayn | Ƹ | ƹ | U+01B8 / U+01B9 |
| غ | ghayn | Ɣ | ɣ | U+0393 / U+03B3 |
| ف | fa | F | f | U+0046 / U+0066 |
| ق | qaf | Q | q | U+0051 / U+0071 |
| ك | kaf | K | k | U+004B / U+006B |
| ل | lam | L | l | U+004C / U+006C |
| م | mim | M | m | U+004D / U+006D |
| ن | nun | N | n | U+004E / U+006E |
| ه | ha | H | h | U+0048 / U+0068 |
| و | waw | W | w | U+0057 / U+0077 |
| ي | ya | Y | y | U+0059 / U+0079 |
| ى | alif maqṣūra | A | a | U+0041 / U+0061 |
| ء | hamza | Ɔ | ɔ | U+0186 / U+0254 |
| ة | tāʾ marbūṭa | Þ | þ | U+00DE / U+00FE |
| — | loanword P | P | p | U+0050 / U+0070 |
| — | loanword G | G | g | U+0047 / U+0067 |
| — | loanword V | V | v | U+0056 / U+0076 |

---

## 5. Hamza (ء)

- Encoded as **Ɔ / ɔ**
- Treated as a full consonant
- Written exactly where hamza occurs
- No carrier logic

---

## 6. Tāʾ marbūṭa (ة)

- Encoded as **þ / Þ**
- Orthographic marker, not phonetic
- Preserves distinction from:
  - ت (t)
  - ه (h)

Optional rendering rules may be applied externally, but **encoding is fixed**.

---

## 7. Vocalization (Shakl)

Vocalization is optional, exactly as in Arabic.

Shakl are **letters**, written **after** the consonant they annotate.

### 7.1 Shakl Inventory

| Arabic | Function | Marker | Unicode |
|------|--------|--------|--------|
| َ | fatḥa | α | U+03B1 |
| ِ | kasra | i | U+0069 |
| ُ | ḍamma | u | U+0075 |
| ْ | sukūn | ə | U+0259 |

### 7.2 Shadda (Gemination)

No special symbol.  
Represented by **doubling the consonant**.

Examples:
شدّ → cdd
مدّ → mdd
حقّ → Ƹqq


### 7.3 Tanwīn (Nunation)

Represented by **doubling the shakl marker**, not by adding n.

| Arabic | Encoding |
|------|---------|
| ً | αα |
| ٍ | ii |
| ٌ | uu |

---

## 8. Punctuation, Digits, and Symbols

All Arabic punctuation and symbols are normalized to **LTR equivalents**.

Examples:

| Arabic | Digital |
|------|--------|
| ، | , |
| ؛ | ; |
| ؟ | ? |
| ٪ | % |
| ﴾ ﴿ | ( ) |
| ٠١٢٣٤٥٦٧٨٩ | 0123456789 |

All bidi controls are **removed**.

---

## 9. Engineering Advantages

Digital Arabic provides:

- deterministic rendering
- safe cursor movement
- stable diffs
- no bidi attacks
- fixed string order
- monospaced compatibility
- safe identifiers and logs

**Arabic that behaves like Latin text in computing systems, without ceasing to be Arabic.**

---

## 10. Non-Goals

Digital Arabic does **not** aim to:

- replace traditional Arabic writing
- change Arabic spelling
- encode phonetics
- compete with Arabic Unicode

---

## 11. Versioning

**v1.0:** Alphabet, hamza, tāʾ marbūṭa, shakl, and punctuation rules frozen.

---

## 12. License

This specification is released under the **MIT License**.
