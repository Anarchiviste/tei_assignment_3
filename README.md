# TEI ODD stylesheet for anglo-saxon fanzine encoding.

Here is the link to my two previous assignment.
- https://github.com/Anarchiviste/evalXML.git
- https://github.com/Anarchiviste/TEI-assignment2.git

### IA statement
This time I used some generative IA to debug a problem with schematron.

## Repo organisation

- **Transcription** : directory with the transcription of the 3 zines.
  - DIY_guide.md
  - The_president.md
  - Why_zine.md
- **XML** : directory with all the 3 encoded tei xml files.
  - DIY_Guide_Prevent_Sexual_Assault.xml
  - The_President_is_Gone.xml
  - Why_Zine_Work.xml
- **Zine img** : directory with all the pdf of the 3 zines.
  - PRESGONE ONLINE FINAL_2_text.pdf
  - diy-guide-prevent-sexual-assault.pdf
  - why_zine_work.pdf
- **out** : directory for outputting the relaxng schema
  - tei_zine_minimal.rng
- tei_zine_minimal.html : the schema documentation for the rng
- tei_zine_minimal.odd : the master file that produce the rng and html output
