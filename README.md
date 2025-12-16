# Mini Tools Documentation

Mini-tools repo is created to develop APIs for tools that can directly be used by consumers by a simple API call and hence, reduce their development time. The backend doesn't store any personal data of the users and hence, is totally secure. The steps on how to access and use the APIs are mentioned below. In case of any queries or feedback, feel free to reach out at:  
**nidhi.business.infotech@gmail.com**

## Mini Tools – Implementation Guide

To get access to a Mini Tool API, the user must first complete a payment for the respective tool.

Once the payment is successful, an **API key** is provided via a **redirect response**.

**Important**
- The API key is **non-retrievable**
- Refreshing the redirect page will permanently remove the key
- Please **store the API key securely**

---

## Customer Dashboard

Manage your subscriptions here:

**Dashboard Link**  
https://customer.dodopayments.com/login/bus_eIyI1p0KKrr4kzPzV4BeT

---

## Using the APIs

Once you have received your API key, you can start using the Mini Tool APIs as described below.

---

### PDF Encryption API

#### Checkout Link

https://checkout.dodopayments.com/buy/pdt_0EoYXtefCr6FtFoVrsJRM?quantity=1&redirect_url=https://mini-tools-live.onrender.com%2Fapi%2Fget-key%3Fproduct_id%3Dpdt_0EoYXtefCr6FtFoVrsJRM

---

#### Description

- Upload a PDF file along with a password
- The API returns the **encrypted PDF file**
- Uploaded files are **deleted immediately after processing**
- Maximum upload size: **10 MB**

**Note**  
Please avoid spaces in the filename as it may cause download issues.  
This will be fixed in an upcoming backend release.

---

#### Sample cURL Request

Replace values inside `< >` with actual values.

```bash
curl --location 'https://mini-tools-live.onrender.com/api/encrypt-pdf' \
--header 'Authorization: Bearer <API-key>' \
--form 'file=@"<Absolute-Filepath>"' \
--form 'password="<pdf-password>"'
```

---

### PDF Decryption API

#### Checkout Link

https://checkout.dodopayments.com/buy/pdt_RvgwnSoMrpDKAIUGEXAlI?quantity=1&redirect_url=https://mini-tools-live.onrender.com%2Fapi%2Fget-key%3Fproduct_id%3Dpdt_RvgwnSoMrpDKAIUGEXAlI

---

#### Description

- Upload an encrypted PDF file along with its password
- The API returns the **decrypted PDF file**
- Uploaded files are **deleted immediately after processing**
- Maximum upload size: **10 MB**

**Note**  
Please avoid spaces in the filename as it may cause download issues.  
This will be resolved from our backend in the next release.

---

#### Sample cURL Request

Replace values inside `< >` with actual values.

```bash
curl --location 'https://mini-tools-live.onrender.com/api/decrypt-pdf' \
--header 'Authorization: Bearer <API-key>' \
--form 'file=@"<Absolute-Filepath>"' \
--form 'password="<pdf-password>"'
```

