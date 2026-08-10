🖥️ Monitor Serial

O Monitor Serial é uma ferramenta da Arduino IDE que permite visualizar mensagens enviadas pelo Arduino para o computador. Ele é muito útil para testar, acompanhar e identificar possíveis erros no funcionamento do projeto.

Para utilizar o Monitor Serial, primeiro é necessário iniciar a comunicação serial no setup():

Serial.begin(9600);

Depois, podemos enviar informações para o computador usando:

Serial.println("LED vermelho ligado");

No projeto da sinaleira, por exemplo, podemos informar qual LED está aceso:

void setup() {
  pinMode(8, OUTPUT);
  pinMode(9, OUTPUT);

  Serial.begin(9600);
}

void loop() {
  digitalWrite(8, HIGH);
  digitalWrite(9, LOW);

  Serial.println("LED vermelho ligado");
  delay(3000);

  digitalWrite(8, LOW);
  digitalWrite(9, HIGH);

  Serial.println("LED branco ligado");
  delay(3000);
}

Ao abrir o Monitor Serial e selecionar 9600 baud, aparecerá algo parecido com:

LED vermelho ligado
LED branco ligado
LED vermelho ligado
LED branco ligado

Isso permite acompanhar em tempo real o que o Arduino está executando.
