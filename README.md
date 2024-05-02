# 1. Elasticsearch:
## Thông tin cơ bản:
- Elasticsearch được xây dựng dựa trên công nghệ Apache Lucene, là một thư viện tìm kiếm cao cấp. Nó là một phần của Elastic Stack, bao gồm Elasticsearch, Logstash, và Kibana, cùng với Beats.
- Elasticsearch cho phép lưu trữ, tìm kiếm và phân tích dữ liệu lớn nhanh chóng. Nó thường được sử dụng để hỗ trợ các ứng dụng có khả năng tìm kiếm mạnh mẽ, bao gồm tìm kiếm trang web nội bộ và phân tích log.
- Elasticsearch có thể mở rộng ngang dễ dàng, hỗ trợ việc phân tán dữ liệu và xử lý qua nhiều nút, giúp tăng khả năng chịu lỗi và khả năng mở rộng.
- Elasticsearch sử dụng JSON qua HTTP cho việc nhập dữ liệu, cập nhật và truy vấn. Nó hỗ trợ các truy vấn phức tạp, bao gồm cả truy vấn dựa trên cú pháp và tìm kiếm theo khoảng.
- Ngoài chức năng tìm kiếm, Elasticsearch cũng cung cấp các công cụ phân tích mạnh mẽ, cho phép người dùng hiểu và phân tích dữ liệu của họ một cách sâu sắc.
- Elasticsearch được sử dụng rộng rãi trong các lĩnh vực như quản lý log hệ thống, phân tích bảo mật, tìm kiếm trang web, và nhiều ứng dụng phân tích dữ liệu khác.

## Ưu điểm:
- Hiệu năng cao: Elasticsearch cung cấp khả năng tìm kiếm nhanh chóng và hiệu quả, ngay cả với lượng dữ liệu lớn, nhờ cơ chế lập chỉ mục và tìm kiếm dựa trên Apache Lucene.
- Khả năng mở rộng ngang: Elasticsearch có thể mở rộng một cách linh hoạt bằng cách thêm nhiều nút vào cluster, giúp cải thiện hiệu năng và khả năng chịu lỗi.
- Hỗ trợ phân tán: Dữ liệu trong Elasticsearch có thể được tự động phân chia thành nhiều shards khác nhau, và mỗi shard có thể có nhiều bản sao. Điều này giúp cải thiện độ tin cậy và khả năng chịu lỗi.
- Tích hợp dễ dàng: Elasticsearch hỗ trợ nhiều ngôn ngữ lập trình thông qua các API RESTful, làm cho việc tích hợp vào các ứng dụng hiện có trở nên dễ dàng hơn.
- Trực quan hóa dữ liệu: Với Kibana, Elasticsearch cho phép người dùng tạo các dashboard trực quan để hiểu sâu hơn về dữ liệu của họ.
Phân tích thời gian thực: Elasticsearch hỗ trợ phân tích thời gian thực, cho phép người dùng nhận được thông tin ngay lập tức từ dữ liệu của họ.

## Nhược điểm:
- Quản lý tài nguyên: Elasticsearch có thể yêu cầu một lượng lớn tài nguyên hệ thống, đặc biệt là RAM, để hoạt động hiệu quả, điều này có thể dẫn đến chi phí cao hơn.
- Độ phức tạp trong quản lý cluster: Quản lý và tối ưu cluster Elasticsearch, đặc biệt là trong các môi trường sản xuất lớn, có thể rất phức tạp và yêu cầu kiến thức chuyên môn.
- Cập nhật dữ liệu: Mặc dù Elasticsearch rất nhanh cho việc tìm kiếm, nhưng việc cập nhật dữ liệu (như thêm hoặc sửa đổi dữ liệu) có thể chậm hơn so với các hệ thống cơ sở dữ liệu truyền thống.
- Phức tạp về transactional: Elasticsearch không phải là lựa chọn tốt nhất cho các ứng dụng yêu cầu giao dịch với tính toàn vẹn và tính nhất quán cao, vì nó không hỗ trợ như các cơ sở dữ liệu quan hệ.
- Không đa dạng về kiểu định dạng: Elasticsearch không hỗ trợ xử lý request và response bằng nhiều định dạng (chỉ dùng JSON) so với một search engine khác cũng xây dựng dựa trên Lucene như Apache Solr (hỗ trợ JSON, CSV, XML).
- Cấu hình và tinh chỉnh: Việc tinh chỉnh cấu hình cho hiệu suất tối ưu có thể rất thách thức và yêu cầu sự hiểu biết sâu về cách vận hành của Elasticsearch.

## Về bảo mật:

### Xác thực và Phân quyền trong Elasticsearch
Xác thực (Authentication): Elasticsearch hỗ trợ các phương thức xác thực nhiều dạng, bao gồm:
- Basic Authentication: Sử dụng tên người dùng và mật khẩu.
- API Keys: Cung cấp khóa API cho các dịch vụ và ứng dụng mà không cần tiết lộ tài khoản người dùng chính.
- SAML, OpenID Connect và Kerberos: Hỗ trợ Single Sign-On (SSO) cho các tổ chức sử dụng các giải pháp xác thực dựa trên chuẩn.
Phân quyền (Authorization): Elasticsearch cho phép kiểm soát chi tiết các quyền truy cập đối với dữ liệu và chức năng:
- Role-Based Access Control (RBAC): Quản lý quyền truy cập dựa trên vai trò của người dùng.
- Attribute-Based Access Control (ABAC): Điều khiển quyền truy cập dựa trên các thuộc tính của người dùng hoặc tài nguyên.
- Field- and Document-Level Security: Giới hạn quyền truy cập đến cấp độ trường dữ liệu hoặc tài liệu cụ thể.
Bảo mật tại các lớp: Elasticsearch cũng hỗ trợ các cấu hình bảo mật ở tầng vận chuyển và tầng HTTP, như SSL/TLS, để mã hóa dữ liệu truyền giữa các client và server, nhằm bảo vệ chống lại các cuộc tấn công man-in-the-middle.

Note: Tính năng bảo mật trên chỉ được cung cấp với các pack mất phí và các bản miễn phí không được cung cấp

## So sánh với RDBMS:

### a. Mục đích và Khả năng

- Elasticsearch: Được thiết kế chủ yếu cho các ứng dụng tìm kiếm và phân tích dữ liệu với khả năng xử lý và trả về kết quả gần như thời gian thực.
Tốt cho việc xử lý dữ liệu không có cấu trúc hoặc bán cấu trúc, như văn bản, log và dữ liệu đa phương tiện.

- RDBMS: Được thiết kế để xử lý các giao dịch có tính toàn vẹn và nhất quán cao, sử dụng mô hình dữ liệu quan hệ.
Phù hợp với các ứng dụng yêu cầu tính toàn vẹn dữ liệu, hỗ trợ các giao dịch ACID (Atomicity, Consistency, Isolation, Durability) và bảo mật cao.

### b. Cấu trúc Dữ liệu

- Elasticsearch: Dữ liệu được chỉ mục theo cách tối ưu cho tìm kiếm nhanh. Sử dụng các chỉ mục đảo ngược để cải thiện hiệu quả tìm kiếm.
Không có cấu trúc dữ liệu quan hệ chặt chẽ, và không hỗ trợ truy vấn phức tạp như join giữa các bảng.

- RDBMS: Dữ liệu được tổ chức thành bảng và các mối quan hệ được xác định rõ ràng thông qua khóa ngoại.
Hỗ trợ truy vấn dữ liệu phức tạp, bao gồm các thao tác như joins, subqueries, và các hàm tập hợp.

### c. Khả năng Mở rộng

- Elasticsearch: Mở rộng ngang dễ dàng, phù hợp cho việc xử lý khối lượng dữ liệu lớn và phân tán trên nhiều máy chủ.
Tối ưu cho việc đọc dữ liệu, nhưng việc cập nhật và xóa có thể không hiệu quả bằng.

- RDBMS: Mở rộng theo chiều dọc, thường đòi hỏi phần cứng mạnh hơn khi dữ liệu tăng lên.
Hiệu quả cho việc cập nhật và xử lý giao dịch, nhưng có thể gặp khó khăn trong việc mở rộng ngang khi dữ liệu tăng lớn.

### d. Truy vấn và Phân tích

- Elasticsearch: Tối ưu cho các truy vấn tìm kiếm full-text và phân tích dữ liệu thời gian thực.
Hỗ trợ các truy vấn phức tạp dựa trên dữ liệu text và cung cấp kết quả gần như ngay lập tức.

- RDBMS: Hỗ trợ truy vấn SQL, một ngôn ngữ truy vấn mạnh mẽ và phổ biến, cho phép truy vấn dữ liệu chính xác và đa dạng.
Không chuyên cho tìm kiếm full-text và có thể cần các extension hoặc công cụ bên ngoài để cải thiện khả năng này.

### e. Transaction và Bảo mật

- Elasticsearch: Không hỗ trợ các transactions ACID truyền thống.
Cung cấp tính năng bảo mật như xác thực và phân quyền qua các mô-đun như X-Pack.

- RDBMS: Hỗ trợ đầy đủ các transactions ACID, đảm bảo tính toàn vẹn và nhất quán của dữ liệu.
Tính năng bảo mật mạnh mẽ, hỗ trợ nhiều cấp độ phân quyền và kiểm soát truy cập.

## Sơ lược về Logstash và Kibana

### Logstash
Logstash là một công cụ tải nhập dữ liệu nguồn mở cho phép bạn thu thập dữ liệu từ các nguồn khác nhau, chuyển đổi dữ liệu và gửi dữ liệu tới điểm đích bạn muốn. Với các bộ lọc được tạo sẵn và hỗ trợ hơn 200 phần bổ trợ, Logstash cho phép người dùng dễ dàng tải nhập dữ liệu đến từ bất kỳ nguồn dữ liệu hay thuộc loại dữ liệu nào. 

Logstash là một quy trình xử lý dữ liệu phía máy chủ, nguồn mở, gọn nhẹ cho phép bạn thu nhập dữ liệu từ các nguồn khác nhau, chuyển đổi dữ liệu nhanh chóng và gửi dữ liệu tới điểm đích bạn muốn. Logstash thường được sử dụng như một đường ống dữ liệu cho Elasticsearch, một công cụ phân tích và tìm kiếm nguồn mở. Bởi vì được tích hợp chặt chẽ với Elasticsearch, khả năng xử lý bản ghi mạnh mẽ và hơn 200 phần bổ trợ nguồn mở được tạo sẵn có thể giúp bạn dễ dàng lập chỉ mục cho dữ liệu của mình, Logstash là một lựa chọn phổ biến cho hoạt động tải dữ liệu vào Elasticsearch.

*Các đặc điểm nổi bật của Logstash:*
- Thu thập Dữ liệu: Logstash có khả năng thu thập dữ liệu từ nhiều nguồn khác nhau, bao gồm hệ thống tệp, thiết bị lưu trữ, và giao diện mạng.
- Đa dạng input: Hỗ trợ nhiều loại ninput, bao gồm tệp, syslog, redis, và nhiều hơn nữa.
- Filter: Cung cấp các bộ lọc mạnh mẽ để biến đổi dữ liệu khi được xử lý, ví dụ như thay đổi dữ liệu dựa trên nội dung, loại bỏ thông tin không cần thiết, thêm trường dữ liệu mới, và phân tích cú pháp các định dạng dữ liệu phức tạp.
- Output: Có thể chuyển dữ liệu đã xử lý đến một hoặc nhiều điểm đích, chẳng hạn như Elasticsearch, file, datadog, graphite, và nhiều hệ thống khác.
- Plugin: Có một hệ thống plugin phong phú, cho phép mở rộng chức năng mà không cần sửa đổi mã nguồn cốt lõi của Logstash.

### Kibana
Kibana là một công cụ hiển thị trực quan và khám phá dữ liệu được sử dụng trong những trường hợp phân tích nhật ký và chuỗi thời gian, giám sát ứng dụng và thông tin kinh doanh. Công cụ này cung cấp những tính năng mạnh mẽ, dễ sử dụng như biểu đồ tần suất, biểu đồ đường, biểu đồ tròn, biểu đồ nhiệt và hỗ trợ không gian địa lý được tích hợp sẵn. Ngoài ra, công cụ này còn cung cấp khả năng tích hợp chặt chẽ với Elasticsearch, một công cụ phân tích và tìm kiếm phổ biến, khiến Kibana trở thành lựa chọn hàng đầu cho hoạt động hiển thị trực quan dữ liệu được lưu trữ trong Elasticsearch.

*Các đặc điểm nổi bật của Kibana:*
- Trực quan hóa Dữ liệu: Kibana cung cấp một loạt các loại biểu đồ, bảng, và bản đồ để trực quan hóa dữ liệu, bao gồm biểu đồ cột, biểu đồ dòng, biểu đồ tròn, bản đồ nhiệt và nhiều hơn nữa.
- Tìm kiếm và Phân tích: Cho phép tạo và quản lý các truy vấn phức tạp, phân tích và khám phá dữ liệu trong thời gian thực.
- Dashboard: Người dùng có thể tạo các dashboard tùy chỉnh bằng cách sử dụng các thành phần trực quan khác nhau, giúp cung cấp cái nhìn tổng quan và sâu sắc về dữ liệu.
- Quản lý Elasticsearch: Kibana cũng bao gồm các công cụ quản lý cho Elasticsearch, như quản lý chỉ mục, cấu hình nút, và kiểm tra trạng thái cluster.
- Dev Tools: Kibana cung cấp các công cụ dành cho nhà phát triển để thử nghiệm truy vấn và xem các tài liệu Elasticsearch.

## Tham khảo cài đặt cấu hình và sử dụng:
- https://viblo.asia/p/tich-hop-elasticsearch-va-kibana-vao-docker-compose-Az45bymqlxY
