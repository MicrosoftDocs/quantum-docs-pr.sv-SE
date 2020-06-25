# <a name="articles"></a>Artiklar

I den här katalogen hittar du artiklarna om dokumentationen för Quantum Development Kit. Den här katalogen innehåller:

- **Artikel kataloger**: innehåller artiklarna för varje avsnitt i dokumentationen. I dessa kataloger kan du hitta följande innehåll:
  
  - Varje katalog innehåller en `toc.yml` fil för att visa innehållet i katalogen i huvud innehålls förteckningen (TOC).
  - Markdown-artiklar som innehåller dokumentationen. De här artiklarna bör följa rikt linjerna i [guiden Microsoft docs Contributor](https://docs.microsoft.com/en-us/contribute/).
  - Artiklarnas under kataloger. Dessa under kataloger bör också innehålla sin egen `toc.yml` fil.

> :p encil: även om det är möjligt att referera till `*.md` filerna direkt i den överordnade `TOC.yml` filen, för att hålla ordning på saker, kan vi bara se dem från den `toc.yml` aktuella katalogen.

- Huvud innehålls förtecknings ** `TOC.yml` fil (TOC)**: i den här filen visas avsnitten i innehålls förteckningen tillsammans med referensen till huvud `toc.yml` filen i katalogen för varje avsnitt.
- **`index.yml`** YAML med konfigurationen av landnings sidan i dokumentationen.
- **`\media`**: En katalog för att lagra alla avbildningar som används i dokumentationen. Den innehåller en `\media\src` under katalog för att lagra källfiler för avbildningarna.
- **Licensfiler**: filer som innehåller juridiska licenser
- **Tekniska filer**: filer som innehåller makron och metadata.

## <a name="guidelines"></a>Riktlinjer

Några allmänna rikt linjer för den här katalogens organisation för deltagare:

- Varje katalog eller under katalog ska innehålla en egen `toc.yml` fil i som kallas samma nivå artiklar eller `toc.yml` filer för dess underordnade kataloger.
- Organisationens kataloger i lagrings platsen bör vara så nära som möjligt till organisationen av innehålls förteckningen på dokumentations webbplatsen.
- Alla avbildningar ska lagras i `articles\media` och inte i mappen artiklar.
- Rubrikerna för artiklarna, namnen i innehålls förteckningen och *UID* för metadata bör vara så nära som möjligt och representerar tydligt H1-huvudet i markdown-dokumentet.

## <a name="adding-images"></a>Lägger till bilder

Om du vill att bilderna ska återges korrekt i mörkt läge måste du undvika Oh-filer.
- För `*.jpg` filer som du inte behöver göra något eftersom fil formatet inte stöder transparenta element.
- För `*.png` filer måste du lägga till en vit bakgrund eller ändra värdet för alfa kanalen till 100. Det enklaste sättet att göra detta i Windows är genom att öppna filen i Paint och spara och skriva över den ursprungliga filen.
- För `*.svg` filer måste du lägga till en vit rektangel i det lägsta lagret. Det kan du göra med Inkscape:
  - Öppna filen `*.svg`.
  - Välj verktyget Square Maker och rita en vit rektangel ovanpå den ursprungliga bilden.
  - Välj verktyget "Välj och transformera objekt" genom att klicka på den mörka pilen eller trycka på F1.
  - När du har valt rektangeln klickar du på verktygsfälts elementet "nedre markering till nederkant" (slut) ".
  - Justera rektangeln med musen och piltangenterna.
