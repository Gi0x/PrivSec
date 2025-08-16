Regex option (/keyword/i)

✅ Pros:
	•	Case-insensitive by default with the /i flag.
	•	Can match plural forms and variations (/cards?/i matches “card” and “cards”).
	•	Can target whole words or complex patterns, reducing false positives.
	•	Lets you match multiple words in one rule (/birth chart/i).

⚠️ Cons:
	•	More complex to maintain.
	•	Slightly slower to read through for large lists.

💡 Best for:
When you have a large, carefully curated list and want to avoid blocking unrelated results (e.g., blocking “moon sign” but not “moonlight signal”).

⸻

Wildcard option (*keyword*)

✅ Pros:
	•	Extremely simple to create and read.
	•	Quick to add new terms without worrying about regex syntax.
	•	Works well for broad blocking sweeps.

⚠️ Cons:
	•	Case-sensitive unless your search engine treats it otherwise.
	•	Matches any part of a URL or title, even inside unrelated words (e.g., *leo* could block “Galileo”).
	•	No plural handling — you must add separate entries for singular and plural.

💡 Best for:
If you don’t care about some false positives and want fast setup.
