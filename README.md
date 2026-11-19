# 🩺 Pneumonia Diagnosis with Bayesian Networks

A probabilistic AI model that reasons like a doctor: it combines a patient's risk factors, symptoms and test results to estimate **what type of pneumonia they have**, then decides **whether to order an X-ray and whether to prescribe antibiotics** by weighing costs against outcomes.

---

## 🧠 The model

### 1. Bayesian network: diagnosis
Estimates the probability that a patient has **bacterial**, **viral** or **no** pneumonia from:

| Type | Variables |
|---|---|
| Risk factors | Age group, vaccination status, immunocompromised |
| Symptoms and tests | Shortness of breath, CRP blood test, chest X-ray result |

Enter what you know about a patient (the evidence) and the network updates its belief about the diagnosis. Hidden variables are summed out automatically.

### 2. Decision network: treatment
Extends the model with two decisions and the utilities behind them:
- **Do an X-ray?** It costs money and time, but adds evidence
- **Prescribe antibiotics?** Treating bacterial pneumonia has a high payoff, leaving it untreated is heavily penalised, and treating a healthy patient has a cost

The network recommends the option with the **highest expected utility**.

### 3. Analysis
The report walks through patient scenarios, compares posterior probabilities, explains how strong versus weak evidence (large studies vs small studies vs expert opinion) affects confidence, and justifies every utility value.

It also includes **propositional and first-order logic** problems solved by converting to clause form and proving with **resolution** (set-of-support and unit-preference strategies).

---

## 📁 Files

| File | Contents |
|---|---|
| `networks/1_network_structure.dne` | First network design (structure only) |
| `networks/2_bayesian_network.dne` | Full Bayesian network with probability tables |
| `networks/3_decision_network.dne` | Decision network with X-ray and antibiotic decisions and utilities |
| `report.pdf` | Full write-up: design, probabilities, scenarios, utilities and logic proofs |

## 🚀 Open it
The `.dne` files open in **[Netica](https://www.norsys.com/netica.html)** (the free limited version is enough). Load a network, click on the variables to set evidence, and watch the probabilities and recommended decisions update.

## 🛠️ Tech
Bayesian networks · decision networks · expected utility · probabilistic inference · first-order logic · resolution
