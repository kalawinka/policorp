# Downloaded data description 
Selected datasets can be downloaded freely in JSON format
**Section 1** provides a detailed description of the fields in the downloaded dataset. 
**Section 2** provides a detailed description of the fields in the text_raw field. 
## 1.	Fields description
<table>
<tbody>
<tr>
<td width="112">
<p><strong>field</strong></p>
</td>
<td width="468">
<p><strong>description</strong></p>
</td>
</tr>
<tr>
<td width="112">
<p>agenda_id</p>
</td>
<td width="468">
<p>Internal unique ID for each agenda within the session</p>
</td>
</tr>
<tr>
<td width="112">
<p>speech_id</p>
</td>
<td width="468">
<p>Internal unique ID for each speech contribution&nbsp; within the agenda</p>
</td>
</tr>
<tr>
<td width="112">
<p>speaker_id</p>
</td>
<td width="468">
<p>Unique speaker ID. Corresponds with the speaker ID from the database of <a href="https://www.bundestag.de/services/opendata">German Parliament Members</a>.</p>
</td>
</tr>
<tr>
<td width="112">
<p>party_id</p>
</td>
<td width="468">
<p>Internal unique ID for each party</p>
</td>
</tr>
<tr>
<td width="112">
<p>legislativePeriod</p>
</td>
<td width="468">
<p>The legislative period</p>
</td>
</tr>
<tr>
<td width="112">
<p>sessionno</p>
</td>
<td width="468">
<p>The session number</p>
</td>
</tr>
<tr>
<td width="112">
<p>date</p>
</td>
<td width="468">
<p>The date of the session</p>
</td>
</tr>
<tr>
<td width="112">
<p>source_file</p>
</td>
<td width="468">
<p>Link to the source file on the website of German Parliament</p>
</td>
</tr>
<tr>
<td width="112">
<p>description</p>
</td>
<td width="468">
<p>Description of the agenda</p>
</td>
</tr>
<tr>
<td width="112">
<p>agenda_type</p>
</td>
<td width="468">
<p>Type of the agenda</p>
</td>
</tr>
<tr>
<td width="112">
<p>agenda_nr</p>
</td>
<td width="468">
<p>Number of the agenda in the session</p>
</td>
</tr>
<tr>
<td width="112">
<p>name</p>
</td>
<td width="468">
<p>Full name of the speaker</p>
</td>
</tr>
<tr>
<td width="112">
<p>role</p>
</td>
<td width="468">
<p>Role of the speaker, e.g., presidency, government, member of the parliament, etc.</p>
</td>
</tr>
<tr>
<td width="112">
<p>position</p>
</td>
<td width="468">
<p>Position of the speaker</p>
</td>
</tr>
<tr>
<td width="112">
<p>party</p>
</td>
<td width="468">
<p>Party of the speaker</p>
</td>
</tr>
<tr>
<td width="112">
<p>type</p>
</td>
<td width="468">
<p>Type of speech contribution.</p>
<p>Can be speech, interjection, or call to order.</p>
</td>
</tr>
<tr>
<td width="112">
<p>topic</p>
</td>
<td width="468">
<p>Topic of the speech, derived with the <a href="https://huggingface.co/chkla/parlbert-topic-german">ParlBERT-Topic-German</a> model.<br /> Includes an additional topic, <strong>&ldquo;Presidency Action&rdquo;,</strong> which flags speeches by the session president that contain session moderation.</p>
</td>
</tr>
<tr>
<td width="112">
<p>text_raw</p>
</td>
<td width="468">
<p>Transcript of the speech of the speaker.</p>
<p>Has a nested structure.</p>
</td>
</tr>
</tbody>
</table>

## 2. The	text_raw field description
The **text_raw** field contains the transcript of a single speaker's speech contribution and has a nested structure. Each speech contribution is divided into individual sentences. In the data format, each sentence is represented as a single element within the data structure, along with its type and any available annotations. 

<table width="580">
<tbody>
<tr>
<td width="70">
<p><strong>field</strong></p>
</td>
<td colspan="2" width="510">
<p><strong>description</strong></p>
</td>
</tr>
<tr>
<td width="70">
<p>text</p>
</td>
<td colspan="2" width="510">
<p>Sentence of a speech contribution</p>
</td>
</tr>
<tr>
<td rowspan="3" width="70">
<p>type</p>
</td>
<td width="170">
<p>speech</p>
</td>
<td width="340">
<p>Part of speech contribution</p>
</td>
</tr>
<tr>
<td width="170">
<p>call to order</p>
</td>
<td width="340">
<p>Call to order</p>
</td>
</tr>
<tr>
<td width="170">
<p>interjection</p>
</td>
<td width="340">
<p>Interjection</p>
</td>
</tr>
<tr>
<td rowspan="6" width="70">
<p>ner</p>
</td>
<td colspan="2" width="510">
<p>Contains the output of the <a href="https://huggingface.co/flair/ner-german">German NER in Flair</a> + additional label Party</p>
<p>Has nested structure:</p>
</td>
</tr>
<tr>
<td width="170">
<p><em><strong>field</strong></em></p>
</td>
<td width="340">
<p><em><strong>description</strong></em></p>
</td>
</tr>
<tr>
<td width="170">
<p>label</p>
</td>
<td width="340">
<p>Named entity description</p>
</td>
</tr>
<tr>
<td width="170">
<p>text</p>
</td>
<td width="340">
<p>Named entity text</p>
</td>
</tr>
<tr>
<td width="170">
<p>start_pos</p>
</td>
<td width="340">
<p>Start position of the named entity in the text</p>
</td>
</tr>
<tr>
<td width="170">
<p>end_pos</p>
</td>
<td width="340">
<p>End position of the named entity in the text</p>
</td>
</tr>
<tr>
<td width="70">
<p>legal_ner</p>
</td>
<td colspan="2" width="510">
<p>Contains the output of the <a href="https://huggingface.co/flair/ner-german-legal">NER for German Legal Text in Flair</a> + additional label Party</p>
<p>Has nested structure:</p>
</td>
</tr>
<tr>
<td rowspan="5" width="70">
<p>&nbsp;</p>
</td>
<td width="170">
<p><em><strong>field</strong></em></p>
</td>
<td width="340">
<p><em><strong>description</strong></em></p>
</td>
</tr>
<tr>
<td width="170">
<p>label</p>
</td>
<td width="340">
<p>Named entity description</p>
</td>
</tr>
<tr>
<td width="170">
<p>text</p>
</td>
<td width="340">
<p>Named entity text</p>
</td>
</tr>
<tr>
<td width="170">
<p>start_pos</p>
</td>
<td width="340">
<p>Start position of the named entity in the text</p>
</td>
</tr>
<tr>
<td width="170">
<p>end_pos</p>
</td>
<td width="340">
<p>End position of the named entity in the text</p>
</td>
</tr>
</tbody>
</table>
