
<script>
  export const rows = ["Times\\Date", "Breakfast", "Lunch", "Teatime", "Bedtime"]
</script>

<style>
  div.flex {
    display: flex;
    
  }

  div.flex-rows {
    display: flex;
    /* gap: 8px; */
    flex-direction: column;
  }

  textarea {
    background-color: transparent;
    border: 0;
    border-bottom: 1px solid gray;
  }

  input {
    border: 0;
    border-bottom: 1px solid gray;
    padding: 6px;
    background-color: transparent;
  }
  div.heading {
    flex: 2;
  }

  div.patient {
    /* width: 100%; */
    flex: 1;
    border: 1px solid green;
    padding: 4px;
    background-color: lightgreen;
  }
  label {
    display: block;
    font-weight: bold;
  }

  .forCarerUse label, .forCarerUse input {
    display: inline-block;
    width: auto;
  }

  textarea, input {
    width: 100%;
  }
  div.codes {
    font-size: 12px;
    background-color: lightcoral;
    padding: 4px;
    margin-bottom: -4px;
    margin-left: -4px;
    margin-right: -4px;
  }

  div.medicalDetails {
    background-color: lightgreen;
    padding: 4px;
    flex: 1;
  }
  div.forCarerUse {
    flex: 1;
    background-color: lightcoral;
    padding: 4px;
  }
  div.forCarerUse > div {
    min-height: 30px;
  }

  table.timesDates {
    width: 100%;
    border-collapse: collapse;
  }
  table.timesDates, table.timesDates td {
    border: 1px solid gray;
    height: 60px;
  }
  td.th {
    width: 86px;
  }
  div.timesDates {
    background-color: lightcoral
  }

  table.comments {
    width: 100%;
    height: 100%;
  }

  table.comments tr:first-child {
    height: 30px;
    background-color: lightgreen
  }
  table.comments tr:last-child {
    height: 100%;
  }

  table.comments, table.comments td, table.comments th  {
    border-collapse: collapse;
    border: 1px solid gray;

  }
  
</style>

<div class="flex-rows landscape">
  <div class="flex">
    <div class="heading">
      <h1>Medicines Administration Record for Domiciliary Care - Medicines NOT in a Monitored Dosage System </h1>
    </div>
    <div class="patient">
      <div>
        <label for="patientName">Patient Name:</label>
        <input id="patientName" type="text"/>
      </div>
      <div>
        <label for="address">Address:</label>
        <textarea id="address" rows="3">

        </textarea>
      </div>
      <div>
        <label for="dob">Date of Birth:</label>
        <input type="text" id="dob"/>
      </div>
    </div>
  </div>

  <div class="flex">
    <div class="medicalDetails">
      <h3><i>Medicine Details - complete below or pharmacy to attach label</i></h3>
      <div>
        <label for="medicineName">Medicine Name:</label>
        <input id="medicineName" />
      </div>
      <div>
        <label for="strength">Strength:</label>
        <input id="strength" />
      </div>
      <div>
        <label for="instructions">Instructions:</label>
        <textarea id="instructions" rows="4" />
      </div>
      <div class="codes">Codes: <b>R</b> = Refused, <b>F</b> = Family administer, <b>O</b> = Other (please provide details on reverse)</div>
    </div>
    <div class="forCarerUse">
      <h3><i>For Carer Use</i></h3>
      <div>
        <label for="marChecked">Mar checked against medicine received:&nbsp;</label>
        
        <input id="marCheckedYes" type="radio" name="marChecked" value="yes" />
        <label for="marCheckedYes">Yes</label>
        <input id="marCheckedNo" type="radio" name="marChecked" value="no" />
        <label for="marCheckedNo">No</label>
      </div>

      <div>
        <label for="officeInformed">Office informed if change in medication:&nbsp;</label>
        
        <input id="officeInformedYes" type="radio" name="officeInformed" value="yes" />
        <label for="officeInformedYes">Yes</label>
        <input id="officeInformedNo" type="radio" name="officeInformed" value="no" />
        <label for="officeInformedNo">No</label>
      </div>
      <div style="display: flex; align-items: center;">
        <label for="from" style="flex: 0 0 auto;">Form covers period from </label>
        <input style="flex: 1 1 25%; width: 20px;" id="from" type="text">
        <label for="to">to</label>
        <input style="flex: 1 1 25%; width: 20px;" id="to" type="text">

      </div>
      <span><i>Name and signature of transcriber if medicine details completed by care provider</i></span>
      <div class="flex" style="align-items: center">
        <label for="transcriberName">Name:</label>
        <input style="flex-grow: 1" id="transcriberName" type="text"/>
      </div>
      <div class="flex" style="align-items: center">
        <label for="transcriberSignature">Signature:</label>
        <input style="flex-grow: 1" id="transcriberSignature"/>
        <label for="transcriberSignatureDate">Date:</label>
        <input id="transcriberSignatureDate" />
      </div>

    </div>
  </div>

  <div class="timesDates">
    <table class="timesDates">
      {#each rows as row}
        <tr>
          <td class="th">{row}</td>
          {#each {length: 31} as _, i}
            <td></td>
          {/each}
        </tr>
      {/each}
    </table>
  </div>
</div>
<div class="portrate">
  <table class="comments">
    <tr>
      <th>
        Date
      </th>
      <th>
        Comments, Incidents, Errors
      </th>
    </tr>
    <tr>
      <td>

      </td>
      <td>

      </td>
    </tr>
  </table>
  <div>
    <h2>Who to contact in case of query / incident</h2>
    <p>If worried about about patient's condition, or following administration error contact:</p>
    <ol>
      <li>Patient's own GP</li>
      <li>Out of hours service (111)</li>
      <li>Safeguarding team at OCC (if medicine administration error) on 0845 0507 666</li>
    </ol>
    <p>For patient specific enquiries about this medication</p>
    <ol>
      <li>Dispensing pharmacy (telephone number on medical label)</li>
    </ol>
    <p>
      For general medicine query - e.g. is this a steroid?, does it contain penicillin?
    </p>
    <ol>
      <li>Dispening pharmacy (if open)</li>
      <li>Any community pharmacy (office should hold contact numbers for pharmacies open late evenings and weekends)</li>
    </ol>
  </div>
</div>