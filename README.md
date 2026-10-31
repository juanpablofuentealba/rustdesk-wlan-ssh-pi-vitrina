# rustdesk-wlan-ssh-pi (vitrina)

Kit para **administrar computadoras de forma remota**: RustDesk (pantalla) +
SSH (trabajo real) + Tailscale (llegar desde cualquier red sin abrir puertos).

> Esta es la **versión pública/vitrina**. El kit completo (con hallazgos, flota y
> automatizaciones) es privado. Aquí se muestra el **método** y los casos
> anonimizados.

## Qué resuelve

RustDesk da acceso visual, pero no tiene CLI y en Wayland necesita setup
especial. Para *trabajar* de verdad (logs, paquetes, specs) hace falta **shell**
(SSH). Y para llegar **fuera de la LAN** sin abrir puertos: **Tailscale**.

| Pieza | Para qué |
|---|---|
| RustDesk unattended | Ver/controlar la pantalla (incluso en login) |
| SSH | Shell, logs, paquetes, specs |
| Tailscale | Acceso desde cualquier red, sin abrir puertos |
| Agente IA (opcional) | Asistencia, solo en el equipo del operador |

## Enfoque

- Detección de distro (Arch/Debian/Fedora) y gestor nativo.
- RustDesk con capturador DRM para Wayland (`libdrmtap`).
- `authorized_keys` del operador, firewall (solo 22/tcp).
- NOPASSWD acotado (solo reboot/poweroff, nunca ALL).
- Verificación de integridad (sha256) del paquete de RustDesk.

## Enlaces

- Casos documentados (anonimizados) en `docs/`.
- Guías del método en `docs/`.

## Licencia

MIT.
