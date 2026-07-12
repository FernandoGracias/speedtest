# Independent Speed Test

An unaffiliated speed test that measures your real download speed by downloading a large file from Cloudflare's CDN. Unlike Ookla Speedtest, this tool is not operated by or affiliated with any carrier or ISP.

**Live:** https://speedtest.jdgregson.com

## Why This Exists

ISPs and mobile carriers use deep packet inspection to selectively throttle traffic while whitelisting known speed test servers (like Ookla's) to hide the throttling. This tool downloads from Cloudflare R2 — a generic CDN endpoint that carriers have no reason to treat specially — giving you a more accurate picture of your real-world throughput.

## How It Works

- Opens a single HTTPS connection to a 2GB file on Cloudflare R2
- Measures bytes received every 250ms for 48 samples (~12 seconds)
- Displays real-time speed, a live graph, and final stats (peak, average, low, duration)
- Uses browser Geolocation API (optional) to show your position on the 3D globe

## How to Use

Compare your results here against Ookla Speedtest (speedtest.net) and Netflix's fast.com. If Ookla shows significantly higher speeds than this tool, your ISP may be whitelisting Ookla's servers while throttling other traffic.

## Tech

- Three.js for the 3D globe with Natural Earth 110m coastline data
- Canvas 2D for the real-time speed graph
- Single-page static HTML, hosted on GitHub Pages
- Test data served from Cloudflare R2 (WNAM region)

## License

MIT
