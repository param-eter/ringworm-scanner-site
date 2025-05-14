---
layout: default
title: Ringworm Scanner
---

![App icon](/assets/app_icon_1024_ultra_tight.png){: width="256" }

# Ringworm Scanner 🩺🐾

Instantly check photos of skin for signs of **ringworm** using on-device AI.  
*(No images ever leave your phone.)*

![Download on the App Store (Coming Soon)](/assets/appstore-badge.svg)

---

## Methodology
Ringworm is something that is highly contagious and can be easily spread from person to person. This makes it important to be able to identify, especially for people participating in sports and other activities where close contact or sharing of equipment is common. This includes brazilian jiu jitsu, wrestling, boxing and yoga.

Ringworm lesions, typically circular or oval-shaped, can be easily mistaken for other skin conditions. This can lead to delayed treatment and the spread of the infection to others. 

I built up a training dataset from public sources and used it to train a vision-transformer model. When looking for publically available datasets, I found that most that had ringworm images were of ringworm in different variations, but limited when it comes to the circular lesions (tinea corporis) that is more commonly seen and confused for other conditions. I also added more data for eczema, a condfition that is commonly mistaken for ringworm.

The dataset contains 2160 training samples and 550 validation samples. The classes are:
- cellulitis
- impetigo
- eczema
- athletes-foot
- nail-fungus
- ringworm
- cutaneous-larva-migrans
- chickenpox
- shingles

The evaluation performance for ringworm is as follows:

## Validation performance for FU-ringworm

|                | Predicted Negative | Predicted Positive |
|----------------|-------------------|-------------------|
| **True Negative** | 520               | 0                 |
| **True Positive** | 2                 | 21                |

- **True Negatives (TN):** 520
- **False Positives (FP):** 0
- **False Negatives (FN):** 2
- **True Positives (TP):** 21

**Metrics:**
- **Accuracy:** 99.63%
- **Precision:** 100%
- **Recall:** 91.3%

The model in it's current state is extremely performant and will improve with more data. I plan to add more data to the training set and also add more classes to the model to improve the performance.

---

### Why on-device?

* **Private** – photos never leave your device.  
* **Fast** – < 200 ms inference on Apple A17.  
* **Offline** – works without an internet connection.
* **Now recurring costs** – now subscriptions or in app purchases.s

---

[Privacy Policy](/privacy/)
