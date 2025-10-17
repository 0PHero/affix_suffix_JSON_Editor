>>>> # ![JSON](logo.png)
>>> # Rarity Editor
>> 
>> ## To-Do:
> - [x] [[SUGGESTION] Longer "Items" section](https://gitlab.rafisa.net/j.meier/affix_suffix_json_editor/-/issues/1)
> - [x] [[SUGGESTION] more themes](https://gitlab.rafisa.net/j.meier/affix_suffix_json_editor/-/issues/2)
> 
> suggest features at the [Issues page](https://gitlab.rafisa.net/j.meier/affix_suffix_json_editor/-/issues) (please assign all issues to me)
> 
> [▶︎](https://www.youtube.com/watch?v=AD5wuYqMpVM) •၊၊||၊|။||||။‌‌‌‌‌၊|• 0:10
> 
>> ## Overview
> The **JSON Rarity Editor** is a browser‑based tool for creating, editing, and exporting item data stored in a specific JSON structure. It is implemented  entirely in HTML, CSS, and vanilla JavaScript, with no external dependencies.
> 
> The editor provides:
> - Uploading existing JSON files in the required format.
> - Creating new rarity templates from scratch.
> - Editing item names, descriptions, and their stats.
> - Managing rarity categories (`common`, `rare`, `epic`, `godly`, `magic`).
> - Adding, renaming, and deleting stats within each item.
> - Selecting stat **Type** (`fixed`[^fixed], `prc`[^prc], `rprc`[^rprc], `race`[^race]) via a visible dropdown.
> - Editing `fixed`[^fixed], `prc`[^prc], `stack`[^stack], `rprc`[^rprc], and `race`[^race] (min/max) values.
> - Downloading the updated JSON back to a file.
> - Multiple themes.
> 
>> ## JSON Format
> Each item is stored inside a rarity category as:
> ```json
> {
>   "rarity": {
>     "Item Name": [
>       "Description",
>       {
>         "attribute": {
>           "fixed": 0,
>           "prc": 10,
>           "rprc": { "min": 5, "max": 20 },
>           "stack": 2
>         }
>       }
>     ]
>   }
> }
> ```
> 
> 
>> ## Features
> 1. **Upload JSON** – Select and load a `.json` file from your computer.
> 2. **Load sample JSON** – Inserts demo items to quickly test the editor.
> 3. **New Template** – Resets the editor to an empty template with all rarity categories.
> 4. **Rarities panel** – Choose which rarity to view or edit.
> 5. **Items panel** – Displays items within the selected rarity. Items can be edited, renamed, or deleted.
> 6. **Editor panel** – Modify the selected item:
>    - Change item name and description.
>    - Add new stats and configure their type.
>    - Use dropdown to select attributes or define custom ones.
>    - Enter values for `fixed`[^fixed], `prc`[^prc], `stack`[^stack], or `rprc (min/max)`[^rprc].
> 7. **Preview JSON** – Shows the current state in real time.
> 8. **Download JSON** – Exports the edited data as a `.json` file.
> 
>> ## Usage
> 1. Open `index.html` in any modern browser (Chrome, Firefox, Edge).
> 2. Use the **Upload JSON** button to load an existing file or click **Load sample JSON** to test.
> 3. Select a rarity, then select or create an item.
> 4. Edit attributes, values, and types in the Editor panel.
> 5. Use **Download JSON** to save your changes.
> 
>> ## Requirements
> - Modern web browser (no server or build tools required).
> - JSON files must follow the described format.
> 
>> ## Notes
> - Duplicate item names within a rarity are not allowed.
> - Duplicate attribute names in a single item are warned and can overwrite if confirmed.
> - Clearing input values for `prc`[^prc], `rprc`[^rprc], or `stack`[^stack] removes them from the JSON.
> 
> 
> [^fixed]:`fixed` is always present. For percentage‑based stats, `fixed` is auto‑calculated.
> 
> [^prc]: `prc` represents a fixed percentage change.
> 
> [^rprc]: `rprc` allows a range (`min` / `max`).
> 
> [^stack]: `stack` is optional and determines how many times the effect can exist.
> [^race]: `race` determines if only one race should be able to use the item