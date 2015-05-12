//TelephoNOUS: Twisted Epiphanies.
//A collaborative digital media project by Travis Feldman, John Barber, and Marc Rose.
//November 2014-May 2015.
//Vancouver, WA and Portland, OR.
//This sketch will determine how Arduino interprets
//phone numbers entered via the touch-tone keypad; 
//Two Arduino libraries are needed: Keypad and Tone.

#include <Keypad.h>
#include <Tone.h>

int keyNumber = 0;
int keySum = 0;
int i = 0;
int num = 0;
int newnum;
int keyPressCounter = 0;

int a = A5;
int b = A4;
int c = A3;
int d = A2;
int e = A1;


Tone freq1;
Tone freq2;

const int DTMF_freq1[] = { 1336, 1209, 1336, 1477, 1209, 1336, 1477, 1209, 1336, 1477 };
const int DTMF_freq2[] = {  941,  697,  697,  697,  770,  770,  770,  852,  852,  852 };

const byte ROWS = 4; //four rows
const byte COLS = 3; //three columns
char keys[ROWS][COLS] = {
  {'1', '2', '3'},
  {'4', '5', '6'},
  {'7', '8', '9'},
  {'*', '0', '#'}
};
byte rowPins[ROWS] = {5, 4, 3, 2}; //connect to the row pinouts of the kpd
byte colPins[COLS] = {8, 7, 6}; //connect to the column pinouts of the kpd

Keypad kpd = Keypad (makeKeymap(keys), rowPins, colPins, ROWS, COLS );

String msg;

void setup() {
  Serial.begin(9600);

  pinMode(a, OUTPUT);
  pinMode(b, OUTPUT);
  pinMode(c, OUTPUT);
  pinMode(d, OUTPUT);
  pinMode(e, OUTPUT);

  freq1.begin(11);
  freq2.begin(12);

  msg = "";

}

void playDTMF(uint8_t number, long duration)
{
  freq1.play(DTMF_freq1[number], duration);
  freq2.play(DTMF_freq2[number], duration);
}

void loop() {

  digitalWrite(a, HIGH);
  digitalWrite(b, HIGH);
  digitalWrite(c, HIGH);
  digitalWrite(d, HIGH);
  digitalWrite(e, HIGH);

  char key = kpd.getKey();
  if (key) {
    switch (key)    //here we use SwitchCase statements http://www.arduino.cc/en/Reference/SwitchCase
    {
      case '*':

        {
          int keyNumber = 1;
        }
        msg = "*";
        Serial.println(msg);
        keyNumber = (msg.toInt() + 1);  //.toInt() function converts String to an integer
        playDTMF(0, 300);

        digitalWrite(c, LOW);
        delay(200);
        digitalWrite(c, HIGH);

        break;

      case '0':

        {
          int keyNumber = 1;
        }
        msg = "0";
        Serial.println(msg);
        keyNumber = (msg.toInt() + 1);
        playDTMF(0, 300);

        digitalWrite(a, LOW);
        delay(200);
        digitalWrite(a, HIGH);

        break;

      case '#':

        {
          int keyNumber = 1;
        }
        msg = "#";
        Serial.println(msg);
        keyNumber = (msg.toInt() + 1);
        playDTMF(0, 300);

        digitalWrite(e, LOW);
        delay(200);
        digitalWrite(e, HIGH);

        break;

      case '9':

        {
          int keyNumber = 10;
        }
        msg = "9";
        Serial.println(msg);
        keyNumber = (msg.toInt() + 1);
        playDTMF(9, 300);

        digitalWrite(d, LOW);
        delay(200);
        digitalWrite(d, HIGH);

        break;

      case '8':

        {
          int keyNumber = 9;
        }
        msg = "8";
        Serial.println(msg);
        keyNumber = (msg.toInt() + 1);
        playDTMF(8, 300);

        digitalWrite(c, LOW);
        delay(200);
        digitalWrite(c, HIGH);

        break;

      case '7':

        {
          int keyNumber = 8;
        }
        msg = "7";
        Serial.println(msg);
        keyNumber = (msg.toInt() + 1);
        playDTMF(7, 300);

        digitalWrite(b, LOW);
        delay(200);
        digitalWrite(b, HIGH);

        break;

      case '6':

        {
          int keyNumber = 7;
        }
        msg = "6";
        Serial.println(msg);
        keyNumber = (msg.toInt() + 1);
        playDTMF(6, 300);

        digitalWrite(a, LOW);
        delay(200);
        digitalWrite(a, HIGH);

        break;

      case '5':

        {
          int keyNumber = 6;
        }
        msg = "5";
        Serial.println(msg);
        keyNumber = (msg.toInt() + 1);
        playDTMF(5, 300);

        digitalWrite(e, LOW);
        delay(200);
        digitalWrite(e, HIGH);

        break;

      case '4':

        {
          int keyNumber = 5;
        }
        msg = "4";
        Serial.println(msg);
        keyNumber = (msg.toInt() + 1);
        playDTMF(4, 300);

        digitalWrite(d, LOW);
        delay(200);
        digitalWrite(d, HIGH);

        break;

      case '3':

        {
          int keyNumber = 4;
        }
        msg = "3";
        Serial.println(msg);
        keyNumber = (msg.toInt() + 1);
        playDTMF(3, 300);

        digitalWrite(c, LOW);
        delay(200);
        digitalWrite(c, HIGH);

        break;

      case '2':

        {
          int keyNumber = 3;
        }
        msg = "2";
        Serial.println(msg);
        keyNumber = (msg.toInt() + 1);
        playDTMF(2, 300);

        digitalWrite(b, LOW);
        delay(200);
        digitalWrite(b, HIGH);

        break;

      case '1':

        {
          int keyNumber = 2;
        }
        msg = "1";
        Serial.println(msg);
        keyNumber = (msg.toInt() + 1);
        playDTMF(1, 300);

        digitalWrite(a, LOW);
        delay(200);
        digitalWrite(a, HIGH);

        break;

      default:
        Serial.println(keyNumber);
    }

    Serial.print("You just pressed: ");
    Serial.println(keyNumber - 1);
    num = keyNumber + num;
    newnum = num;
    if (num != keyNumber) {
      keyPressCounter = keyPressCounter ++;
    } else {
      keyPressCounter == keyPressCounter;
    }
    Serial.print("Total number of key presses: ");
    Serial.println(keyPressCounter);

    keySum = newnum;
    Serial.print("Sum total of digits entered (key press + 1) is ");
    Serial.println(keySum);
  }
}
