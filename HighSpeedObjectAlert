import cv2
import winsound

# Kamera
camera = cv2.VideoCapture(0)

while True:
    # görüntü al
    ret, frame = camera.read()
    if not ret:
        break

    # Gri tonlamaya çevir
    gray_frame = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)

    # Parlaklık eşiğini belirle ve maskele
    _, bright_mask = cv2.threshold(gray_frame, 220, 255, cv2.THRESH_BINARY)

    # Maske üzerinde konturlar
    contours, _ = cv2.findContours(bright_mask, cv2.RETR_TREE, cv2.CHAIN_APPROX_SIMPLE)

    # En parlak noktanın merkezini bul
    if contours:
        largest_contour = max(contours, key=cv2.contourArea)
        (x, y), radius = cv2.minEnclosingCircle(largest_contour)
        center = (int(x), int(y))
        if radius > 2:
            # çember çiz
            cv2.circle(frame, center, int(radius * 2), (0, 255, 0), 2)
            cv2.circle(frame, center, 5, (0, 0, 255), -1)


            cv2.putText(frame, "Roket isigi algilandi", (center[0] - int(radius), center[1] - int(radius) - 10),
                        cv2.FONT_HERSHEY_SIMPLEX, 0.5, (0, 255, 0), 1)

            # Ses
            winsound.Beep(2500, 100)

    # Ekran
    cv2.imshow('Video', frame)
    cv2.imshow('Bright Objects', bright_mask)


    if cv2.waitKey(1) & 0xFF == ord('q'):
        break


camera.release()
cv2.destroyAllWindows()
