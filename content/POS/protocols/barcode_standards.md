---
title: "Barcode Standards"
menuTitle: "Barcode Standards"
date: 2018-05-07T10:32:12+09:30
draft: false
weight: 1
---

<h3>Barcode Standards</h3>

Oxipay uses the <a href="https://en.wikipedia.org/wiki/Code_128">Code 128</a> symbology for pre-approval barcodes, specifically code set B (128B). 128B allows for characters 0–9, A–Z (uppercase) and a–z (lowercase), however we currently only use numeric values 0–9 in the barcode.

The length of encoded data is currently 10 digits, which includes 4 static digits, "6199", followed by 6 generated digits. The reason for starting the encoded data with "6199" is so that POS software vendors can make some inferences about barcodes in this format. If a barcode is scanned that starts with "6199" they could assume it's an Oxipay payment. Essentially the POS operator could be spared having to do some type of action before scanning the payment barcode saving the POS operator one or more clicks.

<div class="panel">
<b>Note</b>: Oxipay reserves the right to change the length of encoded data at any time. For this reason it's strongly advised that POS software integrators do not make any assumptions about barcode lengths.
</div>

The PROs of 128B are as follows:

* Supports alphanumeric characters, giving large combination of barcode ranges to support future business volume
* Difficult to decode our barcode standard with a combination of alphanumeric characters
* Encoded data length is extendable
