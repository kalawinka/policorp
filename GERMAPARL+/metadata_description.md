# 1. Description of the Available Metadata

| Field | Description |
|------|-------------|
| agenda_id | Internal unique ID for each agenda within the session |
| speech_id | Internal unique ID for each speech contribution within the agenda |
| speaker_id | Unique speaker ID. Corresponds with the speaker ID from the database of German Parliament Members |
| party_id | Internal unique ID for each party |
| legislativeperiod | The legislative period |
| sessionno | The session number |
| date | The date of the session |
| source_file | Link to the source file on the website of the German Parliament |
| description | Description of the agenda |
| agenda_type | Type of the agenda |
| agenda_nr | Number of the agenda in the session |
| name | Full name of the speaker |
| role | Role of the speaker (e.g., presidency, government, member of parliament) |
| position | Position of the speaker |
| party | Party of the speaker |
| topic | Topic of the speech, derived using the ParlBERT-Topic-German model. Includes an additional topic, **“Presidency Action”**, flagging session moderation by the session president |
| text_raw | Transcript of the speech of the speaker (nested structure) |

---

# 2. Search Functionality

This section explains the functionality of the advanced search feature.

- **Subsection 2.1** lists the available search fields.  
- **Subsection 2.2** lists fields with fixed values and explains their meanings.  
  To achieve optimal search results, please use the terms provided in Subsection 2.2 when querying fields with fixed values.

## 2.1 List of the Search Fields

- name  
- party  
- text_raw  
- description  
- agenda_type  
- role  
- type  
- topic  
- legislativeperiod  
- sessionno  
- date  

## 2.2 Description of Fields with Fixed Values

### Party

| Field name | Description |
|-----------|-------------|
| AfD | Alternative für Deutschland |
| BP | Bayernpartei |
| CDU | Christlich Demokratische Union Deutschlands |
| CSU | Christlich-Soziale Union |
| Die PARTEI | Die Partei für Arbeit, Rechtsstaat, Tierschutz, Elitenförderung und basisdemokratische Initiative |
| DP | Die Deutsche Partei |
| DRP | Die Deutsche Reichspartei |
| DSU | Deutsche Soziale Union |
| FDP | Freie Demokratische Partei |
| FDV | Freie Deutsche Volkspartei |
| FVP | Freie Volkspartei |
| GB/BHE | Gesamtdeutsche Block/Bund der Heimatvertriebenen und Entrechteten |
| SPD | Sozialdemokratische Partei Deutschlands |
| GDP | Die Gesamtdeutsche Partei |
| Bündnis 90/Die Grünen | Bündnis 90/Die Grünen |
| LKR | Liberal-Konservative Reformer |
| Schill-Partei | Partei Rechtsstaatlicher Offensive |
| PDS | Partei des Demokratischen Sozialismus |
| SSW | Südschleswigsche Wählerverband |
| WAV | Wirtschaftliche Aufbau-Vereinigung |
| Zentrum | Deutsche Zentrumspartei |
| not known | Party affiliation is not known |
| DKP-DRP | Deutsche Konservative Partei – Deutsche Rechtspartei |
| DIE LINKE | DIE LINKE |
| BSW | Bündnis Sahra Wagenknecht |
| CDU/CSU | CDU/CSU-Bundestagsfraktion |
| DKP | Deutsche Kommunistische Partei |
| KPD | Kommunistische Partei Deutschlands |
| non-party | Not affiliated to any party |

### Agenda Type

| Field name |
|-----------|
| announcement |
| assumption |
| briefing |
| budget |
| consultation |
| current_affairs |
| debate |
| election |
| government_declaration |
| interrogation |
| motion |
| oath |
| objection |
| opening |
| point_of_order |
| procedure |
| question_time |
| questioning_of_the_government |
| recent_issues |
| report |
| resolution |
| rules_of_procedure |
| section |
| unknown |
| urgent_question |

### Role

| Field name | Description |
|-----------|-------------|
| presidency | President of the session |
| mp | Member of the parliament |
| government | Member of the government |
| parliamentary_commissioner | Parliamentary commissioner |
| misc | Miscellaneous |
| federal_council | Member of the Federal Council |

### Type

| Field name | Description |
|-----------|-------------|
| speech | Part of a speech contribution |
| call to order | Call to order |
| interjection | Interjection |

### Topic

| Field name |
|-----------|
| Agriculture |
| Public |
| Domestic |
| Culture |
| Defense |
| Labor |
| Civil |
| Macroeconomics |
| Technology |
| Law |
| International |
| Government |
| Foreign |
| Transportation |
| Environment |
| Immigration |
| Social |
| Energy |
| Health |
| Housing |
| Education |
| Presidency Action |

### Date

- **Format:** `yyyy-mm-dd`

---

# 3. Fields Available in the Downloaded Data

Selected datasets can be downloaded freely in **JSON** format.

- **Subsection 3.1** provides a list of the available metadata fields.
- **Subsection 3.2** provides a description of the nested field `text_raw` 

## 3.1	List of the available metadata fields

- agenda_id 
- speech_id 
- speaker_id 
- party_id 
- legislativeperiod 
- sessionno 
- date 
- source_file 
- description 
- agenda_type 
- agenda_nr 
- name 
- role 
- position
- party 
- topic 
- text_raw 

## 3.2 `text_raw` Field Description

The `text_raw` field contains the transcript of a single speaker’s speech contribution and has a nested structure.  
Each speech contribution is divided into individual sentences. Each sentence is represented as a single element along with its type and any available annotations.

### `text_raw` Fields

| Field | Description |
|------|-------------|
| text | Sentence of a speech contribution |
| type | See Section 2.1 |
| ner | Output of German NER in Flair + additional label **Party** (nested structure) |
| legal_ner | Output of NER for German legal text in Flair + additional label **Party** (nested structure) |

### `ner` and `legal_ner` Fields

| Field name | Description |
|-----------|-------------|
| label | Named entity description |
| text | Named entity text |
| start_pos | Start position of the named entity in the text |
| end_pos | End position of the named entity in the text |
