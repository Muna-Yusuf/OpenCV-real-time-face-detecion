# OpenCV-real-time-face-detecion
Using opencv with python to make a real time face detection :

Make sure you have cv2 and umpy packages .

download haarcascade_frontalface_default.xml .
 

    import cv2

    print("Package Imported")
    cap=cv2.VideoCapture(0)   # to use cam

    while cap.isOpened() :   # while loop to dedct faces
        _, img = cap.read ()

    face_cascade = cv2.CascadeClassifier("haarcascade_frontalface_default.xml")
    gray = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
    Faces =face_cascade.detectMultiScale(gray, 1.1, 4)

    for (x,y,w,h) in Faces:
        cv2.rectangle(img, (x,y), (x+w, y+h),(255,0,0),3)

    cv2.imshow("image",img)
    if cv2.waitKey(1)  &  0xFF == ord('q'):
        break

    cap.release()
