FROM ghcr.io/immortalserg/finworkspace:1.5.0

LABEL io.hass.type="app" \
      io.hass.version="1.1.0" \
      io.hass.arch="amd64|aarch64" \
      org.opencontainers.image.source="https://github.com/immortalserg/FinWorkspace-HA"

COPY run.py /app/ha-run.py
CMD ["python", "/app/ha-run.py"]
