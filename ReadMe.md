# 公開鍵暗号を使用した文字列暗号化

## 使用したコマンド

### OpenSSL インストール

---

1. wsl のアップデート

   ```
   sudo apt update
   sudo apt upgrade
   ```

1. インストール
   ```
   sudo apt install openssl libssl-dev
   ```

### 暗号化

---

1. 秘密鍵生成

   ```
   wsl openssl genrsa -out private-key.pem
   ```

1. 公開鍵生成

   ```
   wsl openssl rsa -in private-key.pem -pubout -out public-key.pem
   ```

1. 暗号化

   ```
   wsl openssl rsautl -encrypt -in data.txt -out encrypted-data.txt -inkey public-key.pem -pubin
   ```

1. 複合化

   ```
   wsl openssl rsautl -decrypt -in encrypted-data.txt -out decrypted-data.txt -inkey private-key.pem
   ```
