import processing.serial.*;

Serial port;
int sliderValue = 90; // Initial slider value
boolean draggingSlider = false;

void setup() {
  size(600, 400); // Increase the window size
  background(#a0d2eb); // Set background color
  String portName = Serial.list()[0]; // Change the index if needed
  port = new Serial(this, portName, 9600);
}

void draw() {
  background(#a0d2eb); // Refresh background color

  // Title
  fill(0);
  textSize(24);
  textAlign(CENTER, TOP);
  text("Shamim", width / 2, 10);

  // Display the slider
  float mappedValue = map(sliderValue, 0, 180, 200, 400);

  // Determine color based on slider position
  if (sliderValue >= 150) {
    fill(0, 255, 0); // Green
  } else if (sliderValue >= 100) {
    fill(165, 42, 42); // Brown
  } else if (sliderValue >= 50) {
    fill(135, 206, 250); // Sky Blue
  } else if (sliderValue >= 10) {
    fill(255, 215, 0); // Golden
  } else {
    fill(255, 0, 0); // Red
  }

  rect(200, 200, mappedValue - 200, 20, 10);

  // Display "Servo Position" text
  fill(0);
  textAlign(CENTER, CENTER);
  text("Servo Position: " + int(sliderValue), width / 2, 180);
}

void mousePressed() {
  if (mouseX >= 200 && mouseX <= 400 && mouseY >= 200 && mouseY <= 220) {
    draggingSlider = true;
  }
}

void mouseReleased() {
  draggingSlider = false;
}

void mouseDragged() {
  if (draggingSlider) {
    sliderValue = int(constrain(map(mouseX, 200, 400, 0, 180), 0, 180));
    port.write(sliderValue);
  }
}
