<script>
  let maxParticipants = {
      Hackathon: 3,
      Designathon: 3,
      Hardware: 2,
      Crossword: 2,
      Surprise: 2,
      "Group Discussion": 1,
      "Jr. Robotics": 1,
      "Paint 3D": 1,
      "Adobe Spark": 1,
      Minecraft: 1
  }
  let checkedEvents = [];
  let schoolFields = ['school-name', 'team-name', 'team-email', 'student-incharge-name', 'student-incharge-number']
  let participantFields = ['Name', 'Class', 'Email']
  let apiProps = {
    'school-name': 'schoolName',
    'team-name': 'teamName',
    'team-email': 'teamEmail',
    'student-incharge-name': 'studentIncharge',
    'student-incharge-number': 'studentInchargeNumber',
  }
  const addEvent = (event) => {
    checkedEvents = [...checkedEvents, event]
  }

  const removeEvent = (event) => {
    let index = checkedEvents.indexOf(event);
    if (index !== -1) {
      checkedEvents.splice(index, 1);
    }
    checkedEvents = checkedEvents 
  }

  const submitIndiForm = (type) => {
    let formData = {}
    formData["events"] = checkedEvents
    let errors = []
    schoolFields.forEach((f) => {
      if(document.getElementsByClassName(f)[0].value.trim().length !== 0) {
        formData[apiProps[f]] = document.getElementsByClassName(f)[0].value
      } else {
        let eventFullName = ''
        f.split('-').forEach(e => {
          eventFullName += `${e[0].toUpperCase()}${e.slice(1, e.length)} `
        })
        errors.push(`Please fill in ${eventFullName}`)
      }
    })
    if(errors.length === 0) {
      checkedEvents.forEach(ce => {
        for (let i=1; i<maxParticipants[ce]+1; i++) {
          let eventname = ''
          if(ce === 'Jr. Robotics') {
            eventname = 'jrrobotics' 
          } else {
            eventname = ce.toLowerCase().split(' ').join('')
          }
          let fieldName = `${eventname}P${i}`
          let participant = {}
          participantFields.forEach(pf => {
            let eventClassName = ce + '-' + (i) + '-' + pf
            let detailName = ''
            if(pf === 'Class') {
              detailName = 'cls'
            } else {
              detailName = pf.toLowerCase()
            }
            if(document.getElementsByClassName(eventClassName)[0].value.trim().length !== 0) {
              participant[detailName] = (document.getElementsByClassName(eventClassName)[0].value)
            } else {
              participant[detailName] = 'undefined'
            }
          })
          formData[fieldName] =  participant
        } 
      })
      // TODO: api post request
      console.log(formData)
      fetch('https://ts-reg-21.herokuapp.com/independent', {
          // Adding method type
          method: "POST",

          // Adding body or contents to send
          body: JSON.stringify(formData),

          // Adding headers to the request
          headers: {
            "Content-type": "application/json; charset=UTF-8",
          }
        }
      ).then(async(response) => {
          const resp = await response.json()
          console.log(resp)
        })
        .catch(err => {console.log(err)})
    } else {
      console.log("ERRORS")
      errors.forEach(err => console.log(err))
    }
  }

  window.addEventListener('click', (e) => {
      if(e.target.id === "indi-submit-button") {
        submitIndiForm('independent')
      } else if(e.target.checked === false) {
          if(checkedEvents.includes(e.target.value)) {
            removeEvent(e.target.value)
          } 
      } else if(e.target.checked === true) {
        addEvent(e.target.value)
      }
  })
</script>

<p>School Name</p>
<input type="text" placeholder="Amity International School, Sector-46" class="school-name">
<div class="inline">
<div>
  <p>Team Name</p>
  <input type="text" placeholder="Clubless" id="inline-input" style="width: 16.5vw;" class="team-name">
</div>
<div>
  <p>Team Email</p>
  <input type="text" placeholder="clubless@gmail.com" id="inline-input" class="team-email">
</div>
</div>
<div class="inline">
<div>
  <p>Student Incharge</p>
  <input type="text" placeholder="John Doe" id="inline-input" style="width: 16.5vw;" class="student-incharge-name">
</div>
<div>
  <p>Student Incharge Number</p>
  <input type="text" placeholder="+91 7070707070" id="inline-input" class="student-incharge-number">
</div>
</div>
<p>Choose Events</p>
<div class="checkboxes">
  <div class="left">
      <label for="checkid" style="word-wrap: break-word"><input id="checkbox-id" name="checkid"  type="checkbox" value="Hackathon" class="larger"/><span class="text">Hackathon</span></label><br>
      <label for="checkid" style="word-wrap: break-word"><input id="checkbox-id" name="checkid"  type="checkbox" value="Designathon" class="larger"/><span class="text">Designathon</span></label><br>
      <label for="checkid" style="word-wrap: break-word"><input id="checkbox-id" name="checkid"  type="checkbox" value="Crossword" class="larger"/><span class="text">Crossword</span></label><br>
  </div>
  <div class="left side">
      <label for="checkid" style="word-wrap: break-word"><input id="checkbox-id" name="checkid"  type="checkbox" value="Group Discussion" class="larger"/><span class="text">Group Discussion</span></label><br>
      <label for="checkid" style="word-wrap: break-word"><input id="checkbox-id" name="checkid"  type="checkbox" value="Surprise" class="larger"/><span class="text">Surprise</span></label><br>
      <label for="checkid" style="word-wrap: break-word"><input id="checkbox-id" name="checkid"  type="checkbox" value="Hardware" class="larger"/><span class="text">Hardware</span></label><br>
  </div>
  <div class="left side">
      <label for="checkid" style="word-wrap: break-word"><input id="checkbox-id" name="checkid"  type="checkbox" value="Jr. Robotics" class="larger"/><span class="text">Jr. Robotics</span></label><br>
      <label for="checkid" style="word-wrap: break-word"><input id="checkbox-id" name="checkid"  type="checkbox" value="Minecraft" class="larger"/><span class="text">Minecraft</span></label><br>
      <label for="checkid" style="word-wrap: break-word"><input id="checkbox-id" name="checkid"  type="checkbox" value="Adobe Spark" class="larger"/><span class="text">Adobe Spark</span></label><br>
  </div>
  <div class="right">
      <label for="checkid" style="word-wrap: break-word"><input id="checkbox-id" name="checkid"  type="checkbox" value="Paint 3D" class="larger"/><span class="text">Paint 3D</span></label><br>
  </div>
</div>

{#each checkedEvents as event}
  <p id="event-name">{event}</p>
  {#each [...Array(maxParticipants[event]).keys()] as index}
      <div class="inline">
          <div>
              <p>Participant {index+1} Name</p>
              <input type="text" placeholder="Jane Doe" id="inline-input" style="width: 12.5vw;" class={event + '-' + (index+1) + '-Name'}>
          </div>
          <div style="margin-left: -1vw">
              <p>Participant {index+1} Class</p>
              <input type="text" placeholder="XII" id="inline-input" style="width: 9vw;" class={event + '-' + (index+1) + '-Class'}>
          </div>
          <div style="margin-left: -1vw">
              <p>Participant {index+1} Email</p>
              <input type="text" placeholder="jane@gmail.com" id="inline-input" style="width: 12.9vw;" class={event + '-' + (index+1) + '-Email'}>
          </div>
      </div>
  {/each}
{/each}

{#if checkedEvents.length > 0}
<button id="indi-submit-button">Register</button>
{/if}

<style>
  p {
    font-size: 1vw;
    color: #16e16e
  }
  
  .inline {
    display: flex;
    flex-flow: row wrap;
    align-items: center;
  }

  #inline-input {
    margin-right: 2vw;
    width: 19.3vw;
  }

  input[type=text] {
    background-color: transparent;
    height: 2.2vw;
    border: 0.01vw white solid;
    font-size: 1.2vw;
    padding-left: 1vw;
    color: white;
    width: 39vw;
    border-radius: 3px;
    margin-top: -10%;
    margin-bottom: 1vw;
  }

  .checkboxes {
    display: flex;
    flex-flow: row wrap;
    align-items: center;
    margin-left: -0.5vw;
    margin-top: -0.5%;
    margin-bottom: 1.2vw;
  }

  .checkboxes label {
      font-size: 0.9vw;
  }

  .checkboxes .text {
      margin-left: -0.3vw;
  }

  input.larger {
      transform: scale(1.4);
      border: none;
      margin: 0.8vw;
  }

  [type="checkbox"]
  {
      vertical-align:middle;
  }

  .side {
      margin-left: 1vw;
  }

  .checkboxes .right {
      margin-left: 1vw;
      margin-top: -5vw;
  }

  #event-name {
      font-size: 1.5vw;
      margin-bottom: 0.5vw;
      color: white;
  }

  button {
    height: 2.5vw;
    width: 8vw;
    border: none;
    text-align: center;
    padding-left: 1vw;
    padding-right: 1vw;
    color: white;
    background-color: #00AF3B;
    font-size: 1.2vw;
    border-radius: 5px;
    margin-top: 3vh
  }

  button:hover {
    cursor: pointer;
  }
</style>