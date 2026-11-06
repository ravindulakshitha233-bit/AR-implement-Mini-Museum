# Space Explorer – Marker-Based WebAR

A mobile-friendly A-Frame + AR.js project for the Hiro marker assignment.

## Project files

- `index.html` – complete marker-based WebAR scene, interactions, status messages and camera diagnostics.
- `models/astronaut.glb` – supplied astronaut GLB model (Draco-compressed).

Keep the `models` folder beside `index.html`; do not upload only the HTML file.

## Run locally on your computer

1. Extract the ZIP.
2. Open the `Space_Explorer_AR_Fixed` folder in Visual Studio Code.
3. Install the **Live Server** extension.
4. Right-click `index.html` and choose **Open with Live Server**.
5. Allow camera access in the browser.
6. Show the complete Hiro marker to the webcam.

Use the Live Server URL on the same computer (`http://localhost:...` or `http://127.0.0.1:...`). These loopback origins are treated as secure by modern browsers.

## Run on a phone (important)

A phone opening `http://192.168.x.x:5500` from your computer is using an ordinary HTTP LAN address. Browsers normally block camera access on that address, even if permission was granted earlier. `localhost` on your computer does not make the computer's LAN address secure on the phone.

Deploy the complete folder to an HTTPS host:

### Netlify Drop

1. Visit https://app.netlify.com/drop and sign in if requested.
2. Drag the **entire `Space_Explorer_AR_Fixed` folder** onto the page.
3. Wait for Netlify to publish it and copy the `https://....netlify.app` URL.
4. Open that HTTPS URL in Chrome (Android) or Safari (iPhone).
5. Allow camera access. If prompted, choose the rear/world-facing camera.
6. Hold the Hiro marker fully inside the camera view in bright, even lighting.

### GitHub Pages

1. Create a **public** GitHub repository.
2. Upload `index.html`, `README.md`, and the complete `models` folder to the repository root.
3. Open **Settings → Pages**.
4. Under Build and deployment, select **Deploy from a branch**, choose `main` and `/ (root)`, then Save.
5. Wait for the Pages URL (`https://<username>.github.io/<repository>/`) and test it on a phone.

## Assignment checklist

| Requirement | Implementation |
|---|---|
| Hiro marker scene | `a-marker preset="hiro"` |
| At least four objects and two primitive types | Box, spheres, torus and plane |
| Text label | `a-text` labels: SPACE EXPLORER and TAP TO EXPLORE |
| Two different animations | Rotating box/Earth/astronaut and bouncing Moon/planet |
| Non-workshop GLB model | Supplied astronaut GLB |
| Workshop ball interaction | Tap the pink planet to cycle through five colours |
| New custom interaction | Tap Saturn to grow/shrink it (`grow-object` component) |
| Marker status banner | Green FOUND and red SEARCHING states |
| Hosting / phone test | Publish to HTTPS and perform the phone test described above |

## Camera troubleshooting

- **Permission was allowed but no camera opens:** confirm the page is HTTPS (phone) or localhost (computer), check the browser's site camera permission, close other apps using the camera, then reload.
- **Black screen on a phone:** open the HTTPS deployment directly in the phone browser; do not use a `file://` URL or a plain `http://192.168...` LAN URL.
- **Wrong camera:** use the browser/site camera controls to select the rear camera if available. Browser and device camera selection varies by device.
- **Camera opens but marker is not detected:** use a printed or clearly displayed Hiro marker, keep all four marker corners visible, avoid glare, and provide even lighting.
- **Objects do not appear:** check that the marker is the Hiro marker and inspect the browser console for CDN/network errors.
- **Astronaut does not appear:** confirm `models/astronaut.glb` is present at that exact path and that the browser can access the Draco decoder CDN. The project loads the Draco-compressed GLB through an explicit `GLTFLoader` + `DRACOLoader` setup.
- **External scripts do not load:** internet access is required because A-Frame, AR.js, Three.js loader helpers and the Draco decoder are loaded from CDNs.

## 3D model credit and licence note

The supplied project's previous README attributed the astronaut asset to **NASA 3D Resources** and linked https://github.com/nasa/NASA-3D-Resources. The GLB itself contains no embedded copyright or licence metadata, so the exact source asset and its applicable licence could not be independently confirmed from the file alone. Before public redistribution, identify the exact model page in NASA's repository and retain its specific attribution/licence terms. Do not describe the licence as verified until that check is complete.

## Submission items still requiring your accounts / device

The code and project structure are prepared, but I cannot publish to your GitHub/Netlify accounts or physically test your phone from this workspace. To finish the submission requirement, you must:
1. Publish the complete project to a **public** GitHub repository.
2. Deploy it to HTTPS (Netlify Drop or GitHub Pages).
3. Open the deployed link on a real phone, grant camera permission, and test marker detection and both interactions.
4. Put your actual GitHub repository URL and group number in the Word submission document, then rename that document using your group number.
