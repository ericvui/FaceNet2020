## FaceNet and MTCNN
Nhận diện khuôn mặt khá chuẩn xác bằng MTCNN và Facenet!

Practise article link: 
https://www.miai.vn/2019/09/11/face-recog-2-0-nhan-dien-khuon-mat-trong-video-bang-mtcnn-va-facenet/

## Mai Vui
Tiểu luận mô học: Thị Giác Máy Tính

# MỘT SỐ BƯỚC
1. Tiền xử lý dữ liệu với lệnh sau:

    python src/align_dataset_mtcnn.py  Dataset/FaceData/raw Dataset/FaceData/processed --image_size 160 --margin 32  --random_order --gpu_memory_fraction 0.25

2. Train model với 1 số ảnh mới trong bộ dữ liệu 

    python src/classifier.py TRAIN Dataset/FaceData/processed Models/20180402-114759.pb Models/facemodel.pkl --batch_size 1000

## KIỂM THỬ KẾT QUẢ MODEL
1. Với video là nguồn đã record.

    a) Donald Trump
    
        python src/face_rec.py --path video/DonaldTrumpCovid19.mp4 
    
    b) Donald Trump va Biden

        python src/face_rec.py --path video/TrumpBiden.mp4    
        
        python src/face_rec.py --path video/TrumpBiden.wmv
        
    c) Mr. Bean
        
        python src/face_rec.py --path video/MrBean.mp4 

2. Với Webcam
    
        python src/face_rec_cam.py

 