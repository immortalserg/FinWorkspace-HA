FROM ghcr.io/immortalserg/finworkspace:mobile-auth-1

LABEL io.hass.type="app" \
      io.hass.version="1.1.3" \
      io.hass.arch="amd64|aarch64" \
      org.opencontainers.image.source="https://github.com/immortalserg/FinWorkspace-HA"

COPY run.py /app/ha-run.py
CMD ["python", "/app/ha-run.py"]
