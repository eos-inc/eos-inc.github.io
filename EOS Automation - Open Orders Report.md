
## Details

| ID                    | `OPENORDERS`                                    |
| --------------------- | ----------------------------------------------- |
| **Schedule Interval** | `1 Hour` at `:00`                               |
| **Purpose**           | Automate the creation of the Open Orders report |

---
## Inputs

- **QuickBooks Report:** `openorders-8`
	- *Input Format:* The Excel should be renamed to `qb_open_orders.xlsx`
	- *Upload Target:* The renamed Excel should be uploaded to: `EOS_Automations/OPENORDERS/upload` in Dropbox
- **QuickBooks Report:** `openorders-detail`
	- *Input Format:* The Excel should be renamed to `qb_open_orders_detail.xlsx`
	- *Upload Target:* The renamed Excel should be uploaded to: `EOS_Automations/OPENORDERS/upload` in Dropbox

---
## Outputs

- **Customized Report:** `eos_open_orders`
	- *Output Format:* The Excel output will be named `eos_open_orders_yyyymmdd.xlsx` where `yyyymmdd` is the Year, Month, and Day formatted date for the report creation
	- Download Target:* The processed Excel can be downloaded from: `EOS_Automations/OPENORDERS/download` in Dropbox
- **Archived Copy:** `eos_open_orders`
	- *Output Format:* The Excel output will be named `eos_open_orders_yyyymmdd.xlsx` where `yyyymmdd` is the Year, Month, and Day formatted date for the report creation
	- *Archive Target:* The processed Excel will be copied to `/datasets/OPENORDERS/archive` folder in the AWS S3 cloud storage bucket (`eos-inc`)

---
## Process Flow

*`TODO`*

---
## User Instructions

1. Export the `openorders-8` and `openorders-detail` reports from Quickbooks and save them to your local files.
2. Rename the exported QB reports to `qb_open_orders.xlsx` and `qb_open_orders_detail.xlsx`, respectively.
3. Upload the renamed Excel files to Dropbox in: `EOS_Automations/OPENORDERS/upload`![[Pasted image 20240331153718.png]]
4. The automation will run every hour at `:00` and check for the input files in the `upload` folder - if the inputs are there, the process will execute and put the output report in the `EOS_Automations/OPENORDERS/download` folder![[Pasted image 20240331153826.png]]
5. Download the `eos_open_orders_yyyymmdd.xlsx` and move it to the normal `Reports/Orders/EOS Sales Orders` folder in Dropbox and work the report as normal.![[Pasted image 20240331153925.png]]
*Note:* An archived copy of the custom report output will be stored in the AWS S3 cloud storage bucket `eos-inc` in the `/datasets/OPENORDERS/archive` folder.