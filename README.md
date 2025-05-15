int relayPin = 7;
int pirPin = 2;
int pirState = LOW;

void setup() {
  pinMode(relayPin, OUTPUT);
  pinMode(pirPin, INPUT);
  Serial.begin(9600);
}

void loop() {
  int motionDetected = digitalRead(pirPin);
  if (motionDetected == HIGH) {
    digitalWrite(relayPin, HIGH); // Turn light on
    Serial.println("Motion detected!");
    delay(10000); // Keep light on for 10 sec
    digitalWrite(relayPin, LOW); // Turn light off
  }
}
