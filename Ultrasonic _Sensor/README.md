## Ultra-Sonic Sensor

The main process of this sensor is to calculate the distance to an obstacle. The sensor emits a wave and calculates the distance by the time it takes to reflect in the face of an obstacle. For example, the reader system and the bats used this method. This ultrasonic sensor includes two knobs. One knob emits a pulse and the other knob detects the pulse. This sensor cannot be used for long distances. The maximum value is 25-30 cm. I am not satisfied with the values ​​beyond that. It is more suitable for short distances. If you need long-distance sensors, there are various sensors available in the market. Waterproof sensors are also available in the market. Below is how the ultrasonic sensor works with the Arduino board. The components required for this project and how to purchase these components are given below. we can use the serial monitor to watch the sensor readings.

<img src="https://i0.wp.com/srituhobby.com/wp-content/uploads/2021/04/11-29.jpg?resize=768%2C432&ssl=1"
     alt="Markdown Monster icon"
     style="float: left; margin-right: 10px;" />

### Circuit

Connect the circuit as shown

<img src="https://i0.wp.com/srituhobby.com/wp-content/uploads/2021/04/12-25.jpg?resize=768%2C472&ssl=1"
     alt="Markdown Monster icon"
     style="float: left; margin-right: 10px;" />
### Code

     void setup() {
       pinMode(2, OUTPUT);//define arduino pin
       pinMode(4, INPUT);//define arduino pin
       Serial.begin(9600);//enable serial monitor

     }
     void loop() {
       //pulse output
       digitalWrite(2, LOW);
       delayMicroseconds(4);
       digitalWrite(2, HIGH);
       delayMicroseconds(10);
       digitalWrite(2, LOW);

       long t = pulseIn(4, HIGH);//input pulse and save it veriable

       long inches = t / 74 / 2; //time convert distance
       long cm = t / 29 / 2; //time convert distance
       String inch = " inches t";
       String CM = " cm";

       Serial.print(inches +inch);//print serial monitor inches
       Serial.println(cm +CM);//print serial monitor cm
       Serial.println();//print space
       delay(100);//delay
     }
     
Upload the code to arduino nano and check the serial monitor after uploading.
