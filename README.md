# Kart Rush 3D Championship

A 3D kart racing championship for events. The laptop runs the game on the projector/TV;
up to **32 players** register by scanning a QR code, then race **4 at a time in split screen**
using their phones as controllers. No app install, no accounts.

## Two ways to run it
- **Online (no installs):** follow **ONLINE-SETUP.md** to put the game on a free web host. Everyone just opens a link.
- **On a laptop (works without internet):** follow the steps below.

## What you need (laptop mode)
- A laptop (Windows or Mac) with a reasonably modern graphics chip, connected to the projector/TV
- **Node.js** installed once: download the "LTS" version from https://nodejs.org
- The laptop and all phones on the **same Wi-Fi network**
- Everything else is included (the 3D library is bundled, so no internet is needed during the event)

## Start it
1. Unzip the folder.
2. **Windows:** double-click `start-windows.bat` · **Mac:** right-click `start-mac.command` → Open
3. Chrome opens the big screen (`http://localhost:3000/host`). Press **F11** for full screen.
4. Players scan the QR code and type their name. Their phone opens the **kart customiser** straight away
   (they can tap 🎲 Randomise or DONE to skip). Their kart then appears on the big screen next to their name.
5. Press **START CHAMPIONSHIP**. The format is picked automatically:
   - **2–4 players:** straight to the Grand Final
   - **5–7 players:** points league (3 rounds, 10/6/3/1 points), then the top 4 race the Grand Final
   - **8–32 players:** knockout. The **top 2 of every heat go through**, and the fastest losers fill any gaps.
6. Watch the draw, then follow the screen: **START HEAT → results → CONTINUE**.
   When it's someone's turn, their phone buzzes with **"YOU'RE UP!"**. When all 4 tap **READY**, the heat starts automatically.

Heats are **3 laps (~3 min)**. The **Grand Final is 5 laps (~5 min)**.
Keyboard: **Enter** = next step / start. Keep the black server window open the whole time.

## Items
| | Item | What it does |
|---|---|---|
| ⚡ | Turbo | Speed burst |
| 🛢️ | Oil Slick | Dropped behind you; whoever hits it spins out |
| 💥 | Zapper | Bolt fired forward, bounces off rails |
| 🎯 | Homing Drone | Chases the racer directly ahead of you |
| 🛡️ | Shield | Blocks one hit (and stops the TNT being passed to you) for 8 s |
| 🌰 | Durian Bomb | Thrown ahead: splats every rival's screen for 3 s and leaves a stink cloud that slows anyone driving through |
| 🧨 | TNT Bomb | Hot potato, 10-second fuse (no reset). Bump someone to pass it on; whoever holds it at 0 explodes |
| ⛈️ | Thunderstorm | Rare, last place only: slows everyone ahead for 3 s |

Racers at the back get the stronger catch-up items more often.

## Kart customiser (on the phone)
- **Kart:** body (Classic / Rocket / Buggy), main + accent colour, wheels (Standard / Sporty / Gold), racing number, side sticker (star, flame, bolt, flag, heart)
- **Driver:** skin tone, outfit colour, headwear (helmet, cap, songkok, tudong, headband, crown), face (happy, cool, determined, cheeky)
- **Extras:** boost-trail colour (fire, blue, green, pink, rainbow) and horn sound (beep, duck, truck, clown, trumpet)
- Live 3D preview (drag to spin) and a 🎲 Randomise button. Choices are saved on the phone.
- Players can change their kart any time **until their heat is called**. The 🎨 Customise kart button is on their waiting screen.
- **Horn:** 📢 on the waiting screen and in the race. The horn plays through the big-screen speakers and shows 📢 above the kart.

## Good to know
- **If a phone drops out** (screen lock, app switch), that kart drives on autopilot. Reopening the page reconnects.
- **If the big-screen page is refreshed or closed by accident**, reopen `http://localhost:3000/host` within a minute. The championship continues where it left off.
- **Test the venue Wi-Fi beforehand.** Some guest Wi-Fi blocks devices from seeing each other. If phones can't open the link, use a phone hotspot or a small travel router.
- On Windows, allow the firewall prompt the first time (private networks).
- **Test bots:** "+ 4 test bots" on the registration screen lets you try the full championship alone. Hold **F** during a race to fast-forward (for testing only).

## Tracks (one is picked at random for every race, never the same twice in a row)
| Track | Setting | Lap |
|---|---|---|
| **Water Village Run** | Wooden boardwalks over the river, stilt houses, boats, golden-domed mosque on an island | ~1 min |
| **Capital Circuit** | City streets with tall buildings, street lamps and palms, a golden-domed mosque in a lagoon | ~55 s |
| **Rainforest Rush** | Jungle dirt trail with hills, a high crossing over the river, a waterfall and a longhouse | ~1 min 5 s |
| **Bridge Sprint** | Sweeping cable-stayed sea bridge high above the bay, islands and sailing boats | ~1 min |
| **Beach Blast** | Golden-hour beach with palms, umbrellas, beach huts, a jetty and a lighthouse | ~1 min 5 s |

---
Characters, tracks and items are original. Bundled: three.js r170 (MIT licence) and the QR generator from
`qrcode-terminal` (Apache License 2.0, see `vendor/QRCode`).
