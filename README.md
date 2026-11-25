# Dear Future Me

A digital time capsule app prototype. Write a letter, add photos and pick a date. The capsule stays locked until that day.

## Run it
Open `index.html` in a browser. There is nothing to install or build. Fonts load from Google Fonts, so the first load needs an internet connection.

## Host it on GitHub Pages
1. Create a repository and upload `index.html` and `README.md` to it.
2. Go to Settings > Pages.
3. Under "Build and deployment", choose "Deploy from a branch", pick `main` and `/ (root)`, then Save.
4. After a minute your prototype is live at `https://<your-username>.github.io/<repo-name>/`.

## What the prototype does
- Onboarding: splash, three intro slides, name and goal, welcome
- Create a capsule: name, cover (default or from your gallery), letter, photos (default or from your gallery), unlock date, review and seal
- Home, Memories timeline, Profile and Settings tabs
- Micro-interactions on photo picking, date picking and sealing

## Notes
- Everything is saved in your browser (`localStorage`). Nothing is sent anywhere.
- The three starter capsules are sample data. Settings > Reset sample capsules restores them.
- Fonts: DM Mono, Instrument Sans and Caveat. Screens follow the Figma design.
