🛒

__ADVANCED PRODUCT SEARCH ENGINE__

*Business Requirement Document \(BRD\)*

Tính năng: Product Search \(Tìm Kiếm Sản Phẩm\)

Mô hình phát triển: Agile / Scrum

Phiên bản: 1\.0  |  Ngày phát hành: 09/07/2026

Trạng thái: Bản nháp \- Chờ phê duyệt \(Draft \- Pending Approval\)

# __Lịch Sử Thay Đổi Tài Liệu \(Document Control\)__

__Phiên bản__

__Ngày__

__Người soạn thảo__

__Mô tả thay đổi__

0\.1

05/07/2026

Business Analyst

Khởi tạo tài liệu yêu cầu nghiệp vụ ban đầu

1\.0

09/07/2026

Business Analyst

Hoàn thiện BRD đầy đủ, bổ sung Epics/User Stories theo Agile, NFR, kế hoạch Sprint

# __Mục Lục \(Table of Contents\)__

# __1\. Giới Thiệu & Mục Tiêu Dự Án__

## __1\.1\. Bối cảnh nghiệp vụ__

Nền tảng là một sàn thương mại điện tử B2B/B2C đa quốc gia \(giả định\), phục vụ đồng thời người mua và người bán tại nhiều thị trường có ngôn ngữ khác nhau \(khu vực nói tiếng Việt, tiếng Anh và tiếng Thái\)\. Tính năng tìm kiếm sản phẩm \(Product Search\) là điểm chạm quan trọng nhất trong hành trình mua hàng, ảnh hưởng trực tiếp đến tỷ lệ chuyển đổi và doanh thu của toàn sàn\.

Tài liệu này mô tả toàn bộ yêu cầu nghiệp vụ \(Business Requirements\) cho việc xây dựng mới Product Search Engine, được tổ chức theo mô hình phát triển Agile/Scrum nhằm phục vụ việc lập Product Backlog, chia Epic/User Story và lên kế hoạch Sprint cho đội phát triển\.

## __1\.2\. Mục tiêu kinh doanh cốt lõi__

- Tăng Tỷ Lệ Chuyển Đổi \(Conversion Rate\): giúp người dùng tìm thấy đúng sản phẩm mong muốn ngay lập tức, giảm tỷ lệ thoát trang do không tìm thấy kết quả\.
- Giảm Tỷ Lệ Tìm Kiếm Rỗng \(Zero\-Results Rate\): tự động phát hiện lỗi gõ sai, từ đồng nghĩa hoặc dịch nghĩa để đề xuất sản phẩm phù hợp thay vì hiển thị màn hình trắng\.
- Hỗ Trợ Kinh Doanh Đa Quốc Gia: tích hợp khả năng tìm kiếm song ngữ/đa ngôn ngữ Việt \- Anh \- Thái\.
- Tối Ưu Trải Nghiệm Người Dùng \(UX\): đảm bảo kết quả tìm kiếm và gợi ý từ khóa xuất hiện tức thì, tạo cảm giác mượt mà, cao cấp\.

## __1\.3\. Chỉ số thành công về mặt nghiệp vụ \(Business KPIs\)__

__KPI__

__Mục tiêu__

__Ý nghĩa nghiệp vụ__

Search Latency \(độ trễ tìm kiếm\)

< 50ms cho kết quả tìm kiếm

Đảm bảo trải nghiệm mượt mà, không gây gián đoạn hành vi mua sắm

Autocomplete Latency

< 5ms cho gợi ý từ khóa

Gợi ý phải theo kịp tốc độ gõ phím của người dùng

Tỷ lệ sửa lỗi chính tả chính xác

> 95% với các lỗi gõ sai phổ biến

Giảm thất thoát khách hàng do gõ sai từ khóa thương hiệu/sản phẩm

Khả năng chịu tải \(Scalability\)

Ổn định ở mức 500 lượt truy cập đồng thời

Đảm bảo vận hành an toàn trong các chiến dịch flash sale / khuyến mãi lớn

Zero\-Results Rate

Giảm dần theo từng Sprint nhờ vòng lặp tự học \(mục 3\.6\)

Đo lường hiệu quả của cơ chế học từ khóa tự động

# __2\. Phạm Vi Dự Án \(Project Scope\)__

## __2\.1\. Trong phạm vi \(In\-Scope\)__

- Xây dựng bộ máy Smart Autocomplete \(gợi ý từ khóa tức thì, song ngữ\)\.
- Xây dựng module Tách từ & Xử lý đa ngôn ngữ \(Segmenter\) cho tiếng Việt, Anh, Thái\.
- Xây dựng cơ chế Dịch Nghĩa & Mở Rộng Truy Vấn \(Translation Search\) giữa 3 ngôn ngữ\.
- Xây dựng module Tự Động Sửa Lỗi Chính Tả & Từ Đồng Nghĩa \(Spellcheck & Synonyms\)\.
- Xây dựng Thuật Toán Xếp Hạng Kết Quả \(Ranking Engine\) theo quy tắc nghiệp vụ đã định nghĩa\.
- Xây dựng Cơ Chế Học Từ Khóa Tự Động \(Self\-Learning Feedback Loop\) và trang quản trị \(Admin Portal\) phê duyệt đề xuất\.
- Thiết kế kiến trúc đảm bảo hiệu năng cao, khả năng chịu tải và cô lập sự cố \(Non\-Functional Requirements ở mục 5\)\.

## __2\.2\. Ngoài phạm vi \(Out\-of\-Scope\)__

- Tìm kiếm bằng hình ảnh \(Visual/Image Search\) \- có thể xem xét ở giai đoạn sau\.
- Tìm kiếm bằng giọng nói \(Voice Search\)\.
- Cá nhân hóa kết quả tìm kiếm dựa trên lịch sử mua hàng \(Personalization\) \- đề xuất đưa vào Roadmap Phase 2\.
- Hệ thống quảng cáo/đấu giá từ khóa \(Keyword Bidding Platform\) cho Seller \- chỉ tích hợp điểm neo \(hook\) ưu tiên Sponsored Product tại mục 3\.5, chưa xây dựng sàn đấu giá\.
- Hỗ trợ ngôn ngữ khác ngoài Việt \- Anh \- Thái trong phạm vi giai đoạn 1\.

# __3\. Đối Tượng Người Dùng & Hành Vi \(User Personas\)__

Ba nhóm đối tượng chính tương tác với Product Search Engine, thể hiện qua luồng nghiệp vụ sau:

__Luồng tương tác tổng quan__

Người Mua → nhập từ khóa \(có thể sai chính tả / autocomplete\) → Search Engine trả kết quả  |  Người Bán → đăng ký sản phẩm, tối ưu hiển thị/Sponsored → Search Engine lập chỉ mục  |  Quản Trị Viên → quản lý từ điển, phê duyệt đề xuất → Search Engine cập nhật tức thời\.

__Persona__

__Mục tiêu / Nhu cầu__

__Điểm đau \(Pain Point\) hiện tại__

Khách hàng \(Buyer\)

Nhập từ khóa \(có thể viết tắt, sai chính tả, ngôn ngữ pha trộn\) và nhận danh sách sản phẩm liên quan nhất trong nháy mắt

Gõ sai chính tả hoặc dùng ngôn ngữ khác với sản phẩm dẫn đến 0 kết quả; chờ đợi lâu khi gõ từ khóa

Nhà bán hàng \(Seller\)

Sản phẩm chiến lược/trả phí quảng cáo được ưu tiên hiển thị ở vị trí đầu khi khách tìm từ khóa liên quan

Sản phẩm bị chìm dưới các kết quả khác dù có mức độ liên quan tương đương

Quản trị viên \(Admin\)

Giao diện quản trị để cấu hình từ đồng nghĩa, bản dịch Việt\-Anh\-Thái, phê duyệt đề xuất sửa lỗi tự động

Thiếu công cụ để cập nhật từ điển/đề xuất theo thời gian thực mà không cần deploy lại hệ thống

# __4\. Yêu Cầu Nghiệp Vụ Chi Tiết Theo Epic \(Functional Requirements / Product Backlog\)__

Toàn bộ yêu cầu chức năng được tổ chức thành 6 Epic tương ứng với 6 nhóm năng lực cốt lõi của Search Engine\. Mỗi Epic được chia nhỏ thành nhiều User Story kèm nhiều Tiêu chí Chấp nhận \(Acceptance Criteria \- AC\) cho từng Story, và ước lượng độ ưu tiên/điểm \(Story Points\) theo phương pháp MoSCoW & Planning Poker, sẵn sàng đưa vào Product Backlog\.

*Quy ước đánh số: mỗi AC được gắn mã tương ứng trực tiếp với User Story chứa nó, theo định dạng AC\-\[Epic\]\.\[Story\]\.\[STT AC\]\. Ví dụ: User Story US\-01\.2 có các tiêu chí chấp nhận được đánh số AC\-01\.2\.1, AC\-01\.2\.2, AC\-01\.2\.3\.\.\. giúp truy vết \(traceability\) rõ ràng giữa yêu cầu và tiêu chí kiểm thử\.*

## __EPIC\-01: Smart Autocomplete \- Gợi Ý Tìm Kiếm Thông Minh__

*Giúp người dùng tìm thấy từ khóa mong muốn ngay khi bắt đầu gõ, giảm thao tác nhập liệu và tăng tốc độ điều hướng đến sản phẩm\.*

### __Quy tắc nghiệp vụ \(Business Rules\)__

- Thời gian phản hồi gợi ý phải dưới 5ms để theo kịp tốc độ gõ phím\.
- Danh sách gợi ý được sắp xếp theo mức độ phổ biến \(tần suất tìm kiếm\), sau đó theo bảng chữ cái\.
- Hỗ trợ gợi ý song ngữ tương ứng với ngôn ngữ từ khóa người dùng đang nhập\.

### __User Stories & Acceptance Criteria__

__ID__

__User Story__

__Tiêu Chí Chấp Nhận \(Acceptance Criteria\)__

__Ưu Tiên / Điểm__

__US\-01\.1__

Là Khách hàng, tôi muốn thấy danh sách từ khóa gợi ý ngay khi gõ ký tự đầu tiên, để tôi tìm sản phẩm nhanh hơn\.

__AC\-01\.1\.1: __Khi người dùng gõ ≥1 ký tự vào ô tìm kiếm, danh sách gợi ý phải hiển thị trong vòng dưới 5ms kể từ thời điểm ký tự được nhập\.

__AC\-01\.1\.2: __Danh sách gợi ý tự động cập nhật theo từng ký tự tiếp theo mà không cần người dùng nhấn phím Enter hay nút tìm kiếm\.

__AC\-01\.1\.3: __Nếu không có gợi ý phù hợp, ô gợi ý ẩn đi thay vì hiển thị khung trống gây rối giao diện\.

__AC\-01\.1\.4: __Số lượng gợi ý hiển thị tối đa được giới hạn cấu hình được \(mặc định 10 mục\) để tránh che khuất màn hình trên thiết bị di động\.

Must Have / 8 pts

__US\-01\.2__

Là Khách hàng, tôi muốn gợi ý được sắp xếp theo mức độ phổ biến, để các lựa chọn liên quan nhất hiện lên trước\.

__AC\-01\.2\.1: __Danh sách gợi ý được sắp xếp theo tần suất tìm kiếm \(search volume\) giảm dần\.

__AC\-01\.2\.2: __Các từ khóa có cùng tần suất tìm kiếm được sắp xếp phụ theo thứ tự bảng chữ cái\.

__AC\-01\.2\.3: __Tần suất tìm kiếm dùng để xếp hạng được cập nhật định kỳ \(tối thiểu hàng ngày\) từ dữ liệu truy vấn thực tế\.

Must Have / 5 pts

__US\-01\.3__

Là Khách hàng nói tiếng Thái hoặc tiếng Anh, tôi muốn nhận gợi ý bằng đúng ngôn ngữ tôi đang gõ, để trải nghiệm nhất quán\.

__AC\-01\.3\.1: __Hệ thống tự động nhận diện ngôn ngữ của chuỗi ký tự đang nhập \(Việt/Anh/Thái\) dựa trên bộ ký tự và ngữ cảnh\.

__AC\-01\.3\.2: __Gợi ý trả về đúng bằng ngôn ngữ đã nhận diện, không trộn lẫn gợi ý từ ngôn ngữ khác\.

__AC\-01\.3\.3: __Trường hợp từ khóa mơ hồ giữa nhiều ngôn ngữ \(VD: ký tự Latin dùng chung\), hệ thống ưu tiên ngôn ngữ có tần suất sử dụng cao nhất của người dùng/thị trường\.

Should Have / 5 pts

__US\-01\.4__

Là Khách hàng, tôi muốn gợi ý bao gồm cả tên danh mục sản phẩm bên cạnh từ khóa sản phẩm, để tôi có thể khám phá nhanh theo nhóm ngành hàng\.

__AC\-01\.4\.1: __Danh sách gợi ý phân biệt rõ giữa gợi ý "từ khóa tìm kiếm phổ biến" và gợi ý "danh mục sản phẩm" bằng nhãn/icon riêng\.

__AC\-01\.4\.2: __Khi người dùng chọn một gợi ý danh mục, hệ thống điều hướng thẳng đến trang danh mục tương ứng thay vì trang kết quả tìm kiếm từ khóa\.

Could Have / 5 pts

__US\-01\.5__

Là Quản trị viên, tôi muốn loại bỏ hoặc ẩn các từ khóa gợi ý không phù hợp \(từ nhạy cảm, vi phạm chính sách\), để đảm bảo an toàn nội dung\.

__AC\-01\.5\.1: __Admin Portal cho phép tìm kiếm và gắn cờ "ẩn" cho một từ khóa gợi ý cụ thể\.

__AC\-01\.5\.2: __Từ khóa đã bị ẩn không xuất hiện trong danh sách Autocomplete ở mọi ngôn ngữ, có hiệu lực trong vòng dưới 1 phút sau khi Admin lưu thay đổi\.

Should Have / 5 pts

## __EPIC\-02: Multilingual Search & Segmenter \- Tìm Kiếm Đa Ngôn Ngữ & Phân Tách Từ__

*Xử lý tự nhiên các truy vấn bằng tiếng Việt, Anh, Thái, loại bỏ nhiễu \(stopwords\) và tách từ đúng ngữ nghĩa cho từng ngôn ngữ\.*

### __Quy tắc nghiệp vụ \(Business Rules\)__

- Tự động loại bỏ các từ đệm/trợ từ không mang giá trị tìm kiếm \(VD: VI: "của", "và"; EN: "the", "a"; TH: "และ", "ของ"\)\.
- Tiếng Thái: dùng Trie\-based tokenizer để tách câu viết liền không khoảng trắng\.
- Tiếng Việt: tách từ ghép/từ hai âm tiết \(VD: "cà phê", "áo thun", "điện thoại"\) thành một token đơn có nghĩa, tránh đối sánh nhầm từ đơn lẻ\.
- Tiếng Anh: tách từ theo khoảng trắng tiêu chuẩn\.

### __User Stories & Acceptance Criteria__

__ID__

__User Story__

__Tiêu Chí Chấp Nhận \(Acceptance Criteria\)__

__Ưu Tiên / Điểm__

__US\-02\.1__

Là Khách hàng gõ tiếng Thái không dấu cách, tôi muốn hệ thống tự tách đúng từng từ, để kết quả tìm kiếm chính xác\.

__AC\-02\.1\.1: __Chuỗi tiếng Thái viết liền không khoảng trắng được Trie\-based tokenizer tách thành các token đúng nghĩa dựa trên từ điển gốc\.

__AC\-02\.1\.2: __Tỉ lệ tách từ đúng đạt tối thiểu 95% trên bộ test\-set chuẩn \(tối thiểu 500 câu truy vấn Thái thực tế\)\.

__AC\-02\.1\.3: __Trường hợp không tách được \(từ ngoài từ điển\), hệ thống áp dụng thuật toán dự phòng \(longest\-match hoặc fallback n\-gram\) thay vì trả lỗi\.

Must Have / 13 pts

__US\-02\.2__

Là Khách hàng tìm "cà phê sữa", tôi không muốn hệ thống tách nhầm thành "cà", "phê", "sữa" riêng lẻ, để tránh kết quả sai lệch\.

__AC\-02\.2\.1: __Từ ghép tiếng Việt có trong từ điển \(VD: "cà phê", "áo thun", "điện thoại"\) được nhận diện và giữ nguyên thành một token duy nhất\.

__AC\-02\.2\.2: __Kết quả tìm kiếm không trả về sản phẩm chỉ khớp một âm tiết đơn lẻ không liên quan \(VD: sản phẩm "phê bình" không xuất hiện khi tìm "cà phê"\)\.

__AC\-02\.2\.3: __Từ điển từ ghép tiếng Việt có thể được Admin mở rộng qua Admin Portal mà không cần deploy lại code\.

Must Have / 8 pts

__US\-02\.3__

Là hệ thống, tôi cần loại bỏ stopwords của cả 3 ngôn ngữ trước khi đối sánh chỉ mục, để tối ưu tốc độ và độ chính xác truy vấn\.

__AC\-02\.3\.1: __Danh sách stopwords của từng ngôn ngữ \(VI/EN/TH\) được lưu trữ dưới dạng cấu hình có thể chỉnh sửa\.

__AC\-02\.3\.2: __Token thuộc danh sách stopwords bị loại khỏi chuỗi truy vấn trước bước match & scoring\.

__AC\-02\.3\.3: __Việc loại bỏ stopwords không làm mất ngữ nghĩa quan trọng \(VD: không loại từ nếu nó nằm trong một token ghép có nghĩa\)\.

Must Have / 5 pts

__US\-02\.4__

Là Khách hàng gõ tiếng Anh có khoảng trắng chuẩn, tôi muốn hệ thống tách từ đơn giản và nhanh, để không phát sinh độ trễ không cần thiết\.

__AC\-02\.4\.1: __Chuỗi tiếng Anh được tách theo khoảng trắng và dấu câu tiêu chuẩn \(space, dấu phẩy, dấu gạch ngang\)\.

__AC\-02\.4\.2: __Thời gian xử lý tách từ tiếng Anh không vượt quá 1ms cho truy vấn dưới 50 ký tự\.

Must Have / 3 pts

__US\-02\.5__

Là Khách hàng gõ truy vấn pha trộn nhiều ngôn ngữ trong cùng một câu \(VD: "áo thun size M"\), tôi muốn hệ thống xử lý đúng từng phần, để kết quả vẫn chính xác\.

__AC\-02\.5\.1: __Hệ thống phát hiện và tách riêng các cụm từ theo từng ngôn ngữ trong cùng một truy vấn hỗn hợp\.

__AC\-02\.5\.2: __Mỗi cụm từ được xử lý bằng tokenizer tương ứng với ngôn ngữ của chính nó trước khi gộp lại thành tập token cuối cùng\.

Could Have / 8 pts

## __EPIC\-03: Translation Search \- Dịch Nghĩa & Tìm Kiếm Chéo Ngôn Ngữ__

*Đảm bảo khách hàng tìm bằng bất kỳ ngôn ngữ nào trong 3 ngôn ngữ hỗ trợ vẫn tìm thấy sản phẩm được đăng ký bằng ngôn ngữ khác\.*

### __Quy tắc nghiệp vụ \(Business Rules\)__

- Ingestion Invalidation & Enrichment: khi sản phẩm được tạo bằng tiếng Việt, Ingestion Pipeline tự động dịch tiêu đề/mô tả sang Anh/Thái để tạo mảng token đa ngôn ngữ \(tokens\_vi, tokens\_en, tokens\_th\) trong chỉ mục\.
- Query\-time Translation Expansion: khi tìm bằng một ngôn ngữ \(VD "coffee"\), hệ thống mở rộng từ khóa sang các ngôn ngữ còn lại \(VD: \["cà phê", "กาแฟ"\]\) để đối sánh chéo trên toàn bộ chỉ mục\.
- Translation Match Weighting: kết quả trùng khớp đúng ngôn ngữ gốc truy vấn = 100% trọng số điểm; kết quả trùng khớp qua từ dịch = 80% trọng số điểm\.

### __User Stories & Acceptance Criteria__

__ID__

__User Story__

__Tiêu Chí Chấp Nhận \(Acceptance Criteria\)__

__Ưu Tiên / Điểm__

__US\-03\.1__

Là hệ thống Ingestion, tôi cần tự động dịch tiêu đề/mô tả sản phẩm tiếng Việt sang tiếng Anh và Thái khi Người bán đăng sản phẩm, để chỉ mục hỗ trợ tìm kiếm đa ngôn ngữ ngay từ đầu\.

__AC\-03\.1\.1: __Khi sản phẩm mới được tạo hoặc cập nhật bằng tiếng Việt, các trường tokens\_vi, tokens\_en, tokens\_th được sinh tự động và lưu vào chỉ mục\.

__AC\-03\.1\.2: __Với trường tiêu đề sản phẩm, việc dịch và lập chỉ mục phải hoàn tất trong luồng đồng bộ \(đảm bảo sản phẩm tìm được đa ngôn ngữ ngay khi hiển thị công khai\)\.

__AC\-03\.1\.3: __Với trường mô tả chi tiết \(dài hơn\), việc dịch có thể xử lý bất đồng bộ nhưng phải hoàn tất trong SLA tối đa 5 phút kể từ khi đăng sản phẩm\.

__AC\-03\.1\.4: __Nếu dịch vụ dịch thuật gặp lỗi/timeout, hệ thống ghi log và tự động thử lại \(retry\) theo cơ chế backoff, không chặn luồng đăng sản phẩm của Người bán\.

Must Have / 13 pts

__US\-03\.2__

Là Khách hàng chỉ biết tiếng Anh, tôi muốn tìm "pure Robusta coffee" và vẫn thấy sản phẩm cà phê Robusta nguyên chất được đăng bằng tiếng Việt, để tôi không bỏ lỡ sản phẩm phù hợp\.

__AC\-03\.2\.1: __Truy vấn tiếng Anh được đối chiếu qua từ điển dịch song song để mở rộng sang tiếng Việt và tiếng Thái trước khi truy vấn chỉ mục\.

__AC\-03\.2\.2: __Sản phẩm gốc tiếng Việt xuất hiện trong kết quả tìm kiếm khi có token trùng khớp với bản mở rộng từ khóa\.

__AC\-03\.2\.3: __Kết quả trùng khớp qua bản dịch được gắn nhãn nội bộ \(match\_type = translated\) để phục vụ tính điểm ở US\-03\.3\.

Must Have / 8 pts

__US\-03\.3__

Là hệ thống Ranking, tôi cần phân biệt điểm số giữa match trực tiếp và match qua dịch, để sản phẩm đúng ngôn ngữ người dùng luôn được ưu tiên hơn\.

__AC\-03\.3\.1: __Sản phẩm khớp trực tiếp với ngôn ngữ gốc của truy vấn nhận 100% trọng số điểm trùng khớp\.

__AC\-03\.3\.2: __Sản phẩm khớp gián tiếp qua từ dịch nhận 80% trọng số điểm trùng khớp\.

__AC\-03\.3\.3: __Trong mọi trường hợp có cả hai loại kết quả cho cùng một truy vấn, thứ hạng hiển thị phải phản ánh đúng chênh lệch trọng số này \(kết quả 100% luôn đứng trên kết quả 80% nếu các yếu tố khác tương đương\)\.

Must Have / 5 pts

__US\-03\.4__

Là Quản trị viên, tôi muốn xem và hiệu chỉnh bản dịch tự động của một sản phẩm cụ thể, để sửa các trường hợp dịch sai gây hiểu nhầm\.

__AC\-03\.4\.1: __Admin Portal hiển thị bản dịch tự động \(tokens\_en, tokens\_th\) song song với bản gốc tiếng Việt cho từng sản phẩm\.

__AC\-03\.4\.2: __Admin có thể chỉnh sửa thủ công bản dịch; sau khi lưu, chỉ mục được cập nhật lại trong vòng dưới 1 phút mà không cần dịch lại toàn bộ\.

Should Have / 8 pts

__US\-03\.5__

Là Người bán chỉ đăng sản phẩm bằng tiếng Việt, tôi muốn biết sản phẩm của mình đã sẵn sàng hiển thị cho khách tìm bằng tiếng Anh/Thái hay chưa, để yên tâm về khả năng tiếp cận khách hàng quốc tế\.

__AC\-03\.5\.1: __Trang quản lý sản phẩm của Người bán hiển thị trạng thái "Đã lập chỉ mục đa ngôn ngữ" hoặc "Đang xử lý dịch" cho từng sản phẩm\.

__AC\-03\.5\.2: __Trạng thái được cập nhật tự động ngay khi Ingestion Pipeline hoàn tất bước dịch và lập chỉ mục\.

Could Have / 5 pts

## __EPIC\-04: Spellcheck & Synonyms \- Tự Động Sửa Lỗi Chính Tả & Từ Đồng Nghĩa__

*Giúp người dùng vẫn tìm được sản phẩm dù gõ sai hoặc dùng từ địa phương/từ lóng khác nhau\.*

### __Quy tắc nghiệp vụ \(Business Rules\)__

- Khi phát hiện từ khóa gõ sai \(VD: "samsng", "iphne"\), hệ thống tự nhận diện thương hiệu đúng \("samsung", "iphone"\) để tìm kiếm và hiển thị thông báo "Hiển thị kết quả cho: \[Từ khóa đúng\]"\.
- Từ đồng nghĩa: ánh xạ nhiều từ khóa khác nhau về cùng kết quả \(VD: "mì tôm", "mì gói", "mì ăn liền" → cùng danh sách sản phẩm mì ăn liền\)\.

### __User Stories & Acceptance Criteria__

__ID__

__User Story__

__Tiêu Chí Chấp Nhận \(Acceptance Criteria\)__

__Ưu Tiên / Điểm__

__US\-04\.1__

Là Khách hàng gõ nhầm "samsng", tôi muốn hệ thống tự hiểu ý là "samsung" và trả kết quả đúng, để tôi không phải gõ lại\.

__AC\-04\.1\.1: __Với từ khóa lỗi phổ biến nằm trong bộ từ điển sửa lỗi đã duyệt, hệ thống tự động thay thế bằng từ đúng trước khi truy vấn chỉ mục\.

__AC\-04\.1\.2: __Giao diện hiển thị dòng thông báo "Hiển thị kết quả cho: \[từ khóa đúng\]" ngay phía trên danh sách kết quả\.

__AC\-04\.1\.3: __Độ chính xác sửa lỗi đạt tối thiểu 95% trên bộ test\-case gồm các lỗi gõ phổ biến đã được thu thập\.

__AC\-04\.1\.4: __Người dùng có tùy chọn xem lại kết quả với từ khóa gốc họ đã gõ \(link "Tìm với từ khóa gốc"\) nếu không hài lòng với gợi ý sửa\.

Must Have / 8 pts

__US\-04\.2__

Là Khách hàng tìm "mì gói", tôi muốn thấy cùng kết quả với khi tìm "mì ăn liền", để không bỏ lỡ sản phẩm do khác biệt cách gọi\.

__AC\-04\.2\.1: __Các từ khóa được cấu hình là đồng nghĩa \(VD: "mì tôm", "mì gói", "mì ăn liền"\) trả về cùng một tập kết quả sản phẩm\.

__AC\-04\.2\.2: __Việc mở rộng đồng nghĩa áp dụng hai chiều \(tìm bất kỳ từ nào trong nhóm đồng nghĩa đều ra kết quả như nhau\)\.

__AC\-04\.2\.3: __Một từ khóa có thể thuộc nhiều nhóm đồng nghĩa khác nhau tùy theo ngữ cảnh ngành hàng\.

Must Have / 5 pts

__US\-04\.3__

Là Quản trị viên, tôi muốn quản lý danh sách từ đồng nghĩa và từ sửa lỗi qua giao diện quản trị, để cập nhật mà không cần can thiệp kỹ thuật\.

__AC\-04\.3\.1: __Admin Portal cho phép thêm/sửa/xóa cặp từ đồng nghĩa và đề xuất sửa lỗi thông qua giao diện, không cần viết code hay truy vấn database trực tiếp\.

__AC\-04\.3\.2: __Thay đổi được lưu có hiệu lực tức thì trên Search Engine, không cần restart hệ thống hay chờ đợt deploy\.

__AC\-04\.3\.3: __Mọi thay đổi \(thêm/sửa/xóa\) được ghi log kèm người thực hiện và thời gian để phục vụ audit\.

Should Have / 8 pts

__US\-04\.4__

Là Khách hàng gõ từ khóa viết tắt phổ biến \(VD: "đt" cho "điện thoại", "tv" cho "tivi"\), tôi muốn hệ thống hiểu đúng ý định tìm kiếm, để tiết kiệm thời gian nhập liệu\.

__AC\-04\.4\.1: __Bộ từ điển viết tắt phổ biến theo từng ngành hàng được cấu hình sẵn và có thể mở rộng qua Admin Portal\.

__AC\-04\.4\.2: __Khi phát hiện từ viết tắt khớp trong từ điển, hệ thống mở rộng thành từ đầy đủ tương ứng trước khi tìm kiếm, đồng thời không hiển thị thông báo "sửa lỗi" \(khác với luồng spellcheck\) vì đây là mở rộng chủ đích, không phải lỗi gõ\.

Could Have / 5 pts

## __EPIC\-05: Relevance & Ranking \- Thuật Toán Xếp Hạng Kết Quả__

*Sắp xếp kết quả tìm kiếm theo thứ tự ưu tiên hợp lý nhằm tối đa hóa cơ hội bán hàng\.*

### __Quy tắc nghiệp vụ \(Business Rules\)__

- Sản phẩm trùng khớp từ khóa ở Tiêu đề được ưu tiên cao hơn sản phẩm chỉ trùng khớp ở Mô tả chi tiết\.
- Sản phẩm Nổi bật/Sponsored \(trả phí quảng cáo hoặc thuộc chương trình thúc đẩy doanh số\) được ưu tiên đẩy lên đầu nếu có cùng mức độ trùng khớp từ khóa\.
- Tie\-breaker: khi điểm số bằng nhau, sản phẩm còn tồn kho lớn hơn được ưu tiên hiển thị trước\.

### __User Stories & Acceptance Criteria__

__ID__

__User Story__

__Tiêu Chí Chấp Nhận \(Acceptance Criteria\)__

__Ưu Tiên / Điểm__

__US\-05\.1__

Là Khách hàng, tôi muốn sản phẩm khớp từ khóa ở tiêu đề hiện lên trước sản phẩm chỉ khớp ở mô tả, để kết quả đầu tiên luôn sát nhu cầu nhất\.

__AC\-05\.1\.1: __Trọng số điểm cho match tại trường Tiêu đề \(Title\) cao hơn trọng số match tại trường Mô tả \(Description\) theo tỉ lệ đã thống nhất với nghiệp vụ\.

__AC\-05\.1\.2: __Thứ tự hiển thị kết quả phản ánh đúng phân tầng điểm số này trong mọi truy vấn kiểm thử hồi quy \(regression test\)\.

__AC\-05\.1\.3: __Trường hợp một sản phẩm khớp cả ở Tiêu đề và Mô tả, điểm số được cộng dồn hợp lý \(không tính trùng lặp gây lệch thứ hạng\)\.

Must Have / 8 pts

__US\-05\.2__

Là Người bán có sản phẩm Sponsored, tôi muốn sản phẩm của mình được ưu tiên hiển thị khi có cùng mức độ liên quan, để tăng cơ hội bán hàng\.

__AC\-05\.2\.1: __Trong tập kết quả có cùng điểm relevance, sản phẩm được gắn cờ Featured/Sponsored được xếp trước sản phẩm thường\.

__AC\-05\.2\.2: __Cờ Sponsored không được phép ghi đè lên sản phẩm có điểm relevance cao hơn hẳn \(chỉ áp dụng khi mức độ liên quan tương đương, tránh gây phản cảm cho trải nghiệm tìm kiếm\)\.

__AC\-05\.2\.3: __Sản phẩm Sponsored hiển thị kèm nhãn "Được tài trợ"/"Sponsored" rõ ràng để minh bạch với người mua\.

Must Have / 5 pts

__US\-05\.3__

Là hệ thống Ranking, tôi cần xử lý trường hợp điểm số bằng nhau bằng cách ưu tiên tồn kho lớn hơn, để tránh khách hàng click vào sản phẩm hết hàng\.

__AC\-05\.3\.1: __Khi hai sản phẩm có điểm relevance và cờ Featured/Sponsored bằng nhau, sản phẩm có số lượng tồn kho cao hơn được xếp trước\.

__AC\-05\.3\.2: __Sản phẩm hết hàng \(tồn kho = 0\) bị đẩy xuống cuối danh sách kết quả cùng nhóm điểm số, không bị loại hoàn toàn khỏi kết quả tìm kiếm\.

Must Have / 3 pts

__US\-05\.4__

Là Quản trị viên, tôi muốn có khả năng điều chỉnh trọng số các yếu tố xếp hạng \(Title, Description, Sponsored, tồn kho\) mà không cần deploy lại code, để linh hoạt tối ưu theo mùa vụ kinh doanh\.

__AC\-05\.4\.1: __Trọng số ranking được lưu dưới dạng cấu hình tập trung \(config service\), có thể chỉnh qua Admin Portal\.

__AC\-05\.4\.2: __Thay đổi trọng số có hiệu lực trên kết quả tìm kiếm trong vòng dưới 5 phút, kèm khả năng rollback về cấu hình trước đó nếu phát sinh vấn đề\.

Should Have / 8 pts

## __EPIC\-06: Self\-Learning Feedback Loop \- Cơ Chế Học Từ Khóa Tự Động__

*Hệ thống tự thông minh hơn theo thời gian dựa trên hành vi tìm kiếm thực tế, giảm dần tỷ lệ tìm kiếm 0 kết quả\.*

### __Quy tắc nghiệp vụ \(Business Rules\)__

- Tự động ghi nhận các từ khóa tìm kiếm dẫn đến 0 kết quả hoặc từ khóa lạ chưa có trong từ điển\.
- Phân tích định kỳ: nếu là lỗi chính tả của từ có sẵn → tự tạo đề xuất sửa đổi; nếu là từ khóa hoàn toàn mới → tự dịch nghĩa, tìm sản phẩm liên quan và đẩy vào danh sách chờ duyệt\.
- Admin phê duyệt đề xuất trên trang quản trị để cập nhật ngay vào bộ máy tìm kiếm mà không cần khởi động lại hệ thống\.

### __User Stories & Acceptance Criteria__

__ID__

__User Story__

__Tiêu Chí Chấp Nhận \(Acceptance Criteria\)__

__Ưu Tiên / Điểm__

__US\-06\.1__

Là hệ thống, tôi cần ghi nhận mọi truy vấn trả về 0 kết quả kèm ngôn ngữ và tần suất, để làm đầu vào cho vòng lặp học từ khóa\.

__AC\-06\.1\.1: __Mọi truy vấn trả về 0 kết quả được log kèm timestamp, ngôn ngữ phát hiện, và số lần xuất hiện lặp lại\.

__AC\-06\.1\.2: __Dữ liệu log được lưu trữ tối thiểu 90 ngày và có thể truy vấn theo khoảng thời gian phục vụ phân tích\.

__AC\-06\.1\.3: __Dữ liệu sẵn sàng làm đầu vào cho job phân tích định kỳ tại US\-06\.2 mà không cần xử lý \(transform\) thêm\.

Must Have / 5 pts

__US\-06\.2__

Là hệ thống phân tích định kỳ, tôi cần phân loại từ khóa lỗi thành "lỗi chính tả" hoặc "từ khóa mới", để tạo đề xuất phù hợp\.

__AC\-06\.2\.1: __Job batch chạy định kỳ \(đề xuất hàng ngày\) phân loại từng từ khóa lỗi vào một trong hai nhóm: lỗi chính tả của từ có sẵn, hoặc từ khóa hoàn toàn mới\.

__AC\-06\.2\.2: __Việc phân loại dựa trên độ tương đồng \(edit distance/ngữ âm\) với từ điển hiện có, kèm độ tin cậy \(confidence score\) được lưu cùng kết quả\.

__AC\-06\.2\.3: __Với nhóm "lỗi chính tả", hệ thống tự động sinh đề xuất sửa đổi tương ứng để đưa vào hàng chờ duyệt\.

__AC\-06\.2\.4: __Với nhóm "từ khóa mới", hệ thống tự động dịch nghĩa và tìm các sản phẩm có khả năng liên quan nhất dựa trên đối sánh ngữ nghĩa\.

Should Have / 13 pts

__US\-06\.3__

Là Quản trị viên, tôi muốn xem danh sách đề xuất sửa lỗi/từ mới chờ duyệt và phê duyệt hoặc từ chối chỉ bằng vài thao tác, để cập nhật từ điển nhanh chóng\.

__AC\-06\.3\.1: __Admin Portal hiển thị danh sách đề xuất kèm ngữ cảnh: từ khóa gốc, đề xuất, tần suất xuất hiện, độ tin cậy, và sản phẩm liên quan được gợi ý\.

__AC\-06\.3\.2: __Admin có thể phê duyệt hoặc từ chối từng đề xuất bằng một thao tác click, có thể xử lý hàng loạt \(bulk approve/reject\)\.

__AC\-06\.3\.3: __Sau khi Admin phê duyệt, thay đổi có hiệu lực trên Search Engine trong thời gian thực \(dưới 1 phút\), không cần deploy lại hệ thống\.

__AC\-06\.3\.4: __Đề xuất bị từ chối được lưu lại lịch sử để tránh hệ thống đề xuất lại cùng một từ khóa trong ngắn hạn\.

Should Have / 8 pts

__US\-06\.4__

Là Quản trị viên, tôi muốn theo dõi biểu đồ xu hướng Zero\-Results Rate theo thời gian, để đánh giá hiệu quả của vòng lặp tự học\.

__AC\-06\.4\.1: __Admin Portal hiển thị biểu đồ Zero\-Results Rate theo ngày/tuần/tháng, có thể lọc theo ngôn ngữ\.

__AC\-06\.4\.2: __Biểu đồ thể hiện rõ mốc trước/sau khi một đề xuất được phê duyệt để đánh giá tác động\.

Could Have / 5 pts

# __5\. Yêu Cầu Phi Chức Năng \(Non\-Functional Requirements\)__

__Hạng mục__

__Yêu cầu__

__Ghi chú triển khai__

Hiệu năng \(Performance\)

Search < 50ms, Autocomplete < 5ms, kể cả trong flash sale

Cần caching layer, chỉ mục tối ưu \(VD: inverted index / search engine chuyên dụng\); không được làm chậm luồng thanh toán/đặt hàng

Khả năng chịu tải \(Scalability\)

Ổn định ở 500 lượt truy cập đồng thời tại tải đỉnh

Thiết kế có khả năng horizontal scaling; cần load\-test trước mỗi campaign lớn

Độ tin cậy & Cô lập sự cố \(Resilience\)

Search Engine hoạt động độc lập; nếu DB tìm kiếm gặp sự cố vẫn hiển thị UI cơ bản hoặc kết quả đệm gần nhất

Áp dụng circuit breaker, fallback cache, graceful degradation; không ảnh hưởng ứng dụng chính

Đa đối tác \(Multi\-tenancy\)

Phục vụ nhiều đối tác/phân vùng thị trường trên cùng hạ tầng, dữ liệu cô lập giữa các đối tác

Thiết kế chỉ mục có tenant\_id/partition riêng; kiểm soát truy cập chặt chẽ giữa các tenant

Bảo mật dữ liệu

Dữ liệu sản phẩm của đối tác này không bị lộ sang đối tác khác

Áp dụng row\-level/index\-level isolation, audit log truy cập

Khả năng mở rộng ngôn ngữ

Kiến trúc cho phép bổ sung ngôn ngữ mới ngoài Việt/Anh/Thái trong tương lai

Thiết kế module hóa Segmenter & Translation Dictionary theo plugin

# __6\. Kế Hoạch Triển Khai Theo Agile \(Release & Sprint Roadmap\)__

Dự án áp dụng mô hình Scrum với Sprint 2 tuần\. Product Backlog được ưu tiên hóa theo giá trị nghiệp vụ \(business value\), mức độ phụ thuộc kỹ thuật, và nhãn MoSCoW đã gắn ở từng User Story \(mục 4\)\. Nếu triển khai tuần tự toàn bộ 25 User Story \(Must \+ Should \+ Could Have\) với một đội \(1 Scrum team, velocity trung bình\), tổng khối lượng công việc tương đương khoảng 10 Sprint \(~20 tuần\) — mục 6\.1 dưới đây phân tích lý do và đề xuất phương án rút ngắn thời gian ra thị trường \(Time\-to\-Market\)\.

## __6\.1\. Đánh giá độ dài lộ trình & Đề xuất rút ngắn__

10 Sprint là con số của kịch bản "làm toàn bộ phạm vi \(Must \+ Should \+ Could Have\) tuần tự bằng một đội duy nhất" — đây là kịch bản an toàn nhất về rủi ro nhưng chậm nhất về thời gian ra mắt\. Trên thực tế, không cần chờ hoàn thành 100% phạm vi mới go\-live\. Ba phương án rút ngắn được đề xuất như sau:

__Phương án__

__Cách thực hiện__

__Thời gian dự kiến__

__Đánh đổi \(Trade\-off\)__

A\. MVP\-First \(khuyến nghị\)

Chỉ triển khai các User Story gắn nhãn Must Have \(14 stories\) cho lần go\-live đầu tiên; các Should/Could Have chuyển sang giai đoạn 2 ngay sau khi ra mắt

~6 Sprint \(12 tuần\) để go\-live MVP; 3\-4 Sprint tiếp theo \(song song hậu ra mắt\) để hoàn thiện phần Should/Could Have

Ra thị trường nhanh hơn ~40%, thu thập phản hồi thực tế sớm; đổi lại một số tính năng nâng cao \(quản trị nâng cao, gợi ý danh mục, dashboard xu hướng\.\.\.\) chưa có ngay khi ra mắt

B\. Hai đội song song \(Parallel Squads\)

Tách 2 Squad làm việc song song theo cụm Epic độc lập: Squad A phụ trách EPIC\-02 \+ EPIC\-05 \+ EPIC\-01; Squad B phụ trách EPIC\-03 \+ EPIC\-04 \+ EPIC\-06

~6 Sprint \(12 tuần\) cho toàn bộ phạm vi Must \+ Should Have

Rút ngắn ~40% thời gian nhưng cần thêm nhân sự/ngân sách cho Squad thứ hai và chi phí điều phối liên đội

C\. Giữ nguyên phạm vi, giữ 1 đội

Triển khai tuần tự toàn bộ 25 User Story như hiện trạng

10 Sprint \(20 tuần\)

Rủi ro thấp nhất, không cần thêm nguồn lực, nhưng chậm nhất về Time\-to\-Market và trễ vòng thu thập phản hồi thị trường

Khuyến nghị: chọn Phương án A \(MVP\-First\) làm lộ trình chính thức — vừa đảm bảo ra mắt trong khoảng 12 tuần với đầy đủ giá trị cốt lõi \(tìm kiếm đa ngôn ngữ, sửa lỗi chính tả, xếp hạng, autocomplete cơ bản\), vừa giữ được mô hình 1 đội duy nhất dễ quản lý\. Phương án B chỉ nên áp dụng nếu tổ chức có sẵn ngân sách cho đội thứ hai và ưu tiên tuyệt đối về tốc độ\.

## __6\.2\. Lộ trình chi tiết theo Phương án A \(MVP\-First\)__

__Release__

__Phạm vi__

__Mục tiêu nghiệp vụ__

__Sprint dự kiến__

Release 1 \(MVP\) \- Nền tảng Tìm Kiếm Cốt Lõi

Toàn bộ US gắn nhãn Must Have thuộc EPIC\-02 \(Segmenter\) và EPIC\-05 \(Ranking\)

Có bộ máy tìm kiếm hoạt động ổn định, tách từ đúng 3 ngôn ngữ, xếp hạng đúng theo Title/Description/Sponsored/tồn kho, đáp ứng NFR về hiệu năng

Sprint 1 \- 2

Release 2 \(MVP\) \- Trải Nghiệm Tìm Kiếm Thông Minh

US Must Have thuộc EPIC\-01 \(Autocomplete\) và EPIC\-04 \(Spellcheck & Synonyms\)

Giảm zero\-results do lỗi chính tả, tăng tốc độ nhập liệu, cải thiện UX tìm kiếm

Sprint 3 \- 4

Release 3 \(MVP\) \- Tìm Kiếm Đa Ngôn Ngữ & Go\-live

US Must Have thuộc EPIC\-03 \(Translation Search\) và US\-06\.1 \(ghi nhận zero\-results\) thuộc EPIC\-06

Hỗ trợ tìm kiếm chéo Việt\-Anh\-Thái cho luồng nghiệp vụ cốt lõi; sẵn sàng ra mắt \(go\-live\) với đầy đủ giá trị Must Have

Sprint 5 \- 6

Release 4 \(Phase 2\) \- Hoàn Thiện & Tự Động Hóa

Toàn bộ US còn lại gắn nhãn Should Have và Could Have \(quản trị nâng cao, phân loại tự động, dashboard, gợi ý danh mục\.\.\.\)

Nâng cao trải nghiệm quản trị, tự động hóa vòng lặp học từ khóa, tối ưu liên tục dựa trên dữ liệu thực tế sau go\-live

Sprint 7 \- 9 \(song song/ngay sau go\-live\)

## __6\.3\. Nghi thức Scrum áp dụng__

- Sprint Planning: đầu mỗi Sprint, đội chọn User Story từ Backlog theo độ ưu tiên MoSCoW và năng lực \(velocity\)\.
- Daily Standup: đồng bộ tiến độ, phát hiện sớm rủi ro/blocker liên quan đến các Epic trên\.
- Sprint Review: demo tính năng hoàn thành cho Product Owner & stakeholder \(đại diện Người bán/Quản trị viên nếu cần\)\.
- Sprint Retrospective: cải tiến quy trình, đặc biệt với các Epic phức tạp như Translation Search và Self\-Learning\.
- Backlog Refinement: định kỳ làm rõ & re\-estimate các User Story chưa triển khai, đặc biệt khi có dữ liệu thực tế từ vòng lặp tự học \(EPIC\-06\) hoặc khi chuyển sang Release 4\.

# __7\. Giả Định & Ràng Buộc \(Assumptions & Constraints\)__

## __7\.1\. Giả định \(Assumptions\)__

- Đã có sẵn từ điển dịch cơ bản Việt\-Anh\-Thái hoặc dịch vụ máy dịch \(Machine Translation API\) để bootstrap dữ liệu ban đầu cho EPIC\-03\.
- Dữ liệu sản phẩm hiện có được chuẩn hóa đủ để phục vụ Ingestion Pipeline \(tiêu đề, mô tả, tồn kho, cờ Featured/Sponsored\)\.
- Hạ tầng cho phép triển khai công nghệ search chuyên dụng \(VD: Elasticsearch/OpenSearch hoặc tương đương\) đáp ứng yêu cầu độ trễ\.
- Đội ngũ Admin sẵn sàng tham gia quy trình phê duyệt đề xuất định kỳ để vòng lặp tự học \(EPIC\-06\) phát huy hiệu quả\.

## __7\.2\. Ràng buộc \(Constraints\)__

- Ngân sách & thời gian triển khai theo lộ trình Release đã thống nhất với Business Sponsor\.
- Search Engine không được phép ảnh hưởng đến hiệu năng của luồng thanh toán/đặt hàng trong mọi trường hợp, kể cả khi gặp sự cố\.
- Giai đoạn 1 chỉ hỗ trợ 3 ngôn ngữ: Việt, Anh, Thái\.

# __8\. Rủi Ro & Biện Pháp Giảm Thiểu \(Risks & Mitigation\)__

__Rủi ro__

__Mức độ ảnh hưởng__

__Biện pháp giảm thiểu__

Độ trễ dịch máy/dịch từ điển không đáp ứng SLA ingestion

Cao

Kết hợp từ điển tĩnh \(fast\-path\) với dịch máy bất đồng bộ; ưu tiên xử lý đồng bộ cho các trường quan trọng nhất \(tiêu đề\)

Tokenizer tiếng Thái/Việt tách sai gây kết quả lệch nghĩa

Cao

Xây bộ test\-set đánh giá độ chính xác tách từ theo từng Sprint; thu thập phản hồi qua EPIC\-06 để tinh chỉnh liên tục

Quá tải hệ thống trong flash sale vượt 500 concurrent users

Trung bình

Load\-test định kỳ trước mỗi campaign; auto\-scaling & caching layer theo NFR mục 5

Admin không kịp phê duyệt đề xuất, làm tồn đọng zero\-results

Trung bình

Thiết lập SLA nội bộ cho quy trình duyệt; cân nhắc auto\-approve với đề xuất có độ tin cậy rất cao \(confidence score ngưỡng cao\)

Rò rỉ dữ liệu sản phẩm giữa các đối tác \(multi\-tenancy\)

Cao

Kiểm thử bảo mật cô lập tenant ở mọi Sprint có thay đổi liên quan chỉ mục; audit log định kỳ

# __9\. Định Nghĩa Hoàn Thành \(Definition of Done\)__

Một User Story được xem là Hoàn thành \(Done\) khi đáp ứng đầy đủ các điều kiện sau:

1. Code đã được review và merge vào nhánh chính, tuân thủ coding convention của dự án\.
2. Tất cả Acceptance Criteria của User Story được kiểm thử và pass \(unit test, integration test\)\.
3. Đáp ứng các chỉ tiêu hiệu năng liên quan tại mục 5 \(nếu áp dụng\), được xác nhận qua kiểm thử tải\.
4. Đã qua kiểm thử QA trên môi trường Staging, không còn lỗi mức độ Critical/Blocker\.
5. Tài liệu liên quan \(API doc, hướng dẫn vận hành Admin Portal nếu có\) được cập nhật\.
6. Được Product Owner nghiệm thu trong Sprint Review\.

# __10\. Bảng Thuật Ngữ \(Glossary\)__

__Thuật ngữ__

__Giải thích__

Autocomplete

Chức năng gợi ý từ khóa tức thì khi người dùng đang nhập liệu

Segmenter / Tokenizer

Bộ phân tách chuỗi văn bản thành các đơn vị từ \(token\) có nghĩa để lập chỉ mục và đối sánh

Ingestion Pipeline

Luồng xử lý dữ liệu sản phẩm từ lúc Seller đăng tải đến khi được lập chỉ mục tìm kiếm

Query\-time Expansion

Kỹ thuật mở rộng từ khóa truy vấn \(VD: dịch sang ngôn ngữ khác\) tại thời điểm tìm kiếm

Relevance Score

Điểm số thể hiện mức độ liên quan giữa truy vấn và sản phẩm, dùng để xếp hạng kết quả

Sponsored / Featured Product

Sản phẩm được trả phí quảng cáo hoặc thuộc chương trình thúc đẩy doanh số, được ưu tiên hiển thị

Zero\-Results Rate

Tỷ lệ truy vấn tìm kiếm trả về không có kết quả nào

Story Points

Đơn vị ước lượng độ phức tạp/khối lượng công việc của một User Story trong Scrum

MoSCoW

Kỹ thuật ưu tiên hóa yêu cầu: Must have, Should have, Could have, Won't have

# __11\. Phê Duyệt Tài Liệu \(Sign\-off\)__

Tài liệu này cần được các bên liên quan dưới đây rà soát và phê duyệt trước khi chuyển sang giai đoạn lập Product Backlog chi tiết và Sprint Planning\.

__Vai trò__

__Họ tên__

__Chữ ký__

__Ngày duyệt__

Product Owner

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

Project Manager / Scrum Master

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

Trưởng nhóm Kỹ thuật \(Tech Lead\)

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

Đại diện Kinh doanh \(Business Sponsor\)

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

