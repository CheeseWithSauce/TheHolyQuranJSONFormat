# TheHolyQuranJSONFormat
A complete Quran dataset in JSON format with 114 per surah files and one full quran.json containing every verse. Each verse has a continuous global ID for easy lookup, plus surah/ayah info and Arabic text. Made specially keeping our Muslim devs in mind.

!!!DEVELOPER REFERENCE!!!
This dataset provides the full text of the Qur’an in Arabic (Uthmani Script) structured specifically for easy use in Apps etc

What you get:-

quran.json : the entire Quran in one file with a continuous global ID for each verse.

surahs/  114 separate files, one per surah.

1. File Structure
quran.json
Top-level:


chapters

verses

Each verse object:


{
  "global_id": 255,
  "surah": 2,
  "ayah": 248,
  "verse_key": "2:248",
  "text_ar": "وَقَالَ لَهُمْ نَبِيُّهُمْ..."
}
surahs/{xxx}.json
Each file contains:


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
