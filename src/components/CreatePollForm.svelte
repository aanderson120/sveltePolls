<script>
  import Button from "../shared/Button.svelte";

  let fields = { question: "", answerA: "", answerB: "" };
  let errors = { question: "", answerA: "", answerB: "" };
  let valid = false;

  const sumbitHandler = () => {
    valid = true;

    //validate question
    if (fields.question.trim().length < 5) {
      valid = false;
      errors.question = "Question must be at least 5 characters long.";
    } else {
      errors.question = "";
    }
    //validate answer A
    if (fields.answerA.trim().length < 1) {
      valid = false;
      errors.answerA = "Answer A cannot be empty.";
    } else {
      errors.answerA = "";
    }
    //validate answer B
    if (fields.answerB.trim().length < 1) {
      valid = false;
      errors.answerB = "Answer A cannot be empty.";
    } else {
      errors.answerB = "";
    }

    if (valid) {
      console.log(valid, fields);
    }
  };
</script>

<form on:submit|preventDefault={sumbitHandler}>
  <div class="form-field">
    <label for="question">Poll Question:</label>
    <input type="text" id="question" bind:value={fields.question} />
    <div class="error">{errors.question}</div>
  </div>
  <div class="form-field">
    <label for="answer-a">Answer A:</label>
    <input type="text" id="answer-a" bind:value={fields.answerA} />
    <div class="error">{errors.answerA}</div>
  </div>
  <div class="form-field">
    <label for="answer-b">Answer B:</label>
    <input type="text" id="answer-b" bind:value={fields.answerB} />
    <div class="error">{errors.answerB}</div>
  </div>
  <Button type="secondary" flat={true}>Add Poll</Button>
</form>

<style>
  form {
    width: 400px;
    margin: 0 auto;
    text-align: center;
  }
  .form-field {
    margin: 18px auto;
  }
  input {
    height: 25px;
    width: 100%;
    border-radius: 6px;
    border: none;
  }
  label {
    margin: 10px auto;
    text-align: left;
  }
  .error {
    font-weight: bold;
    font-size: 12px;
    color: #A81532;
  }
</style>
