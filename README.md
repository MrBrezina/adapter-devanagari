# Adapter World

PE: William Montrose & David Březina & Sláva Jevčinová  
Devanagari: Lipi Raval  
Georgian: Ana Sanikidze  
Gujarati: Lipi Raval  
Tamil: Aadarsh Rajan  

## Scripts

* Cyrillic
* Devanagari
* Georgian
* Greek
* Gujarati
* Latin
* Tamil

## Styles

### Style overview

- All families have `ital` variation axis
- **masters** marked below
- All Text Extralights are used as fake Text Thin masters to compile variable fonts
- Extra "Display Extralight Master" instances with matching `wght` 55 are used as masters to compile variable fonts

                              | PE       | Hebrew   | Arabic   | Tamil    | Georgian
-----------------------------------------------------------------------------------
wght                          | [+]      | [+]      | [+]      | [+]      | [+]
opsz                          | [+]      | [+]      | [+]      |          |
slnt                          | [+]      | [+]      |          |          |
ital (always Latin parts!)    | [+]      | [+]      | [+]      | [+]      | [+]  
-----------------------------------------------------------------------------------
Text Thin                     | [+]      | [+]      | [+]      | [+]      | [+]
**Text Extralight**           | [+]      | [+]      | [+]      | [+]      | [+]
Text Light                    | [+]      | [+]      | [+]      | [+]      | [+]
Text Regular                  | [+]      | [+]      | [+]      | [+]      | [+]
**Text Medium**               | [+]      | [+]      | [+]      | [+]      | [+]
Text Semibold                 | [+]      | [+]      | [+]      | [+]      | [+]
Text Bold                     | [+]      | [+]      | [+]      | [+]      | [+]
Text Extrabold                | [+]      | [+]      | [+]      | [+]      | [+]
**Text Black**                | [+]      | [+]      | [+]      | [+]      | [+]
-----------------------------------------------------------------------------------
Text Thin Italic              | [+]      | [+]      |          |          | 
**Text Extralight Italic**    | [+]      | [+]      |          |          | 
Text Light Italic             | [+]      | [+]      |          |          | 
Text Italic                   | [+]      | [+]      |          |          | 
**Text Medium Italic**        | [+]      | [+]      |          |          | 
Text Semibold Italic          | [+]      | [+]      |          |          | 
Text Bold Italic              | [+]      | [+]      |          |          | 
Text Extrabold Italic         | [+]      | [+]      |          |          | 
**Text Black Italic**         | [+]      | [+]      |          |          | 
-----------------------------------------------------------------------------------
**Display Thin**              | [+]      | [+]      | [+]      |          | 
Display Extralight            | [+]      | [+]      | [+]      |          | 
Display Light                 | [+]      | [+]      | [+]      |          | 
Display Regular               | [+]      | [+]      | [+]      |          | 
**Display Medium**            | [+]      | [+]      | [+]      |          | 
Display Semibold              | [+]      | [+]      | [+]      |          | 
Display Bold                  | [+]      | [+]      | [+]      |          | 
Display Extrabold             | [+]      | [+]      | [+]      |          | 
**Display Black**             | [+]      | [+]      | [+]      |          | 
-----------------------------------------------------------------------------------
**Display Thin Italic**       | [+]      | [+]      |          |          | 
Display Extralight Italic     | [+]      | [+]      |          |          | 
Display Light Italic          | [+]      | [+]      |          |          | 
Display Regular Italic        | [+]      | [+]      |          |          | 
**Display Medium Italic**     | [+]      | [+]      |          |          | 
Display Semibold Italic       | [+]      | [+]      |          |          | 
Display Bold Italic           | [+]      | [+]      |          |          | 
Display Extrabold Italic      | [+]      | [+]      |          |          | 
**Display Black Italic**      | [+]      | [+]      |          |          | 


### Display

* **Hairline – master**
* **Thin – master**
* Extralight
* Light
* Regular
* **Medium – master**
* Semibold
* Bold
* Extrabold
* **Black – master**

### Text

Styles in parenthesis are produced, but not offered (only as a part of var. font).

* **(Thin) – master**
* **(Thin Italic) – master**
* Extralight
* Extralight Italic
* Light
* Light Italic
* Regular
* Italic
* **Medium – master**
* **Medium Italic – master**
* Semibold
* Semibold Italic
* Bold
* Bold Italic
* Extrabold
* Extrabold Italic
* **(Black) – master**
* **(Black Italic) – master**

## Notes

The lightest **Text** is designed to go until `wght` 55 (Extralight), whereas the lightest **Display** is designed to 20 (Thin). For the Variable font, we want the Thin—Extralight range for `opsz` Text to just remain the same. The way the (PE) sources are set up now, the "Text Thin" masters are really the *Extralight design*, but *numerically have `wght` 20* to avoid designspace distorions. From this follows:
- Text instance weights between "Thin" and Medium are remapped, so their weight actually matches the Display:
  - Text Light `wght` instead of 70: 47
  - Text REegular `wght` instead of 85: 74
  - e.g.: On the designed 55-70-85-100 range for Text those are steps of 33.33%; since we moved the master numerically to 20 but want to visually match the previous steps, reach the same looking values by: 20 + 0.33 * (100 - 20), and 20 + 0.66 * (100 - 20) respectively
- The source instances also contain "Display Extralight master" (+ Italic); these get extracted and cloned as masters that the VF designspace uses, so there are Display Extralight "sources" where there are Text Extralight sources.

When copying between versions (PE -> Arabic, Hebrew) pay attention to:
- UPM is bigger in Arabic, simply change the number from 2100 to 2700
- keep non-exporting glyphs’ Export flag off (Omega, Delta, mu, c.ka in Hebrew and Arabic)
