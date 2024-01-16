# publish_vite_project

**1. Skapa ett Vite-projekt** 

Kör följande kommando för att skapa ett nytt Vite-projekt:


```
npm create vite@latest mitt-vite-projekt
```

**2. Navigera till din projektmapp**

```
cd mitt-vite-projekt
```

**3. Installera dependencies**

```
npm install
```

**4. Skapa en vite.config.js-fil**

Skapa en vite.config.js-fil i rotkatalogen för ditt projekt. Den här filen kommer att innehålla dina Vite-konfigurationsinställningar:

```
import { defineConfig } from 'vite';

export default defineConfig({
  base: '/ditt-repo-namn/', // Ändra till namnet på din GitHub-repo
});
```

`base` ska matcha namnet på din GitHub-repo om du publicerar på GitHub Pages.

**5. Skapa ett github repo för ditt projekt**

Gå till github.com och skapa ett repo. Skriv följande i den mapp du sksa använda.

```
echo "# sdf" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/ditt-användarnamn/ditt-repo-namn.git
git push -u origin main
```

**6. Bygg ditt projekt**

Generera filer för produktion (alltså för hosting) av ditt projekt genom att köra:

```
npm run build
```


**7. Skapa en gh-pages branch och kopera dist-mappen dit**

```
git checkout -b gh-pages
```

Kopiera innehållet i `dist` in till branchen gh-pages

```
cp -r dist/* .

```

**8. Commita och pusha innehållet i gh-pages grenen**

```
git add .
git commit -m "Publishing to GitHub Pages"
git push origin gh-pages
```

**9. Konfigurera Github Pages i ditt repo**

1. Gå till `Settings` i ditt repo
2. Gå till `Pages`
Under `Branch` välj "gh-pages" i dropdown.
3. Spara
