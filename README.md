NodeMCU Flasher
===============

NodeMCU flasher is a firmware programmer for NodeMCU DEVKIT V0.9.

You can use it to program NodeMCU DEVKIT or your own ESP8266 board.

You MUST set GPIO0 to LOW before programming, and NodeMCU DEVKIT V0.9 will do it automatically.

This is demo version.

We are working on next version and will use QT framework. 

It will be cross platform and open source.

Usage
---------------
Just click flash and you can burn firmware to ESP8266. Before you doing it, GPIO0 MUST LOW.

![Begin program](Resources/Images/NodeMCU-Flasher-Begin.png)

And wait a moment.

![Programming](Resources/Images/NodeMCU-Flasher-Programming.png)

Program success.

![Program success](Resources/Images/NodeMCU-Flasher-Success.png)

Setting your own firmware.

![Setting](Resources/Images/NodeMCU-Flasher-Setting.png)

When the path have some error(e.g. file not exist), the line will become red.

Tips: You could use some special path to do something interesting.

The blank.bin file:

INTERNAL://BLANK

The esp_init_data_default.bin file(for 26MHz crystal):

INTERNAL://DEFAULTimport cv2

def start_sofia_vision():
    # 1. Initialize the camera (0 is usually the default webcam)
    camera = cv2.VideoCapture(0)

    if not camera.isOpened():
        print("Error: Could not open Sofia's camera.")
        return

    print("Sofia is now looking...")

    while True:
        # 2. Capture frame-by-frame
        ret, frame = camera.read()

        if not ret:
            print("Error: Failed to grab visual data.")
            break

        # 3. (Optional) Convert to grayscale for easier 'learning' processing
        # gray_vision = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)

        # 4. Display the resulting frame
        cv2.imshow('Sofia Vision Feed', frame)

        # 5. Break the loop if the 'q' key is pressed
        if cv2.waitKey(1) & 0xFF == ord('q'):
            break

    # 6. Release the hardware and close windows
    camera.release()
    cv2.destroyAllWindows()
    print("Sofia has closed her eyes.")

if __name__ == "__main__":
    start_sofia_vision()

