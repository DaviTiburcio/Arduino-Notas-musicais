int leds[] = {2, 3, 4, 5, 6, 7, 8, 9, 10};
int botaoPin = 12;
int buzzerPin = 11;
int configuracao = 0;

int DO = 262;
int RE = 294;
int MI = 330;
int FA = 349;
int SOL = 392;
int LA = 440;
int SI = 494;
int E = MI;

void tocarMusica(int musica) {
  int tempoLongo = 500;
  int tempoMuitoLongo = 1000;

  if (musica == 1) {
    // Megalovania
    acenderLedSincronizado(0, 294, 125);  // D4
    acenderLedSincronizado(0, 294, 125);  // D4
    acenderLedSincronizado(1, 587, 250);  // D5
    acenderLedSincronizado(2, 440, 250);  // A4
    acenderLedSincronizado(3, 415, 125);  // Ab4
    acenderLedSincronizado(4, 392, 250);  // G4
    acenderLedSincronizado(5, 349, 250);  // F4
    acenderLedSincronizado(6, 294, 125);  // D4
    acenderLedSincronizado(7, 349, 125);  // F4
    acenderLedSincronizado(8, 392, 125);  // G4
    acenderLedSincronizado(0, 261, 125);  // C4 (middle)
    acenderLedSincronizado(0, 261, 125);  // C4 (middle)
    acenderLedSincronizado(0, 261, 125);  // C4 (middle)
    acenderLedSincronizado(0, 261, 125);  // C4 (middle)
    acenderLedSincronizado(1, 587, 250);  // D5
    acenderLedSincronizado(2, 440, 375);  // A4
    acenderLedSincronizado(3, 415, 125);  // Ab4
    acenderLedSincronizado(4, 392, 250);  // G4
    acenderLedSincronizado(5, 349, 250);  // F4
    acenderLedSincronizado(6, 294, 125);  // D4
    acenderLedSincronizado(7, 349, 125);  // F4
    acenderLedSincronizado(8, 392, 125);  // G4
    acenderLedSincronizado(0, 247, 125);  // B3
    acenderLedSincronizado(0, 247, 125);  // B3
    acenderLedSincronizado(1, 587, 250);  // D5
    acenderLedSincronizado(2, 440, 375);  // A4
    acenderLedSincronizado(3, 415, 125);  // Ab4
    acenderLedSincronizado(4, 392, 250);  // G4
    acenderLedSincronizado(5, 349, 250);  // F4
    acenderLedSincronizado(6, 294, 125);  // D4
    acenderLedSincronizado(7, 349, 125);  // F4
    acenderLedSincronizado(8, 392, 125);  // G4
  } else if (musica == 2) {
    // Jingle Bells
    acenderLedSincronizado(0, E, tempoLongo);  
    acenderLedSincronizado(0, E, tempoLongo);
    acenderLedSincronizado(0, E, tempoLongo);
    acenderLedSincronizado(1, SOL, tempoLongo);
    acenderLedSincronizado(2, DO, tempoLongo);
    acenderLedSincronizado(3, RE, tempoLongo);
    acenderLedSincronizado(4, E, tempoLongo);
    acenderLedSincronizado(5, E, tempoLongo);
    acenderLedSincronizado(6, E, tempoLongo);
    acenderLedSincronizado(7, SOL, tempoLongo);
    acenderLedSincronizado(8, DO, tempoLongo);
    acenderLedSincronizado(0, RE, tempoLongo);
    acenderLedSincronizado(1, E, tempoMuitoLongo);
  }
  
	else if (musica == 4) {
int melodia[] = {262, 262, 392, 392, 440, 440, 392, 349, 349, 330, 330, 294, 294, 262};
for (int i = 0; i < 14; i++) {
      acenderLedSincronizado(i % 9, melodia[i], 500);
    }
}

  else if (musica == 3) {
    // Outra música natalina (We Wish You a Merry Christmas ou outra)
    int melodiaNatalina[] = {262, 262, 294, 294, 330, 330, 294, 349, 349, 330, 330, 294, 262};
    for (int i = 0; i < 13; i++) {
      acenderLedSincronizado(i % 9, melodiaNatalina[i], 500);
    }
  }
  noTone(buzzerPin);
}

void acenderLedSincronizado(int ledIndex, int frequencia, int tempo) {
  digitalWrite(leds[ledIndex], HIGH);  // Acende o LED
  tone(buzzerPin, frequencia);         // Toca a nota correspondente
  delay(tempo);                        // Duração da nota
  noTone(buzzerPin);                   // Para o som
  digitalWrite(leds[ledIndex], LOW);   // Apaga o LED
  delay(50);                           // Breve pausa entre notas
}

void setup() {
  for (int i = 0; i < 9; i++) {
    pinMode(leds[i], OUTPUT);
  }
  pinMode(botaoPin, INPUT);
  pinMode(buzzerPin, OUTPUT);
}

void loop() {
  static bool botaoAnterior = LOW;
  bool botaoAtual = digitalRead(botaoPin);

  if (botaoAtual == HIGH && botaoAnterior == LOW) {
    configuracao++;
    if (configuracao > 0) {
      configuracao = 0;
    }

    if (configuracao == 0) {
      configurarLeds(1);
      tocarMusica(1);  // Tocar Megalovania

      configurarLeds(2);
      tocarMusica(2);  // Tocar Megalovania

      configurarLeds(3);
      tocarMusica(3);  // Tocar Megalovania

      configurarLeds(4);
      tocarMusica(4);  // Tocar Megalovania

    } else {
      
      digitalWrite(buzzerPin, 0);

    } 

    delay(1000);  // Delay para evitar múltiplos acionamentos rápidos
  }

  botaoAnterior = botaoAtual;
}

void configurarLeds(int configuracao) {
  for (int i = 0; i < 9; i++) {
    digitalWrite(leds[i], LOW);
  }

  if (configuracao == 1) {
    for (int i = 0; i < 9; i++) {
      digitalWrite(leds[i], HIGH);
      delay(200);
    }
  } else if (configuracao == 2) {
    for (int i = 0; i < 9; i++) {
      digitalWrite(leds[i], HIGH);
    }
    delay(500);
    for (int i = 0; i < 9; i++) {
      digitalWrite(leds[i], LOW);
    }
    delay(500);
  } else if (configuracao == 3) {
    for (int i = 0; i < 9; i++) {
      if (random(2) == 0) {
        digitalWrite(leds[i], HIGH);
      }
else if (configuracao == 4) {
    for (int i = 0; i < 9; i++) {
      if (random(2) == 0) {
        digitalWrite(leds[i], HIGH);
      }
 else {
        digitalWrite(leds[i], LOW);
      }
    }
    delay(500);
  }
    }
  }
}
