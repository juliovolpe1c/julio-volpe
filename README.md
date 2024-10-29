let campoIdade;
let campoFantasia;
let campoAventura;

function setup() {
  createCanvas(800, 400);
  createElement("h2", "Recomendador de filmes");
  createSpan("idade:");
  campoIdade = createInput("10");
  campoFantasia = createCheckbox("Gosta de terror");
  campoAventura = createCheckbox("Gosta de suspense?");
}

function draw() {
  background("black");
  let idade = campoIdade.value();
  let gostaDeFantasia = campoFantasia.checked();
  let gostaDeAventura = campoAventura.checked();
  let recomendacao = geraRecomendacao(idade, gostaDeFantasia, gostaDeAventura);

  fill(color(150, 150, 150));
  textAlign(CENTER, CENTER);
  textSize(38);
  text(recomendacao, width / 2, height / 2);
}

function geraRecomendacao(idade, gostaDeFantasia, gostaDeAventura) {
  if (idade >= 10) {
    if (idade >= 14) {
      return "Coraline e o Mundo Secreto ";
    } else {
      if (idade >= 12) {
        if(gostaDeFantasia || gostaDeAventura) {
          return "Pacto Secreto.";          
        } else{
         return "homem aranha";
        }
      } else {
        if (gostaDeFantasia) {
          return "A Noiva-Cadáver";
        } else {
          return "harry poter";
        }
      }
    }
  } else {
    if (gostaDeFantasia) {
      return "Pânico na floresta";
    } else {
      return "O feitiço do tempo";
    }
  }
}
