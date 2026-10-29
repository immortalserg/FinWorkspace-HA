FROM ghcr.io/immortalserg/homefinance:1.3.3

LABEL io.hass.type="app" \
      io.hass.version="1.0.0" \
      io.hass.arch="amd64|aarch64" \
      org.opencontainers.image.source="https://github.com/immortalserg/HomeFinance-HA"

COPY run.py /app/ha-run.py
CMD ["python", "/app/ha-run.py"]
