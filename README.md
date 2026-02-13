# Frappe Translations
Custom gettext translation files _(.po)_ for Frappe Framework apps.

#### Note: These translations are specifically tailored and optimized for our internal ERP version to ensure terminology alignment with our business workflows.

## Installation & Deployment

To apply these translations to your Frappe environment, run the following commands from your `frappe-bench` directory.

### 1. Create missing locale folders
Ensure the target directories exist for apps that might not have them initialized:

```bash
# If necessary, create locale folders for apps missing them
mkdir -p apps/erpnext/erpnext/locale
mkdir -p apps/hrms/hrms/locale
```

### 2. Copy translation files
Use `curl`, `wget` or other tool of your preference to fetch the latest _.po_ files for each language directly into your local app directories:

#### 2.1 Frappe Framework
```bash
curl https://raw.githubusercontent.com/dutlabs/frappe-translations/main/frappe/pt_BR.po -o apps/frappe/frappe/locale/pt_BR.po
```

#### 2.2 ERP
```bash
curl https://raw.githubusercontent.com/dutlabs/frappe-translations/main/erp/pt_BR.po -o apps/erpnext/erpnext/locale/pt_BR.po
```
#### 2.3 HRMS
```bash
curl https://raw.githubusercontent.com/dutlabs/frappe-translations/main/hrms/pt_BR.po -o apps/hrms/hrms/locale/pt_BR.po
```

## 3. Apply changes
After downloading the files, clear the cache and restart your bench for the changes to take effect:

```bash
bench compile-po-to-mo
bench clear-cache
```
