# VirusTotal-Bulk-IP-Scanner

This script reads a list of IP addresses from a CSV file, checks each IP address for malicious activity using the VirusTotal API, and writes the results to a new CSV file. It adheres to VirusTotal's rate limit by sending a maximum of 4 requests per minute.

### Requirements

- Python 3.x
- `requests` library
- Install the required Python package using pip:

```bash
pip install requests
```

### Description

1. **API Key Setup**: 
   - Requires a valid VirusTotal API key (`apikey`) to authenticate requests.

2. **Function `check_ip`**: 
   - Sends a GET request to VirusTotal for each IP address in the list.
   - Retrieves and parses the JSON response to extract details such as owner, country, and analysis stats (malicious, suspicious, undetected, harmless).

3. **CSV Handling**: 
   - Reads a CSV file (`IP_list.csv`) containing a list of IP addresses.
   - Writes the scan results to another CSV file (`IP_score.csv`) with columns for IP address, country, Owner, Malicious score, Suspicious score, Undetected score, and Total score.

4. **Rate Limiting**: 
   - Ensures no more than 4 API requests per minute sent by pausing execution between requests.

### Usage

1. Replace `apikey` with your own VirusTotal API key.
2. Prepare a CSV file (`IP_list.csv`) with a header row and IP addresses listed under the 'IP Address' column.
3. Adjust file paths (`input_file`, `output_file`) as per your local directory structure.
4. Run the script to initiate the scanning process.

```bash
python virustotal_ip_scan.py
```
5. Monitor the console for progress updates and any encountered errors.

---

For detailed information and updates, refer to the [VirusTotal API Documentation](https://docs.virustotal.com/reference/overview).
