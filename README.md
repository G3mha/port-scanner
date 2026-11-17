# Port Scanner

A Python CLI that checks TCP ports on a host, one port at a time. It uses a
0.5-second connection timeout and color-coded terminal output.

## Run

```bash
git clone https://github.com/G3mha/port-scanner.git
cd port-scanner
pip install -r requirements.txt
python main.py
```

Enter a hostname or IPv4 address, an inclusive port range, and whether to show
only open ports.

## Results and limits

- Open ports show a service name from Python’s local port database when available.
  This is a port-name lookup, not service detection.
- Failed connections are labeled `Closed`; the scanner does not distinguish
  refused connections from timeouts or other connection errors.
- Results are appended to `port_scan_results.json`, which is cleared on each run.
  The file contains consecutive JSON objects without separators, so it is not a
  valid JSON array or JSON Lines file. Choosing open-only output also omits
  failed connections from the file.

Requires Python 3 and `colorama`.

## License

AGPL. See [LICENSE](LICENSE).
