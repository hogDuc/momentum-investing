# I. Đề bài
Một số nghiên cứu chỉ ra rằng Chiến lược đầu tư cổ phiếu Động lượng (mua vào các cổ phiếu có mức tăng giá mạnh nhất trên thị trường) có thể đánh bại thị trường trong dài hạn.

a. Hãy áp dụng chiến lược Động lượng với thị trường cổ phiếu Việt Nam để xây dựng danh mục cổ phiếu. Thực hiện kiểm thử và đánh giá hiệu quả đầu tư danh mục này, bắt đầu từ ngày 02/01/2025 tới 16/05/2025, so sánh với VN-Index là danh mục tiêu chuẩn.

b. Đưa ra danh sách và tỷ trọng cổ phiếu khuyến nghị với ngày đầu tư là 27/05/2025.

# II. Hướng dẫn sử dụng
Có 2 cách trích xuất danh mục và kiểm thử hiệu quả
### 1. Sử dụng dashboard Streamlit
Truy cập qua url [Dashboard](https://ducngh-momentum.streamlit.app/)

Hoặc chạy `streamlit run momentum.py`

*Lưu ý*: Lần chạy đầu của dashboard sẽ bị chậm do cần thời gian xử lý dữ liệu lần đầu

### 2. Sử dụng notebook momentum.ipynb
Truy cập notebook `momentum.ipynb` để kiểm thử và trích xuất danh mục đề xuất. Hướng dẫn chi tiết sẽ được để trong notebook.
[Truy cập notebook tại đây](./momentum.ipynb)

# III. Phương pháp
### 1. Chiến lược đầu tư cổ phiếu Động lượng - Momentum investing
Chiến lược đầu tư cổ phiếu Động lượng là chiến lược mua những cổ phiếu đang tăng giá và bán chúng khi giá có vẻ đạt đến đỉnh tăng. Tuy nhiên, việc xét mức độ tăng của giá cổ phiếu không nên được xét trong thời gian quá ngắn, mà cần được quan sát qua nhiều khoảng thời gian khác nhau để đảm bảo rằng các cổ phiếu tăng trưởng mạnh không phải là tức thời, tránh trường hợp "lái" trong vài phiên. Do đó các mức tăng trưởng 1 tháng, 3 tháng, 6 tháng và 12 tháng sẽ được sử dụng để đánh giá mức độ tăng giá của các cổ phiếu.

### 2. Giả định
- Nhà đầu tư có thể mua các lượng cổ phiếu bất kỳ.
- Thị trường không có phí giao dịch.
- Thị trường giao dịch sôi nổi, không có hiện tượng không mua, bán được cổ phiếu.

### 3. Bước thực hiện
Từ dữ liệu lịch sử giá các mã trên sàn chứng khoán, thực hiện tính lợi nhuận tích lũy theo các khoảng thời gian 1 tháng, 3 tháng, 6 tháng và 12 tháng. Tính điểm Động lượng - momentum score bằng cách tính trung bình lợi nhuận tích lũy các khoảng thời gian.

Thực hiện tính lợi nhuận tích lũy tương tự với dữ liệu VNIndex để thực hiện so sánh, lọc ra các cổ phiếu có điểm Động lượng cao hơn VNIndex, tức các cổ phiếu có mức tăng trung bình cao hơn VNIndex.

Khi đã có danh sách các mã cổ phiếu điểm Động lượng cao hơn VNIndex, thực hiện tối ưu hóa danh mục, tìm tỷ trọng phân bổ cổ phiếu sao cho có tỷ lệ Sharpe lớn nhất, giúp nhà đầu tư giảm thiểu rủi ro.
