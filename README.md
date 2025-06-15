# ETL Weather Airflow Project

## Tổng quan

Đây là project ETL pipeline sử dụng Apache Airflow để tự động thu thập, xử lý và lưu trữ dữ liệu thời tiết từ API Open-Meteo vào cơ sở dữ liệu PostgreSQL. Pipeline này được triển khai dưới dạng DAG trong Airflow, thực hiện các bước Extract, Transform, Load (ETL) cho dữ liệu thời tiết của một vị trí cụ thể (Tokyo).

## Cấu trúc project

- **dags/etlweather.py**: Chứa định nghĩa DAG chính cho pipeline ETL thời tiết.
- **docker-compose.yml**: Khởi tạo dịch vụ PostgreSQL phục vụ cho việc lưu trữ dữ liệu.
- **requirements.txt**: Khai báo các thư viện Python cần thiết (có thể bổ sung nếu cần).
- **plugins/**, **include/**: Thư mục mở rộng cho các plugin hoặc file bổ sung (hiện để trống).
- **.astro/**: Thư mục cấu hình cho Astronomer/Airflow.

## Quy trình ETL

1. **Extract**: Sử dụng `HttpHook` để lấy dữ liệu thời tiết hiện tại từ API Open-Meteo cho vị trí Tokyo.
2. **Transform**: Trích xuất các trường dữ liệu cần thiết như nhiệt độ, tốc độ gió, hướng gió, mã thời tiết,...
3. **Load**: Sử dụng `PostgresHook` để lưu dữ liệu đã xử lý vào bảng `weather_data` trong PostgreSQL. Nếu bảng chưa tồn tại sẽ tự động tạo mới.

## Hướng dẫn chạy project

1. **Create project**: "astro dev init"
2. **Run project**: "astro dev start"

## Contact
Email: phong.danghandsomek@hcmut.edu.vn
