const questions = [
  {
    question: "$\\mathbb{N}$ is a field.",
    answer: false
  }]

const container = document.getElementById("AMT4B1-container");
const scoreBox = document.getElementById("score-summary");

let answeredCount = 0;
let correctCount = 0;

const intro = document.createElement("intro")
intro.innerHTML = `<p><b>Note.</b>  When some symbols are not specified, it is understood that alphabets 
    ($x,y,z,\\dots$) represent vectors in an arbitrary vector space (capital letters $V,W,\\dots$) and 
    Greek letters ($\\alpha,\\beta,\\gamma,\\lambda,\\dots$) represent scalars in the underlying field. </p>`
container.appendChild(intro)


questions.forEach((q, i) => {
  const div = document.createElement("div");
  div.innerHTML = `
    <p><b>Q${i + 1}.</b> ${q.question}</p>
    <button style = "font-size: 1.1em; padding: 5px 14px;", id="true-${i}" onclick="checkAnswer(${i}, true)">True</button>
    <button style = "font-size: 1.1em; padding: 5px 14px;", id="false-${i}" onclick="checkAnswer(${i}, false)">False</button>
    <span id="feedback-${i}" style="min-width: 100px; margin-left: 30px;"></span>
  `;
  container.appendChild(div);
});

const savedAnswer = localStorage.getItem(`question-${i}`);
if (savedAnswer !== null) {
  checkAnswer(i, savedAnswer === 'true', true); // true = restoring
}


function checkAnswer(index, selected) {
  const correct = questions[index].answer;
  const feedback = document.getElementById(`feedback-${index}`);
  const trueBtn = document.getElementById(`true-${index}`);
  const falseBtn = document.getElementById(`false-${index}`);

  if (trueBtn.disabled || falseBtn.disabled) return; // prevent double-clicking

  // Disable buttons
  trueBtn.disabled = true;
  falseBtn.disabled = true;

  // Highlight the clicked button
  const selectedBtn = selected ? trueBtn : falseBtn;
  if (selected === correct) {
    selectedBtn.classList.add("correct");
  } else {
    selectedBtn.classList.add("wrong");
  }

  const isCorrect = selected === correct;
  feedback.innerHTML = isCorrect ? "(¦3[▓▓]" : "＼(・｀(エ)・)/ ";

  answeredCount++;
  if (isCorrect) correctCount++;

  // Show final score after last answer
  if (answeredCount === questions.length) {
    let grade;
    if (correctCount == questions.length) grade = 'Genius Level! I love you so matcha.';
    else if (correctCount >= questions.length-5) grade = 'So close! Give you a chocolatte.';
    else if (correctCount >= questions.length-20) grade = 'Good Job. Give you a cookie. Crooked Hillary.';
    else if (correctCount >= questions.length-30) grade = 'Masih memuaskan. Kasih satu nasi lemak.';
    else if (correctCount >= questions.length-50) grade = 'Need more practice!';
    else grade = 'Hello what happen? Habis lah!';
    scoreBox.innerHTML = `<div style="font-size: 1.5em; font-weight: bold; margin-top: 50px; margin-bottom: 50px;">
    You got ${correctCount} out of ${questions.length} correct. ${grade}
    </div>`
  }
}
