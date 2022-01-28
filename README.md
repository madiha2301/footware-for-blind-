# footware-for-blind-
/* Constants for broches */
const byte TRIGGER_PIN = 2; // Broche TRIGGER
const byte ECHO_PIN = 3;
// Broche ECHO
const byte LED_PIN = 12; // Broche LED
const unsigned long MEASURE_TIMEOUT = 50000UL; // 25ms = ~8m a 340m/s
const float SOUND_SPEED = 340.0 / 1000;



void setup() {
  //Serial Port begin
  Serial.begin (9600);
  //Define inputs and outputs
  pinMode(TRIGGER_PIN, OUTPUT);
  digitalWrite(TRIGGER_PIN, LOW);
  pinMode(LED_PIN,OUTPUT );
  digitalWrite(LED_PIN, LOW);
  pinMode(ECHO_PIN,INPUT );
}
 
void loop() {
  // The sensor is triggered by a HIGH pulse of 10 or more microseconds.
  // Give a short LOW pulse beforehand to ensure a clean HIGH pulse:
  digitalWrite(TRIGGER_PIN, HIGH);
  delayMicroseconds(10);
  digitalWrite(TRIGGER_PIN, LOW);
long measure = pulseIn(ECHO_PIN, HIGH, MEASURE_TIMEOUT);
float distance_mm = measure / 2.0*SOUND_SPEED;
if (distance_mm/1000 < 1&& distance_mm/1000>0)

{ 
digitalWrite (LED_PIN, HIGH) ; 
}
 else {digitalWrite (LED_PIN, LOW) ;

Serial . print (F ("Distance: ") ) ;
Serial. print (distance_mm / 1000.0, 2) ;
Serial. println (F ("m) ") ) ;

}}
 
