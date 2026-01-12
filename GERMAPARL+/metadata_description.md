# 1. Description of the Available Metadata

|  **Field name**                    | **Description**  |
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

| **Field name**              | **Description**  |
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

| **Field name**                    | **Description**                                                                                                              |
| --------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| **announcement**                  | A formal notification of information or events raised to the plenary (not always debated).                                             |
| **assumption**                    | A presumption or given premise used in a motion or debate; could refer to assumed facts to be debated.                                 |
| **briefing**                      | An informational presentation to members, not a decision item (e.g., government updates).                                              |
| **budget**                        | Discussions or decisions on budget matters; often part of budget committee or plenary sessions.                                        |
| **consultation**                  | Review or preparation of issues before full debate; consultation with committees or groups.                                            |
| **current_affairs**               | Debates or statements on topical issues of immediate public relevance.                                                                 |
| **debate**                        | Discussion by Members of Parliament on a topic or proposal.                                                                            |
| **election**                      | Formal election process within the Bundestag (e.g., electing the President of the Bundestag or Chancellor).                            |
| **government_declaration**        | A statement by the government (e.g., Chancellor) on policy or plans, often followed by debate.                                         |
| **interrogation**                 | Formal questioning of government ministers or representatives (parliamentary scrutiny).                                                |
| **motion**                        | A formal proposal submitted by a Member or group of Members for debate or decision.                                                    |
| **oath**                          | Swearing in of Members or office holders (e.g., at the start of a legislative period).                                                 |
| **objection**                     | A formal objection to an agenda item or decision, potentially affecting adoption of items.                                             |
| **opening**                       | The start of a plenary session (procedural item).                                                                                      |
| **point_of_order**                | A procedural challenge raised during a sitting to question whether rules of procedure are being followed.                              |
| **procedure**                     | Items related to internal Bundestag processes and rules.                                                                               |
| **question_time**                 | A scheduled session in which Members ask questions to government representatives.                                                      |
| **questioning_of_the_government** | A specific form of interrogation or questioning directed at the government’s actions.                                                  |
| **recent_issues**                 | Topics of recent political or societal importance flagged for discussion.                                                              |
| **report**                        | Presentation or discussion of reports from committees, commissions, or government bodies.                                              |
| **resolution**                    | A formal decision or position adopted by the Bundestag.                                                                                |
| **rules_of_procedure**            | Materials or items concerning the parliamentary rules themselves.                                                                      |
| **section**                       | A structural subdivision in documents or protocols.                                                                                    |
| **urgent_question**               | A question raised on an urgent matter requiring timely government response (similar to “current affairs”).                             |
| **<empty>**                       | Not known.                                                                                  |

### Role

|  **Field name**                    | **Description**  |
|-----------|-------------|
| presidency | President of the session |
| mp | Member of the parliament |
| government | Member of the government |
| parliamentary_commissioner | Parliamentary commissioner |
| misc | Miscellaneous |
| federal_council | Member of the Federal Council |

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
