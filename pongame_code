//Variaveis bola:
let xbola = 300;
let ybola = 200;
let diametrob = 15;
let raiob = diametrob / 1;
let velocx = 6;
let velocy = 5;

//variaveis minha raquete (mrqt)
let xmrqt = 5;
let ymrqt = 150;
let largmrqt = 10;
let altmrqt = 90;
let velocmrqt = 10;

//variaveis raquete oponente (orqt)
let xorqt = 585;
let yorqt = 150;
let velocorqt;

//placar
let mponto = 0; //meus pontos
let oponto = 0; //pontos oponentes

//sons
let raquetada;
let ponto;
let trilhajogo;

function preload(){
  trilhajogo = loadSound("trilha.mp3");
  raquetada = loadSound("raquetada.mp3");
  ponto = loadSound("ponto.mp3");
}

function setup() {
  createCanvas(600, 400);
  trilhajogo.loop();
}

function draw() {
  background(10, 10, 80);
  criaplacar();
  criaBola();
  moveBola();
  colideBola();
  criaRqt(xmrqt, ymrqt);
  moveMrqt();
  criaRqt(xorqt, yorqt);
  multiplayer();
  rqtcollide(xmrqt, ymrqt);
  rqtcollide(xorqt, yorqt);
  //criaplacar();
  pontuacao();
  //enfeite();
}

function criaBola(){
  circle(xbola, ybola, diametrob);
}

function moveBola(){
  xbola += velocx;
  ybola += velocy;
}

function colideBola(){
  if (xbola + raiob > width || xbola - raiob < 0){
    velocx *= -1;
  }
  if (ybola + raiob > height || ybola - raiob < 0){
    velocy *= -1;
  }
}

function criaRqt(x, y){
  rect(x, y, largmrqt, altmrqt);
}

function moveMrqt(){
  if (keyIsDown(UP_ARROW)){
    ymrqt -= velocmrqt;
  }
  
  if (keyIsDown(DOWN_ARROW)){
    ymrqt += 10;
  }
}

function multiplayer(){
  if (keyIsDown(87)){
    yorqt -= 10;
  }
  
  if (keyIsDown(83)){
    yorqt += 10;
  }
}

function rqtcollide(x, y){
  colidiu =
  collideRectCircle(x, y, largmrqt, altmrqt, xbola, ybola, raiob);
  if(colidiu){
    velocx *= -1;
    raquetada.play();
  }
}

function moveOrqt(){
  velocorqt = ybola - yorqt - largmrqt / 2 - 30;
  yorqt += velocorqt;
}

function criaplacar(){
  stroke(3,0, 12)
  textAlign(CENTER);
  textSize(18);
  fill(color(100,100,150));
  rect(300, 0, 5, 600)
  fill(color(200,150,200));
  rect(180, 10, 40, 20);
  fill(255);
  text(mponto, 200, 26);
  fill(color(200,150,200));
  rect(380, 10, 40, 20);
  fill(255);
  text(oponto, 400, 26);
}

function pontuacao(){
  if (xbola + raiob > 599){
    mponto += 1;
    ponto.play();
  }
  if (xbola - raiob < 1){
    oponto += 1;
    ponto.play();
  }
}

function enfeite(){
  fill(color(30,30,255));
  rect(300, 0, 5, 600)
}
