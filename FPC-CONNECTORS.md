# Popular FPC/FFC Connectors Reference

For adapting the XIAO ESP32S3 Sense B2B connector (Hirose DF40HC(3.0)-30DS-0.4V(51), 0.4mm pitch, 30-pin) to a standard FPC/FFC interface.

---

## Most Common Pitches

### 0.5mm Pitch — Industry Standard (RECOMMENDED)
The most widely used FPC/FFC pitch. Cables are cheap, everywhere, and come in many lengths.

| Connector | Manufacturer | Pins | Type | Height | Notes |
|-----------|-------------|------|------|--------|-------|
| **FH12-30S-0.5SH** | Hirose | 30 | ZIF, back-flip | 1.0mm | Very popular, same manufacturer as DF40 |
| **FH12-34S-0.5SH** | Hirose | 34 | ZIF, back-flip | 1.0mm | Extra pins for power/ground |
| **68611-0300** (Easy-On) | Molex | 30 | ZIF, back-flip | 1.0mm | Common alternative |
| **52271-3069** (FFC/FPC) | Molex | 30 | ZIF, top contact | 2.0mm | Easy hand-soldering |
| **F0500WR-S-xxP** | XKB | 30+ | ZIF, back-flip | 1.0mm | Budget option, LCSC stock |
| **AFC07-S30** | JAE | 30 | ZIF, front-flip | 1.0mm | High reliability |

**0.5mm FFC cables**: Available on AliExpress/LCSC in 6-80 pin, lengths 50mm-300mm, ~$0.10-0.50 each.

### 1.0mm Pitch — Easy to Hand-Solder
Larger pitch = easier prototyping, bigger cables, more forgiving alignment.

| Connector | Manufacturer | Pins | Type | Height | Notes |
|-----------|-------------|------|------|--------|-------|
| **FH12-30S-1SH** | Hirose | 30 | ZIF | 1.0mm | 1.0mm version of FH12 |
| **52610-3069** | Molex | 30 | ZIF | 2.55mm | Through-hole option available |
| **SFW30R-1STE1LF** | Amphenol | 30 | ZIF, front-flip | 2.0mm | Robust, easy to use |

**1.0mm FFC cables**: Wider, easier to handle. Same availability as 0.5mm.

### 0.3mm Pitch — Ultra-Compact
For space-constrained designs. Harder to solder, smaller cables.

| Connector | Manufacturer | Pins | Type | Notes |
|-----------|-------------|------|------|-------|
| **BM20B(0.6)-30DS-0.4V** | Hirose | 30 | B2B/FPC | Very small, mobile phone grade |
| **502078-3030** | Molex | 30 | ZIF | SlimStack series |

---

## Connector Styles

### ZIF (Zero Insertion Force)
- Flip-lock actuator — open lock, slide cable in, close lock
- Most common for FPC/FFC
- **Back-flip**: actuator flips away from cable entry (most popular)
- **Front-flip**: actuator flips toward cable entry
- **Slide-lock**: slides forward/back

### Non-ZIF (Friction Lock)
- Cable just pushes in
- Simpler but less reliable connection
- Good for permanent installations

### Contact Side
- **Top contact**: cable pads face up (toward actuator)
- **Bottom contact**: cable pads face down (toward PCB)
- **Dual contact**: pads on both sides — most flexible, works with any cable orientation

---

## Recommended for XIAO B2B Adapter

**Best general-purpose choice:**
> **Hirose FH12-30S-0.5SH** (0.5mm, 30-pin, ZIF back-flip)
> - Same manufacturer as DF40 (consistent quality)
> - 0.5mm pitch cables are dirt cheap and universal
> - 30 pins matches the B2B pin count exactly
> - LCSC: ~$0.30-0.50

**Best for prototyping:**
> **1.0mm pitch, 30-pin ZIF** (any brand)
> - Easier to hand-solder
> - Bigger cables, easier to probe with multimeter
> - Can use individual jumper wires with an FFC breakout

**Budget option:**
> **XKB F0500WR-S-30P** or generic 0.5mm 30-pin ZIF from LCSC
> - $0.10-0.20 each
> - Works fine, just less premium feel

---

## Adapter Board Design Notes

### Option A: Rigid PCB Breakout
```
[DF40 plug] —— small PCB —— [FFC connector]
```
- DF40C(3.0)-30DP-0.4V(51) on one end (mates with XIAO socket)
- FH12-30S-0.5SH on the other end
- PCB size: ~15mm × 25mm
- JLCPCB: ~$2 for 5 boards

### Option B: Flex PCB (FPC)
```
[DF40 plug] ═══ flex ribbon ═══ [FFC connector or pads]
```
- True flexible adapter
- JLCPCB flex: ~$8-15 for 5 pieces
- More elegant but slower turnaround

### Option C: FPC to 2.54mm Headers
```
[DF40 plug] —— PCB —— [2×15 pin header]
```
- Breadboard-friendly
- Best for early prototyping
- Can use standard dupont jumpers

---

## Where to Buy

| Source | Best For | Notes |
|--------|----------|-------|
| **LCSC** | Connectors + cables | Cheapest, ships from China, huge selection |
| **DigiKey** | Hirose/Molex originals | Fast US shipping, guaranteed authentic |
| **Mouser** | Same as DigiKey | Alternative source |
| **AliExpress** | FFC cables in bulk | $0.05-0.20 per cable, many lengths |
| **JLCPCB** | PCB + assembly | Can assemble the adapter board for you |

---

## Pin Count Considerations

The XIAO B2B has 30 pins. You might want more pins on the FFC side for:
- Extra ground pins (signal integrity)
- Power distribution
- Shield/ground plane connection

A **34-pin FFC** with 4 extra grounds is a common upgrade. Or use 30-pin and dedicate 2-3 pins to ground.
