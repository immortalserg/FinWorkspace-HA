FROM ghcr.io/immortalserg/finworkspace:i18n-2b064d6cb5e28695b1fa2dbac0fc55c628f9104c

LABEL io.hass.type="app" \
      io.hass.version="1.1.1" \
      io.hass.arch="amd64|aarch64" \
      org.opencontainers.image.source="https://github.com/immortalserg/FinWorkspace-HA"

COPY run.py /app/ha-run.py
CMD ["python", "/app/ha-run.py"]
