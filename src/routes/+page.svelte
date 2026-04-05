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

let randomSymptoms = getRandomItems(symptoms, 3);
let randomMedications = getRandomItems(medications, 2);
let randomCondition = getRandomItems(conditions, 1)[0];
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
        <li>{randomCondition}</li>
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
    }}>New Scenario
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
</style>