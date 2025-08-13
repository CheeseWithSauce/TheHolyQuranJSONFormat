# TheHolyQuranJSONFormat
A complete Quran dataset in JSON format,available in both standard Uthmani script and Tajweed colored versions.
Includes 114 separate Surah files and one full quran.json file containing every verse.
Each verse is given a continuous global ID plus Surah/Ayah info.
Built specially for Muslim developers creating Quran apps etc

CONTENTS:
Standard Version
quran.json , the entire Quran in one file with a continuous global_id for each verse.

surahs/ – 114 separate files, one per Surah.

Tajweed Version
tajweedquran.json : full Quran with Tajweed rules which have been coded in HTML markup for color rendering.
tajweedsurahs/ : 114 separate Tajweed formatted Surah files.

File Structure
quran.json
{
  "chapters": [...],
  "verses": [
    {
      "global_id": 255,
      "surah": 2,
      "ayah": 248,
      "verse_key": "2:248",
      "text_ar": "وَقَالَ لَهُمْ نَبِيُّهُمْ..."
    }
  ]
}

surahs/{xxx}.json

{
  "surah_number": 2,
  "name_en": "Al-Baqarah",
  "name_ar": "البقرة",
  "verses_count": 286,
  "revelation_place": "madinah",
  "verses": [
    {
      "global_id": 8,
      "surah": 2,
      "ayah": 1,
      "verse_key": "2:1",
      "text_ar": "الم"
    }
  ]
}

Tajweed verse example

{
  "global_id": 151,
  "surah": 2,
  "ayah": 144,
  "verse_key": "2:144",
  "text_ar": "قَدْ نَرَىٰ تَقَلُّبَ وَجْهِكَ...",
  "text_tajweed_html": "قَ<tajweed class=qalaqah>دْ</tajweed> نَرَىٰ...",
  "tajweed_segments": [
    {
      "rule": "qalaqah",
      "text": "قَ<tajweed class=qalaqah>دْ</tajweed>"
    }
  ]
}
How to use?
Load the JSON

fetch("quran.json")
  .then(res => res.json())
  .then(data => console.log(data.verses[0].text_ar));
Tajweed rendering

Use text_tajweed_html to render color coded Quran text in HTML.

Apply RTL styling and a Uthmani font:


font-family: 'UthmanicHafs', 'Amiri Quran', serif;
direction: rtl;

Plain Arabic Text

Use text_ar for non-colored text.

Custom rule handling

tajweed_segments contains the rule name and matching text so you can highlight with your own colors.

NOTES
The text is fully Uthmani script.

Surah and Ayah numbers follow standard Quranic numbering

The Tajweed colors follow international Mushaf Tajweed standards.

If you strip HTML, you will lose Tajweed coloring but retain Arabic text.

No harakat or glyph shaping is altered Arabic rendering is left to the font.
