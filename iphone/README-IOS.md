
## iOS v2 mobile UX
- The app requests landscape orientation at launch through Capacitor Screen Orientation.
- Touch devices use a smaller 0.75 km default proximity zone with a thin/no-fill idle ring.
- Track details are presented as a compact bottom selection sheet on touch devices rather than a desktop-style hover card.
- Landscape side panels are compact to keep the map as the primary surface.

After installing this version, run `npm install` once so `@capacitor/screen-orientation` is installed, then `npm run build`, `npx cap sync ios`, and `npx cap open ios`.


v2.2 uses a full-bleed landscape canvas. Safe-area insets protect interactive content while backgrounds extend beneath the Dynamic Island / rounded edges. Sensor labels are suppressed on the touch map to reduce overlap; tap a sensor for details.

## iOS v2.4 — device location + touch interaction
- On iPhone/iPad, the proximity alert origin requests the device's current location at startup and moves the map/origin there when permission is granted.
- If location is denied or unavailable, the existing demo origin remains in use.
- Reset Alert Zone returns to the latest acquired device location on touch devices.
- Desktop hover detail behavior is preserved, but hover-driven sensor coverage and track-detail interactions are disabled on touch devices. Mobile uses explicit taps instead.
- This version adds `@capacitor/geolocation`. After `npm install`, run `npx cap sync ios`.
- If Xcode does not automatically provide a location usage string, add `NSLocationWhenInUseUsageDescription` to the App target Info settings, e.g. “RECON COPILOT uses your location to place the proximity alert origin.”

## v2.5.2 phone layout
- iPhone uses a three-view bottom navigation: Sensors/Reports / Map / Control.
- Map is the default view and receives the full content area.
- Alerts are global overlays and appear over every phone view.
- iPhone and iPad are landscape-only. The app requests landscape orientation at launch.
- iPad/dashboard layout is preserved from v2.4.1.


## v2.5.2 phone layout
- SENSORS/REPORTS is split into two side-by-side panes in landscape.
- CONTROL is split into Tracks and Simulation/Tools panes.
- The phone bottom navigation bar is reduced to preserve map height.
- iPad layout remains unchanged.

- v2.5.3: Fixed legacy mobile max-height creating an empty black band; enlarged phone sensor cards to use the full Sensors half-pane.
