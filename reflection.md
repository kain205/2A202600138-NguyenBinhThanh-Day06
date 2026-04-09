# Individual reflection — Nguyễn Bình Thành (2A202600138)

## 1. Role
Techlead + AI Engineer kiêm Fullstack Dev.
Đóng góp phần lớn code.

## 2. Đóng góp cụ thể
- Thiết kế và xây dựng dual-search RAG phân tầng officials/community. Hệ thống sẽ chia ra 2 hướng: nếu được người dùng assign role, query(top3_officials, top3_community), nếu chưa được assign role -> query(top6_all)
- Xây tools calling: 
    - query_rewrite: LLM rewrite query dựa vào context, ví dụ những trường hợp follow-up text sẽ không phù hợp: trả lời cụt ngủn "taxi" sẽ khó viết tạo query. 
    - fare_data: tính cước, có những parameters (loại dịch vụ, thành phố) cho function
    - intent_detector: đoán intent của người dùng cho trường hợp 1. (general) 2. submit form làm tài xế Xanh(driver_registration), 3. trường hợp cần con người can thiệp (human_escalation)

## 3. SPEC mạnh/yếu
- Mạnh nhất: Hỗ trợ bởi AI nên sẽ có đủ context, khớp với repo dự án. Mô tả đủ features
- Yếu nhất: AI viết phần lớn documentation nên có thể chưa đúng ý, đây sẽ là bài toán Automation chứ không phải Augmentation như AI đã viết.

## 4. Đóng góp khác
- Giúp các bạn làm việc với nhau dễ dàng hơn, kết nối mọi người lại với nhau để đi cùng 1 hướng đi. Mọi người ban đầu khá ngại đề xuất, không chủ động.

## 5. Điều học được
Trước hackathon, tiết học về Tools và Agent chỉ ở dạng lý thuyết, sau hackathon có cơ hội đẩy nhanh tiến độ giúp cô đọng kiến thức dễ dàng.
Sau khi triển khai Hackathon dự án mới hiểu: Cách Agent và Tools phối hợp với nhau trong 1 dự án có thể có impact ngoài thị trường, giải quyết 1 bài toán cụ thể mà chưa có sẵn bên ngoài.

## 6. Nếu làm lại
Sẽ nghĩ ý tưởng độc đáo hơn, ý tưởng này rất thực tiễn nhưng mà chưa Win được hackathon 4.69 so với 4.78 của nhóm top1. Nhưng mà nói chung thì vẫn rất hài lòng, nếu dành thời gian nghĩ ý tưởng thì có thể khiến điểm tệ hơn.
Chưa test kĩ phần test case mà chỉ trả lời được khi RAG từ nguồn data Community, khiến lúc demo chựng 1 nhịp

## 7. AI giúp gì / AI sai gì
- **Giúp:** AI giúp triển khai vừa đưa code.
- **Sai/mislead:** Claude không thật sự hiểu giới hạn của công nghệ. Hôm nay khi nhóm đang cố add 1 phần để UI hiển thị những câu hỏi gợi ý, Claude dựa vào docs code nói không thể chèn được do chainlit đã set câu hỏi chào của AI chatbot làm chỗ để hiển thị câu hỏi gợi ý. Nhưng mà đấy không đúng sự thật, em đã dựa vào quan sát là UI có hiển thị mục "chọn tệp khách hàng" cùng với câu hỏi chào, em nghĩ là cái "hộp" ghi chữ "tệp khách hàng" đấy không có lí do gì mà không có properties để thay thế thành ô gợi ý câu hỏi -> tức là nếu ta đã có thể ấn vào nhận tệp khách hàng, không có lí do gì mà không thể ấn vào -> dùng luôn câu hỏi gợi ý.
    - Ngoài ra, Claude cũng không thể đề xuất đúng pipeline RAG 1 cách tin cậy, pipeline design phải tự nhóm nghĩ ra 