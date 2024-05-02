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
- https://viblo.asia/p/elasticsearch-kibana-logstash-tong-quan-cai-dat-va-su-dung-RQqKLRn6l7z
- https://viblo.asia/p/tich-hop-elasticsearch-va-kibana-vao-docker-compose-Az45bymqlxY

# 2. Elastic Observability:

## Thông tin cơ bản:
Elastic Observability là một phần của bộ công cụ Elastic Stack, được thiết kế để cung cấp một giải pháp toàn diện về quan sát, phân tích và theo dõi các hệ thống và ứng dụng. Elastic Observability kết hợp các dữ liệu từ logs, metrics, và traces để cung cấp cái nhìn toàn cảnh và sâu sắc về hiệu suất và trạng thái của cả hạ tầng IT và các ứng dụng kinh doanh. Đây là một công cụ hữu ích cho các nhóm DevOps, SRE (Site Reliability Engineering) và IT operations để theo dõi và giải quyết các vấn đề hệ thống.

## Các Thành Phần Chính tạo lên Elastic Observability
- **Elasticsearch:** Là trung tâm lưu trữ và phân tích dữ liệu, Elasticsearch cho phép quản lý và truy xuất dữ liệu logs, metrics, và traces một cách hiệu quả.
- **Beats:** Là một nhóm các nhà thu thập dữ liệu nhẹ, mỗi loại Beat có chức năng thu thập dữ liệu đặc thù từ các nguồn khác nhau. Ví dụ, Filebeat thu thập log files, Metricbeat thu thập metrics từ hệ thống và các ứng dụng, Packetbeat phân tích lưu lượng mạng, và Heartbeat để kiểm tra tính khả dụng của dịch vụ.
- **APM Server:** Là một phần mềm giám sát hiệu suất ứng dụng, nó thu thập dữ liệu từ các ứng dụng và gửi chúng đến Elasticsearch. Điều này cho phép người dùng theo dõi các yêu cầu của ứng dụng, phản ứng từ cơ sở dữ liệu và gọi dịch vụ bên ngoài.
- **Kibana:** Được sử dụng để trực quan hóa và phân tích dữ liệu thu thập được. Kibana cung cấp dashboards sẵn có và khả năng tùy chỉnh mạnh mẽ, cho phép người dùng tạo ra các biểu đồ, bản đồ nhiệt và báo cáo tùy biến dựa trên dữ liệu thu được.

## Tính Năng của Elastic Observability
- **Unified View:** Tập hợp dữ liệu từ logs, metrics và APM traces để cung cấp cái nhìn toàn diện về hệ thống. Điều này giúp nhận diện nhanh chóng nguyên nhân gốc rễ của các vấn đề.
- **Real-time Monitoring and Alerting:** Cho phép thiết lập các cảnh báo dựa trên các điều kiện cụ thể. Người dùng có thể được thông báo ngay lập tức khi có sự kiện quan trọng hoặc khi hệ thống hoạt động không như mong đợi.
- **Scalability:** Hệ thống có khả năng mở rộng cao, phù hợp cho cả doanh nghiệp nhỏ lẫn các tổ chức lớn. Elastic Observability có thể xử lý lượng dữ liệu lớn từ nhiều nguồn khác nhau một cách hiệu quả.
- **Troubleshooting and Root Cause Analysis:** Cung cấp các công cụ để phân tích sâu và xác định nguyên nhân của các sự cố, từ đó giúp giảm thời gian để giải quyết vấn đề.
- **Integration and Extensibility:** Dễ dàng tích hợp với nhiều công nghệ và dịch vụ khác, bao gồm cloud services, containers và orchestration platforms như Kubernetes, cho phép quản lý và giám sát trong một môi trường đa dạng.
  
**Elastic Observability** là một giải pháp mạnh mẽ cho việc giám sát và quản lý hiệu suất ứng dụng và hệ thống, giúp các tổ chức duy trì sự ổn định và hiệu quả của hạ tầng CNTT.

## Sơ lược về APM Server và Beats

### APM Server
APM Server là một thành phần của Elastic Stack, chịu trách nhiệm thu thập dữ liệu từ các ứng dụng để phân tích hiệu suất (Application Performance Monitoring). Nó làm cầu nối giữa các ứng dụng và Elasticsearch, giúp lưu trữ và phân tích dữ liệu hiệu suất ứng dụng. APM Server thu thập các loại dữ liệu như requests, responses, exceptions, và transactions từ các ứng dụng để cung cấp cái nhìn tổng quan về hiệu suất và giúp xác định các vấn đề tiềm ẩn.

*Các tính năng chính của APM Server:*
- **Tự động phát hiện lỗi:** Phân tích các giao dịch và lỗi để xác định các vấn đề tiềm ẩn trong ứng dụng.
- **Real-Time Profiling:** Giám sát hiệu suất của ứng dụng trong thời gian thực, cung cấp dữ liệu chi tiết về các hàm gọi và thời gian thực hiện.
- **Hỗ trợ Ngôn Ngữ Đa Dạng:** Tương thích với nhiều ngôn ngữ lập trình phổ biến như Java, .NET, Ruby, Python, JavaScript, và Go.
- **Tích hợp với Kibana:** Sử dụng Kibana để trực quan hóa dữ liệu APM, cho phép tạo các báo cáo và dashboard chi tiết về hiệu suất ứng dụng.

### Beats
Beats là một bộ sưu tập các data shippers đơn giản mà bạn có thể cài đặt làm agent trên các máy chủ để gửi các loại dữ liệu cụ thể đến Elasticsearch. Mỗi Beat được tối ưu hóa để thu thập một loại dữ liệu khác nhau, từ log files, metrics cho đến network data.

*Các loại Beats phổ biến bao gồm:*
- **Filebeat:** Thu thập và chuyển tiếp log files.
- **Metricbeat:** Thu thập metrics từ hệ thống và các dịch vụ.
- **Packetbeat:** Thu thập và phân tích lưu lượng mạng.
- **Heartbeat:** Thực hiện các kiểm tra tính khả dụng của dịch vụ từ xa.
- **Auditbeat:** Thu thập dữ liệu về truy cập và các thay đổi trên hệ thống tệp để giám sát bảo mật.
- **Functionbeat:** Cho phép thu thập dữ liệu từ các dịch vụ đám mây như AWS Lambda.

*Các tính năng chính của Beats:*
- **Nhẹ và Hiệu Quả:** Các Beats được thiết kế để sử dụng ít tài nguyên hệ thống, cho phép chúng hoạt động hiệu quả trên các môi trường sản xuất.
- **Tích hợp Sẵn:** Dễ dàng tích hợp với Elasticsearch và Logstash để phân tích và xử lý dữ liệu thêm.
- **Cấu hình Linh Hoạt:** Cho phép tùy chỉnh đáng kể trong việc thu thập dữ liệu, bao gồm thời gian thu thập, loại dữ liệu và cách xử lý.
- **Bảo Mật:** Hỗ trợ mã hóa SSL/TLS và xác thực để bảo đảm an toàn khi truyền dữ liệu.

## Tài liệu tham khảo:
- https://viblo.asia/p/elastic-stack-xay-dung-trien-khai-giam-sat-va-quan-ly-tap-trung-request-logs-theo-kien-truc-microservices-RnB5pAnDKPG

# 3. Elastic Security
**Elastic Security** là một giải pháp toàn diện được thiết kế để phát hiện, điều tra và phản hồi trước các mối đe dọa an ninh mạng trong thời gian thực. Nó là một phần của Elastic Stack và hợp nhất các chức năng của SIEM (Security Information and Event Management) và EDR (Endpoint Detection and Response) để cung cấp bảo mật mở rộng từ các điểm cuối đến các mạng và điện toán đám mây.

*Các tính năng chính của Elastic Security:*
**Tích hợp dữ liệu an ninh:** 
- Thu thập dữ liệu đa nguồn: Elastic Security có thể tích hợp dữ liệu từ logs, metrics, network traffic, và các endpoint, tạo nên một hệ thống phòng thủ chắc chắn.
- Normalization: Dữ liệu từ nhiều nguồn khác nhau được chuẩn hóa để dễ dàng phân tích và truy vấn.

**Phát hiện mối đe dọa:**
- Phát hiện dựa trên quy tắc và hành vi: Sử dụng một bộ sưu tập lớn các quy tắc phát hiện được cập nhật liên tục để nhận diện mối đe dọa dựa trên các dấu hiệu đã biết và các hoạt động bất thường.
- Machine learning: Phát hiện các hành vi bất thường và bất thường trong dữ liệu an ninh, giúp xác định các mối đe dọa tiềm ẩn mà không bị giới hạn bởi các định nghĩa mối đe dọa trước.

**Điều tra và phản hồi:**
- Timeline Investigation: Người dùng có thể tương tác với dữ liệu sự kiện để nhanh chóng xác định và truy xuất nguồn gốc của một mối đe dọa.
- Automated response: Tích hợp với các công cụ và script để tự động hóa các phản hồi an ninh, giúp giảm thiểu thời gian phản hồi và giảm tải cho các nhóm an ninh.
  
**Trực quan hóa và báo cáo:**
- Dashboards: Các dashboard được tạo sẵn và khả năng tùy chỉnh cao cho phép người dùng trực quan hóa các dữ liệu an ninh và phân tích xu hướng.
- Reporting: Cung cấp báo cáo định kỳ và tự động về tình hình an ninh, giúp các tổ chức tuân thủ các quy định và tiêu chuẩn an ninh.
  
**Quản lý và tích hợp:**
- Role-based access control (RBAC): Đảm bảo rằng chỉ những người dùng được phép mới có thể truy cập vào dữ liệu và công cụ quan trọng.
- APIs and integration: Dễ dàng tích hợp với các hệ thống an ninh khác và các công nghệ thông tin để mở rộng khả năng phòng thủ.
  
**Elastic Security** được thiết kế để hoạt động trên môi trường đám mây, tại chỗ và hybrid, đảm bảo linh hoạt và phù hợp với nhiều kiến trúc công nghệ. Nó là một phần quan trọng trong việc giúp các tổ chức phòng thủ chủ động chống lại các mối đe dọa an ninh mạng, giảm thiểu rủi ro và bảo vệ tài sản kỹ thuật số.
