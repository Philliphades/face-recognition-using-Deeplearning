#Nhận diện khuôn mặt khá chuẩn xác bằng MTCNN và Facenet!
-Tiền xử lý dữ liệu để cắt khuôn mặt từ ảnh gốc
-Với chỗ ảnh mà đã  chọn bên trên, có thể là ảnh cả người, bây giờ ta sẽ cắt riêng khuôn mặt ra để train. 

-Chạy lệnh :
python src/align_dataset_mtcnn.py Dataset/FaceData/raw Dataset/FaceData/processed --image_size 160 --margin 32 --random_order --gpu_memory_fraction 0.25

-Tiến hành train model để nhận diện khuôn mặt
python src/classifier.py TRAIN Dataset/FaceData/processed Models/20180402-114759.pb Models/facemodel.pkl --batch_size 1000

-Bạn chạy file face_rec_cam.py bằng lệnh sau:
python src/face_rec_cam.py
Nhận diện khuôn mặt qua webcam 

- bạn chạy;
python src/face_rec.py --path video/camtest.mp4
để nhận diện khuôn mat qua video




