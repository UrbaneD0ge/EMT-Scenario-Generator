<script>
import content from '$lib';
let symptoms = content.symptoms;
let medications = content.medications;
let conditions = content.conditions;

function getRandomItems(arr, count) {
  const copy = [...arr];
  const selected = [];
  while (selected.length < count && copy.length) {
    const index = Math.floor(Math.random() * copy.length);
    selected.push(copy.splice(index, 1)[0]);
  }
  return selected;
}

let numberOfSymptoms = Math.floor(Math.random() * 3) + 1;
let numberOfConditions = Math.floor(Math.random() * 2) + 1;
let numberOfMedications = Math.floor(Math.random() * 3) + 1;

let randomSymptoms = getRandomItems(symptoms, numberOfSymptoms);
let randomCondition = getRandomItems(conditions, numberOfConditions);
let randomMedications = getRandomItems(medications, numberOfMedications);
</script>

<main>

    <h4>Patient presents with the following symptoms:</h4>
    <ul>
        {#each randomSymptoms as symptom}
        <li>{symptom}</li>
        {/each}
    </ul>

    <h4>Patient informs you they have had these conditions:</h4>
    <ul>
        {#each randomCondition as condition}
        <li>{condition}</li>
        {/each}
    </ul>

    <div>

        <h4>Patient takes the following medications:</h4>

        <ul>
            {#each randomMedications as medication}
            <li>{medication}</li>
            {/each}
        </ul>

    </div>

<button onclick={() => {
        location.reload();
    }}><b>New Scenario</b>
</button>

</main>


<style>
    main {
        padding: 20px;
        font-family: Arial, Helvetica, sans-serif;
    }

  ul {
      list-style-type: disc;
    }

    h4, ul {
    font-size: 2em;
  }

    button {
        background-color: midnightblue;
        color: white;
        border: none;
        border-radius: 20px;
        font-size: 1.5em;
        padding: 10px 20px;
        margin-top: 20px;
        cursor: pointer;
    }

    button:hover {
        background-color: rgb(0, 0, 74);
    }

    @media (max-width: 768px) {
        h4, ul {
            font-size: 1.2em;
        }

        button {
            font-size: 1em;
            padding: 8px 16px;
        }
    }
</style>