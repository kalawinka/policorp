# 1. Description of the Available Metadata

|  **Field name**                    | **Description**  |
|------|-------------|
| session_id | Internal unique ID for each session |
| speech_id | Internal unique ID for each speech contribution within the agenda |
| speaker_id | Unique speaker ID. Corresponds with the speaker ID from the database of German Parliament Members |
| party_id | Internal unique ID for each party |
| legislativeperiod | The legislative period |
| sessionno | The session number |
| date | The date of the session |
| source_file | Link to the source file |
| name | Full name of the speaker |
| role | Role of the speaker (e.g., presidency, government, member of parliament) |
| party | Party of the speaker |
| topic | Topic of the speech, derived using the ParlBERT-Topic-German model. Includes an additional topic, **“Presidency Action”**, flagging session moderation by the session president |
|state| Name of the federal state |
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
- state 
- text_raw  
- role  
- type  
- topic  
- legislativeperiod  
- sessionno  
- date  

## 2.2 Description of Fields with Fixed Values

### Party

| **Field name**              | **Description**  |
|-----------|-------------|
|--------|------|
| AfD | Alternative für Deutschland |
| CDU | Christlich Demokratische Union Deutschlands |
| CSU | Christlich-Soziale Union |
| DIE LINKE | DIE LINKE |
| Die PARTEI | Die Partei für Arbeit, Rechtsstaat, Tierschutz, Elitenförderung und basisdemokratische Initiative |
| DP | Die Deutsche Partei |
| FDP | Freie Demokratische Partei |
| SPD | Sozialdemokratische Partei Deutschlands |
| Bündnis 90/Die Grünen | Bündnis 90/Die Grünen |
| LKR | Liberal-Konservative Reformer |
| Schill-Partei | Partei Rechtsstaatlicher Offensive |
| non-party |  |
| FW | Freie Wähler |
| BIW | Bürger in Wut |
| BMV | Bürger für Mecklenburg-Vorpommern |
| BfTh | Bürger für Thüringen |
| BD | Bündnis Deutschland |
| DVU | Deutsche Volksunion |
| FAMILIE | Familien-Partei Deutschlands |
| FDVP | Freiheitliche Deutsche Volkspartei |
| Graue Panther | Die Grauen – Graue Panther |
| NPD | Nationaldemokratische Partei Deutschlands |
| ÖDP | Ökologisch-Demokratische Partei |
| Piraten | Piratenpartei Deutschland |
| REP | Die Republikaner |
| Regenbogen | Regenbogen – Für eine neue Linke |
| SSW | Südschleswigscher Wählerverband |
| M.R.F. | Gruppe Magnitz, Runge, Felgenträger |
| L.F.M. | Gruppe Löhmann, Felgenträger, Magnitz |


### Role

|  **Field name**                    | **Description**  |
|-----------|-------------|
| presidium | President of the session |
| mp | Member of the parliament |
| government | Member of the government |
| other | Miscellaneous |


### Type

|  **Field name**                    | **Description**  |
|-----------|-------------|
| speech | Part of a speech contribution |
| call to order | Call to order |
| interjection | Interjection |

### Topic

| **Field name**|
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

- session_id 
- speech_id 
- speaker_id 
- party_id 
- legislativeperiod 
- sessionno 
- date 
- source_file 
- name 
- role 
- position
- party 
- topic
- state 
- text_raw 

## 3.2 `text_raw` Field Description

The `text_raw` field contains the transcript of a single speaker’s speech contribution and has a nested structure.  
Each speech contribution is divided into individual sentences. Each sentence is represented as a single element along with its type and any available annotations.

### `text_raw` Fields

|  **Field name**                    | **Description** |
|------|-------------|
| text | Sentence of a speech contribution |
| type | See Section 2.1 |
| ner | Output of German NER in Flair + additional label **Party** (nested structure) |
| legal_ner | Output of NER for German legal text in Flair + additional label **Party** (nested structure) |

### `ner` and `legal_ner` Fields

|  **Field name**                    | **Description**  |
|-----------|-------------|
| label | Named entity description |
| text | Named entity text |
| start_pos | Start position of the named entity in the text |
| end_pos | End position of the named entity in the text |
