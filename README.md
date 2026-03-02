# GTM Templates Library 🚀

Moje osobní knihovna prověřených GTM šablon a JSON exportů pro rychlou implementaci analytiky.

---

## 📂 Dostupné šablony

### 1. GA4 Contact Interactions (`/templates/ga4-contact-interactions.json`)
Tento kontejner slouží k automatickému měření interakcí s kontaktními údaji na webu.

**Co to měří:**
* **Kliknutí na telefon:** Detekuje odkazy začínající na `tel:`.
* **Kliknutí na e-mail:** Detekuje odkazy začínající na `mailto:`.
* **Kopírování telefonu:** Detekuje, když uživatel označí a zkopíruje (Ctrl+C) řetězec odpovídající formátu telefonu.
* **Kopírování e-mailu:** Detekuje, když uživatel zkopíruje text obsahující zavináč `@`.

**Parametry událostí v GA4:**
* `type`: Rozlišuje mezi hodnotou `click` a `copy`.
* `click_text`: Text, na který bylo kliknuto.
* `clipboardText`: Text, který byl zkopírován do schránky.

---

## 🛠️ Návod k instalaci

1.  Stáhni si `.json` soubor z tohoto repozitáře.
2.  V Google Tag Manageru jdi do **Admin** -> **Import Container**.
3.  Vyber stažený soubor a zvol možnost **Merge** (sloučit) – *nikdy nedávej Overwrite, pokud nechceš smazat stávající nastavení!*
4.  Po importu najdi proměnnou `{{v.ga4.measurementId}}` a změň její hodnotu na tvé skutečné **G-XXXXXXXXXX** ID z GA4.
5.  Zkontroluj v Preview módu a publikuj.

---

## 📝 Poznámky
Pro správné fungování měření kopírování (`textCopied`) je nutné mít na webu nasazený odpovídající JavaScript listener, který posílá událost a hodnotu `clipboardText` do DataLayeru.
