# ![openplace](../../banner.png "openplace banner")

<p align="center"><strong>Translations</strong> v6.3</p>
<p align="center">
	<a href="../../README.md"><img src="https://flagcdn.com/256x192/us.png" width="48" alt="United States Flag"></a>

## 

Openplace (không viết hoa) là một mã nguồn mở backend miễn phí, không chính thức cho [wplace.](https://wplace.live) Chúng tôi hướng tới việc mang lại sự tự do và linh hoạt cho tất cả người dùng để có thể tạo ra một trải nghiệm tương tự Wplace riêng tư cho bản thân, bạn bè, hay thậm chí là cộng đồng của họ.

> [CẢNH BÁO ⚠️]
> Đây là một dự án đang dần được hoàn thiện. Vẫn có thể tồn tại các tính năng chưa hoàn thiện hoặc lỗi. Hãy giúp chúng tôi bằng cách gửi các vấn đề vào kênh #tech-support trong [máy chủ Discord](https://discord.gg/ZRC4DnP9Z2) của chúng tôi hoặc bằng cách đóng góp thông qua pull request. Cảm ơn!

## Bắt Đầu

### Windows

- [Hướng dẫn cài đặt cho Windows](translations/vi/SETUP_WINDOWS.md)

### macOS

- [Hướng dẫn cài đặt cho macOS](translations/vi/SETUP_MACOS.md)

### Docker

- [Hướng dẫn cài đặt cho Docker](translations/vi/SETUP_DOCKER.md)


### Khả năng truy cập máy chủ
Bạn sẽ cần phải cấu hình chứng chỉ SSL nếu dự định sử dụng nó trong production. Tuy nhiên, nếu bạn chỉ sử dụng cho bạn và bạn bè của bạn, bạn chỉ cần điều hướng đến `https://{IP}:8080` LƯU Ý: openplace chỉ được host bằng HTTPS. bạn sẽ gặp lỗi HTTP 400 nếu bạn cố gắng tải trang web thông qua giao thức HTTP.

### Cập nhật cơ sở dữ liệu
Trong trường hợp sơ đồ cơ sở dữ liệu thay đổi, bạn chỉ cần chạy `npm run db:push` để cập nhật sơ đồ cơ sở dữ liệu của bạn.

## Thêm bản dịch

> [CẢNH BÁO ⚠️]
> Việc đóng góp có sử dụng AI sẽ bị từ chối, và bạn **SẼ** bị cấm khỏi repo này. Bạn phải thành thạo với ngôn ngữ mà bạn dịch.

Để đóng góp vào repo này và dịch `README.md` cũng các file hướng dẫn cài đặt khác, vui lòng theo các bước sau.

### Thay đổi số của phiên bản trên đầu trang README này để chỉ ra rằng một ngôn ngữ mới đã được thêm

Số của phiên bản được định dạng dưới dạng `X.XX`, với "X" đầu tiên đại diện cho số ngôn ngữ được thêm vào chính thức. Các chữ "X" sau dấu chấm được thay đổi mỗi khi có bất kì sự thay đổi nào với phiên bản tiếng Anh của file README.
Số của phiên bản giúp cho các dịch giả có thể biết được khi nào thì họ cần cập nhật nội dung của bản dịch hiện có.

### Tạo một thư mục mới trong thư mục `translations`, đặt tên dựa vào mã ISO của ngôn ngữ mà bạn sử dụng

Nếu bạn không chắc mã ISO của bạn là gì, bạn có thể kiểm tra tại [đây](https://gist.githubusercontent.com/josantonius/b455e315bc7f790d14b136d61d9ae469/raw/416def353b8849c427e9062a9db6445c62e77f75/language-codes.json) hoặc đơn giản hơn là tìm kiếm trên mạng. Bạn sẽ phải tìm một mã gồm hai chữ cái, ví dụ như `"vi"` đối với tiếng Việt.

### Sao chép các tệp tiếng Anh vào thư mục mới của bạn

Sao chép các tệp tiếng Anh từ thư mục `translations` và tệp `README.md` chính vào trong thư mục bạn mới vừa tạo.
Bạn hiện giờ nên có bốn tệp: `README.md` và ba tệp markdown (`.md`) hướng dẫn cài đặt.

### Thêm đúng cờ vào hai tệp README

Khi tạo một bản dịch mới, bạn phải cập nhật **hai** tệp README:

#### 1. **README tiếng Anh gốc**

Chỉ thêm **mỗi lá cờ của quốc gia/ngôn ngữ bạn đang dịch vào** đầu.
Lá cờ sẽ phải liên kết đến tệp README mà bạn vừa mới dịch.

Sử dụng mẫu này:

```html
<a href="translations/LANGUAGE_ISO_CODE/NAME_OF_YOUR_README.md"><img src="https://flagcdn.com/256x192/LANGUAGE_ISO_CODE.png" width="48" alt="NAME_OF_COUNTRY Flag"></a>
```

Thay thế các vị trí giữ chỗ với mã ISO và tên của quốc gia cho bản dịch của bạn.

#### 2. **Tệp README được dịch của bạn**

Ở đầu trang README đã được dịch của bạn, chỉ thêm **mỗi lá cờ của nước Mỹ**, liên kết đến tệp README tiếng Anh ban đầu.

> [CẢNH BÁO ⚠️]
> Các lá cờ trong tệp README tiếng Anh phải được giữ nguyên theo thứ tự bảng chữ cái dựa theo mã ISO.

### Cập nhật các liên kết trong phần Bắt Đầu

Trong phần **Bắt Đầu**, cập nhật các liên kết để chúng trỏ đến các tệp đã dịch của bạn.
Nếu bạn không biết cách làm, có thể xem qua các thư mục ngôn ngữ khác (ví dụ như `fr`).

### Dịch tất cả tệp

Dịch toàn bộ các tệp một cách đầy đủ và chính xác.
Một khi bạn đã hoàn tất, Hãy tạo một pull request. Một người đóng góp hoặc người dùng sẽ xác minh bản dịch của bạn.
**Đừng quên rằng:** việc sử dụng AI bị nghiêm cấm tuyệt đối và sẽ dẫn đến lệnh cấm vĩnh viễn nếu bị phát hiện.

### Xác minh bản dịch của bạn

Nhấn vào **TỪNG** liên kết và cờ. Mỗi liên kết phải hoạt động chính xác và dẫn đến tệp hoặc trang web thích hợp.
Nếu có gì đó không hoạt động đúng, hãy sửa nó trước khi gửi pull request.
Một khi mọi thứ hoạt động như mong đợi, bạn có thể tự tin và mở pull request của bạn.
Hãy nhớ rằng: Các hướng dẫn này sẽ được xem xét lại đối với tất cả các bản dịch để đảm bảo tuân thủ đầy đủ.


## Giấy phép
Được cấp phép theo Giấy phép Apache, phiên bản 2.0. Tham khảo [LICENSE.md](https://github.com/openplaceteam/openplace/blob/main/LICENSE.md).

### Công nhận
Dữ liệu khu vực được lấy từ [GeoNames Gazetteer](https://download.geonames.org/export/dump/), và được cấp phép theo [Creative Commons Attribution 4.0 License](https://creativecommons.org/licenses/by/4.0/). Dữ liệu được cung cấp "nguyên trạng" mà không có bất kỳ bảo đảm hoặc cam kết nào về tính chính xác, kịp thời hoặc đầy đủ.
