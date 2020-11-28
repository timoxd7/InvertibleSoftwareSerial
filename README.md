# Invertible Software Serial

This is a 1:1 Copy of the Arduino Software Serial (New Software Serial) but separates the inversion for the tx and rx pins individually

## Usage

It is used exactly as the original Software Serial but with a difference in the Constructor:

    InvertibleSoftwareSerial(uint8_t receivePin, uint8_t transmitPin, bool inverse_rx = false, bool inverse_tx = false)

So, to use it in your code, for example to invert the RX pin only, do this (with pin 2 for rx and pin 3 for tx):

    InvertibleSoftwareSerial softSerial(2, 3, true, false);

Later in the code, it is used like the normal Serial:

    // ...
    
    void setup() {
        // ...
        softSerial.begin(9600); // To select baud rate
        // ...
    }

    // ...

    void loop() {
        // ...
        softSerial.println("Test");
        // ...
    }
