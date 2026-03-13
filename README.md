# Raspberry Pi Digital Signage Player

## Overview

This project implements a **Raspberry Pi-based digital signage player** that displays multimedia content from a remote web endpoint.  
The Raspberry Pi runs **Chromium in kiosk mode**, automatically loading a display endpoint that delivers videos and images managed by a web system.

The device acts as a **display client**, while the web platform handles:

- media uploads
- playlist generation
- scheduling
- content management

---

## System Architecture

Admin Dashboard  
↓  
Frontend Display Route  
↓  
Backend Media Storage  
↓  
Display Endpoint  
↓  
Raspberry Pi Kiosk Player  
↓  
Display Monitor / TV

The Raspberry Pi simply loads the **endpoint URL** and renders the content fullscreen.

---

## Current System Setup

### Operating System
- Raspberry Pi OS

### Display Server
- X11

### Browser
- Chromium (Kiosk Mode)

### Boot Behavior
When the Raspberry Pi boots:

1. System starts the X11 desktop session.
2. The kiosk script automatically launches Chromium.
3. Chromium opens the signage endpoint in fullscreen.
4. If the browser crashes or closes, it automatically restarts.

This ensures the signage screen is always displayed.