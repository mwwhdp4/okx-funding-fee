# phí funding OKX: Cách tính, thời điểm thanh toán và cách đọc funding rate khi giao dịch futures

Nếu bạn giao dịch **futures vĩnh cửu trên OKX**, phí funding là một khoản cần kiểm tra trước khi giữ lệnh qua nhiều kỳ thanh toán. Khoản phí này có thể khá nhỏ khi vị thế ngắn hoặc funding rate thấp, nhưng sẽ nhanh chóng đáng kể nếu bạn dùng đòn bẩy cao, giữ lệnh lâu hoặc giao dịch hợp đồng có funding rate biến động mạnh.

Điểm dễ nhầm là phí funding không giống phí giao dịch. OKX không thu khoản này như một loại hoa hồng riêng. Funding được chuyển trực tiếp giữa bên Long và bên Short để giúp giá hợp đồng vĩnh cửu bám sát giá chỉ số của tài sản cơ sở. Khi funding dương, bên Long trả cho bên Short. Khi funding âm, bên Short trả cho bên Long.

Bài viết này giải thích phí funding OKX là gì, công thức tính ra sao, khi nào bị trừ, cách xem funding rate hiện tại và cách phân biệt funding với maker fee, taker fee hay phí thanh lý.

## Phí funding OKX là gì?

Futures vĩnh cửu là hợp đồng không có ngày đáo hạn cố định. Vì không có ngày hết hạn để giá hợp đồng tự hội tụ với giá giao ngay, sàn sử dụng funding rate để khuyến khích bên Long và Short cân bằng hơn.

Cơ chế hoạt động khá đơn giản:

- **Funding rate dương:** Người giữ vị thế Long trả phí cho người giữ vị thế Short.
- **Funding rate âm:** Người giữ vị thế Short trả phí cho người giữ vị thế Long.
- **Funding rate bằng 0%:** Không phát sinh khoản thanh toán funding giữa hai bên.
- **OKX không thu phần phí funding như doanh thu dịch vụ:** nền tảng chỉ hỗ trợ quá trình tính và phân phối khoản tiền giữa các bên tham gia.

Vì vậy, funding rate không phải là mức phí cố định của OKX. Nó thay đổi theo từng hợp đồng và phản ánh chênh lệch giữa giá hợp đồng vĩnh cửu với giá chỉ số, cùng một số thành phần trong công thức funding của nền tảng.

Nói ngắn gọn: khi thị trường nghiêng quá mạnh về một phía, phía đó thường phải trả funding cho phía đối diện. Đây là cách thị trường “nhắc nhẹ” rằng vị thế đang quá đông, dù cái nhắc nhẹ này đôi khi có thể trừ thẳng vào số dư ký quỹ.

## Funding rate được thanh toán lúc nào?

Theo tài liệu OKX, funding fee thường được thanh toán theo chu kỳ **8 giờ**, mặc định vào các mốc:

- 00:00 UTC
- 08:00 UTC
- 16:00 UTC

Một số hợp đồng có chu kỳ ngắn hơn, chẳng hạn **1 giờ, 2 giờ hoặc 4 giờ**. Lịch thanh toán cụ thể được hiển thị ngay trên giao diện giao dịch của từng hợp đồng.

Nếu quy đổi sang giờ Việt Nam, các mốc 8 giờ mặc định thường tương ứng với:

- 07:00
- 15:00
- 23:00

Tuy nhiên, bạn nên ưu tiên đồng hồ đếm ngược trên giao diện OKX thay vì chỉ ghi nhớ giờ cố định. Thời điểm thanh toán có thể được điều chỉnh tùy điều kiện thị trường và từng sản phẩm. OKX cũng cho biết quá trình đánh giá diễn ra ở cấp độ rất ngắn, còn việc hoàn tất thanh toán thực tế có thể kéo dài khoảng một phút.

### Có phải cứ mở lệnh là phải trả funding không?

Không.

Bạn chỉ trả hoặc nhận funding nếu vẫn đang nắm giữ vị thế tại thời điểm hệ thống đánh giá phí. Nếu đóng vị thế trước thời điểm đó, bạn không tham gia kỳ thanh toán tương ứng.

Ví dụ:

- Bạn mở lệnh Long lúc 10:00.
- Funding tiếp theo diễn ra lúc 15:00 theo giờ Việt Nam.
- Nếu đóng lệnh lúc 14:58, bạn thường không phải trả funding của kỳ 15:00.
- Nếu vẫn giữ lệnh qua thời điểm đánh giá, khoản funding sẽ được tính theo hướng của vị thế và funding rate tại thời điểm đó.

Việc đóng lệnh trước kỳ funding không có nghĩa là giao dịch miễn phí. Bạn vẫn có thể chịu maker fee hoặc taker fee khi mở và đóng vị thế, cùng các khoản khác nếu có. Funding chỉ là một phần trong tổng chi phí.

## Công thức tính phí funding OKX

Công thức cơ bản là:

text
Phí funding = Giá trị vị thế × Funding rate


Với hợp đồng futures vĩnh cửu ký quỹ bằng USDT hoặc USDC, giá trị vị thế thường được tính theo:

text
Giá trị vị thế =
Số lượng hợp đồng × Quy mô hợp đồng × Hệ số nhân × Giá đánh dấu


OKX đưa ra ví dụ với vị thế Long 10 hợp đồng BTCUSDT, mỗi hợp đồng có mệnh giá 0,01 BTC, giá đánh dấu là 60.000 USDT và funding rate là 0,1%:

text
Giá trị vị thế = 10 × 0,01 × 1 × 60.000
               = 6.000 USDT

Phí funding = 6.000 × 0,1%
            = 6 USDT


Trong trường hợp funding rate dương, người giữ Long sẽ bị trừ 6 USDT và khoản này được chuyển cho phía Short theo cơ chế thanh toán của hợp đồng.

Với hợp đồng ký quỹ bằng crypto, cách tính giá trị vị thế có thể khác. Ví dụ, OKX minh họa hợp đồng ETHUSD bằng công thức dựa trên mệnh giá hợp đồng chia cho giá đánh dấu. Vì vậy, không nên lấy công thức của BTCUSDT rồi áp dụng máy móc cho mọi sản phẩm. Hãy kiểm tra quy mô hợp đồng và đơn vị thanh toán trước khi ước tính chi phí.

### Ví dụ với funding rate thấp hơn

Giả sử:

- Giá trị vị thế: 10.000 USDT
- Funding rate: 0,01%
- Chu kỳ thanh toán: 8 giờ

Khi đó:

text
Phí funding = 10.000 × 0,01%
            = 1 USDT mỗi kỳ


Nếu giữ vị thế qua ba kỳ trong 24 giờ và funding rate không đổi, tổng phí lý thuyết là 3 USDT. Nhưng đây chỉ là phép tính minh họa. Funding rate thực tế thay đổi liên tục và khoản phí được tính theo giá trị vị thế tại thời điểm đánh giá, không phải nhất thiết theo số tiền ký quỹ ban đầu.

## Đòn bẩy có làm phí funding tăng không?

Đòn bẩy không trực tiếp xuất hiện trong công thức phí funding. Khoản phí được tính trên **giá trị danh nghĩa của vị thế**, không chỉ trên số tiền ký quỹ.

Ví dụ, cùng mở vị thế trị giá 10.000 USDT:

- Dùng đòn bẩy 2x: ký quỹ khoảng 5.000 USDT.
- Dùng đòn bẩy 10x: ký quỹ khoảng 1.000 USDT.
- Funding rate là 0,05%.

Trong cả hai trường hợp, nếu giá trị vị thế đều là 10.000 USDT:

text
Phí funding = 10.000 × 0,05%
            = 5 USDT mỗi kỳ


Số tiền funding không tự giảm chỉ vì bạn dùng ít ký quỹ hơn. Tuy nhiên, xét trên phần ký quỹ, vị thế 10x sẽ chịu ảnh hưởng lớn hơn. Khoản 5 USDT có thể chỉ chiếm một phần nhỏ của vị thế 2x nhưng chiếm tỷ lệ đáng kể hơn so với tiền ký quỹ của vị thế 10x.

Đó là lý do funding rate cao cộng với đòn bẩy lớn có thể làm biên an toàn của lệnh giảm nhanh, đặc biệt khi vị thế đang lỗ chưa thực hiện.

## Funding rate OKX được tính như thế nào?

Công thức funding rate trên OKX có nhiều thành phần. Tài liệu của sàn mô tả công thức theo dạng:

text
Funding rate =
Clamp [
  Average premium index
  + Clamp (Interest rate - Average premium index, 0,05%, -0,05%),
  Funding cap,
  Funding floor
]


Trong đó:

- **Average premium index** phản ánh mức chênh lệch giữa giá hợp đồng và giá chỉ số.
- **Interest rate** là thành phần lãi suất được đưa vào công thức.
- **Funding cap** và **funding floor** giới hạn mức funding tối đa và tối thiểu.
- Chỉ số chênh lệch giá được tính dựa trên giá chào mua tác động, giá chào bán tác động và giá chỉ số.
- Giá trị trung bình được tính theo một phương pháp trung bình động có trọng số trong chu kỳ funding.

Bạn không cần tự tính toàn bộ công thức này mỗi lần giao dịch. Việc thực tế cần làm là kiểm tra funding rate hiện tại, hướng Long/Short phải trả và thời gian còn lại đến kỳ thanh toán.

Điểm đáng chú ý là OKX đã cập nhật logic tính funding rate cho các hợp đồng có chu kỳ ngắn hơn 8 giờ. Thông báo ngày 29 tháng 5 năm 2026 cho biết công thức mới sử dụng hệ số `8/N`, trong đó `N` là số giờ của chu kỳ thanh toán. Hợp đồng 8 giờ không thay đổi theo phần hệ số này; hợp đồng 4 giờ, 2 giờ và 1 giờ có mức funding mỗi kỳ được điều chỉnh tương ứng.

Điều này có nghĩa là bạn không nên nhìn một con số funding mà bỏ qua chu kỳ áp dụng. Funding 0,02% mỗi 8 giờ và 0,02% mỗi 1 giờ là hai mức chi phí hoàn toàn khác nhau.

## Cách xem phí funding trên OKX

### Trên ứng dụng

Bạn có thể kiểm tra theo các bước sau:

1. Mở ứng dụng OKX.
2. Chọn **Giao dịch**.
3. Chọn **Futures** hoặc khu vực hợp đồng vĩnh cửu.
4. Chọn cặp giao dịch cần xem.
5. Mở phần **Candles** hoặc **Info**.
6. Chọn **Funding rate**.

Tại đây, OKX hiển thị funding rate hiện tại, hướng thanh toán, giới hạn trần/sàn nếu có, lịch sử funding và đồng hồ đếm ngược đến kỳ kế tiếp.

### Trên website

Trên phiên bản web, hãy mở khu vực giao dịch futures, chọn hợp đồng vĩnh cửu rồi nhấn vào phần **Funding rate / Countdown** phía trên giao diện giao dịch.

Nếu không nhìn thấy thông tin funding, OKX hướng dẫn chuyển sang chế độ nâng cao bằng cách mở rộng khu vực giao dịch. Vị trí nút có thể thay đổi theo phiên bản giao diện, nhưng thông tin cần tìm vẫn là funding rate và thời gian đếm ngược.

### Kiểm tra lịch sử funding

Lịch sử funding hữu ích hơn một con số đang chạy tại thời điểm hiện tại. Một funding rate đẹp ở phút này không đảm bảo vài giờ nữa vẫn giữ nguyên.

Trên ứng dụng, bạn có thể vào khu vực futures, chọn funding rate hoặc countdown rồi mở lịch sử funding. OKX cho biết người dùng có thể xem biến động funding trong tối đa khoảng ba tháng gần đây tùy giao diện và sản phẩm.

Khi đọc lịch sử, hãy chú ý:

- Funding thường dương hay âm?
- Mức funding có tăng mạnh vào lúc thị trường biến động không?
- Hợp đồng có chu kỳ 1, 2, 4 hay 8 giờ?
- Funding rate cao kéo dài trong bao nhiêu kỳ?
- Vị thế của bạn đang ở phía trả hay phía nhận?

## Phí funding khác gì phí giao dịch?

Đây là ba loại chi phí thường bị trộn lẫn:

| Loại phí | Khi phát sinh | Cách xác định | Ai nhận tiền? |
| --- | --- | --- | --- |
| Maker fee | Khi lệnh được khớp với vai trò cung cấp thanh khoản | Theo bậc phí và loại sản phẩm | OKX thu theo bảng phí |
| Taker fee | Khi lệnh khớp ngay với lệnh có sẵn trên sổ lệnh | Theo bậc phí và loại sản phẩm | OKX thu theo bảng phí |
| Funding fee | Khi giữ vị thế qua thời điểm thanh toán | Giá trị vị thế × funding rate | Chuyển giữa Long và Short |
| Phí thanh lý | Khi vị thế bị thanh lý | Theo quy tắc thanh lý và bậc phí áp dụng | Có thể áp dụng theo chính sách sàn |

OKX xác nhận funding fee và trading fee là hai khoản khác nhau. Người dùng có thể chịu cả phí giao dịch khi mở hoặc đóng vị thế, đồng thời chịu funding nếu vẫn giữ lệnh qua thời điểm thanh toán.

Nếu bạn giao dịch thường xuyên, maker/taker fee có thể là khoản lớn hơn funding. Nếu bạn giữ lệnh nhiều giờ hoặc nhiều ngày, funding có thể trở thành chi phí đáng kể. Không nên chỉ nhìn một loại phí rồi kết luận giao dịch đang “rẻ”.

## Bảng phí futures OKX theo từng bậc

Bảng dưới đây là khung phí maker và taker cho thị trường futures theo thông tin OKX công bố. Đây là **phí giao dịch**, không phải funding fee. Funding không có một mức cố định theo bậc VIP; nó phụ thuộc vào hợp đồng, hướng vị thế, giá trị vị thế và funding rate tại thời điểm thanh toán.

| Bậc tài khoản | Điều kiện tài sản hoặc khối lượng futures 30 ngày | Maker nhóm 1 | Taker nhóm 1 | Maker nhóm 2 | Taker nhóm 2 | Xem điều kiện |
| --- | ---: | ---: | ---: | ---: | ---: | --- |
| Người dùng thông thường | Tài sản dưới 100.000 USD hoặc khối lượng dưới 10 triệu USD | 0,0200% | 0,0500% | 0,0200% | 0,0500% | [ Mở tài khoản và kiểm tra mức phí](https://okx.com/join/CASH20) |
| VIP 1 | Tài sản từ 100.000 USD hoặc khối lượng từ 10 triệu USD | 0,0180% | 0,0400% | 0,0180% | 0,0400% | [ Xem quyền lợi VIP 1](https://okx.com/join/CASH20) |
| VIP 2 | Tài sản từ 250.000 USD hoặc khối lượng từ 50 triệu USD | 0,0130% | 0,0350% | 0,0130% | 0,0350% | [ Kiểm tra điều kiện VIP 2](https://okx.com/join/CASH20) |
| VIP 3 | Tài sản từ 500.000 USD hoặc khối lượng từ 100 triệu USD | 0,0100% | 0,0280% | 0,0100% | 0,0280% | [ Xem bảng phí futures](https://okx.com/join/CASH20) |
| VIP 4 | Tài sản từ 2 triệu USD hoặc khối lượng từ 200 triệu USD | 0,0080% | 0,0270% | 0,0080% | 0,0270% | [ Kiểm tra bậc phí của bạn](https://okx.com/join/CASH20) |
| VIP 5 | Tài sản từ 5 triệu USD hoặc khối lượng từ 600 triệu USD | 0,0050% | 0,0260% | 0,0050% | 0,0260% | [ Xem điều kiện VIP 5](https://okx.com/join/CASH20) |
| VIP 6 | Tài sản từ 10 triệu USD hoặc khối lượng từ 1 tỷ USD | 0,0000% | 0,0250% | 0,0000% | 0,0250% | [ Kiểm tra quyền lợi VIP 6](https://okx.com/join/CASH20) |
| VIP 7 | Khối lượng futures từ 1,5 tỷ USD | -0,0020% | 0,0200% | -0,0050% | 0,0250% | [ Xem mức phí VIP 7](https://okx.com/join/CASH20) |
| VIP 8 | Khối lượng futures từ 2 tỷ USD | -0,0050% | 0,0200% | -0,0100% | 0,0250% | [ Kiểm tra điều kiện VIP 8](https://okx.com/join/CASH20) |
| VIP 9 | Khối lượng futures từ 20 tỷ USD | -0,0050% | 0,0150% | -0,0100% | 0,0200% | [ Xem khung phí VIP 9](https://okx.com/join/CASH20) |

OKX chia futures thành hai nhóm. Nhóm 1 gồm một số hợp đồng lớn như BTC-USDT, ETH-USDT, SOL-USDT, DOGE-USDT, BTC-USD, XRP-USDT, ETH-USD, PEPE-USDT, PUMP-USDT và SUI-USDT. Nhóm 2 là các hợp đồng futures còn lại đang được hỗ trợ. Một số sản phẩm có thể không khả dụng ở mọi khu vực.

OKX cũng cho biết bảng phí và phân nhóm có thể được rà soát định kỳ. Vì vậy, bảng trên nên được dùng để định hướng, còn mức phí áp dụng thực tế cần kiểm tra sau khi đăng nhập vào tài khoản.

## Mã giới thiệu CASH20 có giảm phí funding không?

Mã **CASH20** không làm thay đổi công thức funding rate của từng hợp đồng. Funding vẫn được tính dựa trên giá trị vị thế và funding rate tại thời điểm thanh toán.

Mã giới thiệu có thể liên quan đến chương trình dành cho người đăng ký mới hoặc quyền lợi giao dịch được hiển thị theo khu vực, thời điểm và điều kiện tài khoản. Vì các chương trình giới thiệu có thể thay đổi, hãy kiểm tra nội dung ưu đãi trực tiếp trong quá trình đăng ký và trước khi nạp tiền.

Bạn có thể bắt đầu từ liên kết được cung cấp dưới đây và nhập mã giới thiệu nếu hệ thống yêu cầu:

[👉 Đăng ký OKX với mã CASH20](https://okx.com/join/CASH20)

Không nên hiểu “hoàn phí” hoặc “rebate” là được miễn funding. Phí funding là khoản trao đổi giữa Long và Short, còn ưu đãi giới thiệu, nếu có, thường liên quan đến điều kiện tài khoản hoặc phí giao dịch theo chương trình cụ thể. Hai cơ chế này không giống nhau.

## Cách giảm tác động của phí funding

Không có cách nào bảo đảm funding rate luôn thấp hoặc luôn có lợi cho vị thế của bạn. Tuy vậy, bạn có thể giảm tác động của khoản phí này bằng vài nguyên tắc thực tế.

### 1. Kiểm tra funding trước khi mở vị thế

Đừng chỉ nhìn giá và biểu đồ. Trước khi đặt lệnh, hãy kiểm tra:

- Funding rate hiện tại.
- Funding rate dự kiến cho kỳ tiếp theo.
- Thời gian còn lại đến lúc thanh toán.
- Chu kỳ funding của hợp đồng.
- Bên Long hay Short đang trả phí.

Nếu funding đang tăng nhanh và bạn dự định giữ lệnh lâu, chi phí này cần được đưa vào kế hoạch giao dịch.

### 2. Tính trên giá trị vị thế, không phải tiền ký quỹ

Một lỗi phổ biến là lấy số tiền ký quỹ nhân với funding rate. Cách này có thể sai vì funding được tính trên giá trị danh nghĩa của vị thế.

Ví dụ, bạn ký quỹ 1.000 USDT để mở vị thế trị giá 10.000 USDT. Funding rate 0,1% sẽ tương đương:

text
10.000 × 0,1% = 10 USDT


Không phải:

text
1.000 × 0,1% = 1 USDT


Khoản chênh lệch này đủ lớn để làm hỏng phép tính lợi nhuận nếu bạn dùng đòn bẩy cao.

### 3. Không giữ lệnh qua kỳ funding nếu chiến lược không cần

Nếu giao dịch của bạn chỉ nhắm đến một biến động ngắn, việc giữ lệnh thêm vài phút để “chờ xem sao” có thể khiến bạn đi qua kỳ funding không cần thiết. Đương nhiên, không nên đóng lệnh chỉ vì một khoản funding nhỏ nếu việc đóng lệnh làm phát sinh rủi ro lớn hơn hoặc phí giao dịch cao hơn.

Cần cân đối cả ba yếu tố:

- Chi phí funding.
- Phí mở và đóng vị thế.
- Rủi ro giá biến động trong thời gian chờ.

### 4. So sánh funding theo chu kỳ

Funding 0,05% mỗi 8 giờ tương đương một mức khác hoàn toàn so với 0,05% mỗi 1 giờ. Khi so sánh hai hợp đồng, hãy quy đổi về cùng khoảng thời gian.

Ví dụ về mặt lý thuyết:

text
0,05% mỗi 8 giờ × 3 kỳ/ngày = 0,15%/ngày


Trong khi đó:

text
0,05% mỗi 1 giờ × 24 kỳ/ngày = 1,20%/ngày


Đây là lý do chu kỳ thanh toán quan trọng không kém con số funding rate hiển thị trên màn hình.

### 5. Đừng xem funding âm là “tiền miễn phí”

Funding âm có thể khiến một phía nhận được khoản thanh toán, nhưng điều đó không biến giao dịch thành không có rủi ro. Giá tài sản có thể đi ngược hướng vị thế, funding có thể chuyển dương, thanh khoản có thể giảm và phí giao dịch vẫn tồn tại.

Nếu vị thế Short đang nhận funding nhưng giá tăng mạnh, khoản funding nhận được có thể không bù được khoản lỗ từ biến động giá. Một vài phần trăm funding không nên trở thành lý do duy nhất để mở lệnh.

## Vì sao phí funding thay đổi mạnh khi thị trường biến động?

Funding rate phản ánh sự mất cân bằng giữa giá hợp đồng và giá chỉ số, nên thường nhạy cảm với:

- Biến động giá mạnh.
- Dòng tiền tập trung về Long hoặc Short.
- Tin tức khiến nhà giao dịch cùng nghiêng về một hướng.
- Thanh khoản thấp trên một số hợp đồng.
- Chênh lệch giữa giá hợp đồng và giá giao ngay.
- Thay đổi trong giới hạn funding hoặc chu kỳ thanh toán.

OKX lưu ý rằng trong giai đoạn thị trường biến động mạnh hoặc Long và Short mất cân bằng, funding rate có thể tăng đáng kể. Vì vậy, không nên lấy funding rate ở thời điểm thị trường yên ắng để ước tính chi phí cho một giai đoạn biến động lớn.

## Phí funding có liên quan đến PNL không?

Funding ảnh hưởng đến số dư và kết quả ròng của vị thế, nhưng bản thân funding không được tính theo PNL.

Theo OKX, phí funding dựa trên:

text
Giá trị vị thế × Funding rate


Không dựa trực tiếp trên việc vị thế đang lời hay lỗ. Một vị thế đang có lãi vẫn có thể phải trả funding. Một vị thế đang lỗ vẫn có thể nhận funding nếu hướng thanh toán và funding rate phù hợp.

Ví dụ, bạn đang Long BTCUSDT và vị thế đang lời 200 USDT. Nếu funding rate dương, bạn vẫn có thể bị trừ funding. Ngược lại, nếu vị thế đang lỗ nhưng funding rate âm, bạn có thể nhận funding từ bên Short, dù khoản nhận được không nhất thiết bù được khoản lỗ giá.

## Nên xem phí funding ở đâu trước khi giao dịch?

Một quy trình kiểm tra nhanh có thể gồm:

1. Chọn đúng hợp đồng vĩnh cửu.
2. Kiểm tra funding rate hiện tại.
3. Kiểm tra thời gian đến kỳ thanh toán.
4. Xác định chu kỳ 1, 2, 4 hay 8 giờ.
5. Ước tính giá trị danh nghĩa của vị thế.
6. Tính phí funding dự kiến bằng công thức cơ bản.
7. Cộng thêm maker/taker fee khi mở và đóng lệnh.
8. Đặt ngưỡng dừng lỗ phù hợp với mức ký quỹ.

Bạn có thể xem lại lịch sử funding sau giao dịch trong phần lịch sử giao dịch. OKX cho phép lọc các bản ghi liên quan đến funding để biết mình đã trả hay nhận bao nhiêu.

## Kết luận

Phí funding OKX là khoản thanh toán định kỳ giữa người giữ Long và Short trên hợp đồng futures vĩnh cửu. Khoản này không phải phí giao dịch cố định và không được tính đơn giản trên tiền ký quỹ. Công thức cơ bản là:

text
Phí funding = Giá trị vị thế × Funding rate


Funding dương có lợi cho bên Short và bất lợi cho bên Long. Funding âm thì ngược lại. Bạn chỉ trả hoặc nhận khoản này nếu còn giữ vị thế tại thời điểm thanh toán.

Trước khi giao dịch, hãy kiểm tra cả funding rate, chu kỳ thanh toán, giá trị danh nghĩa, maker/taker fee và nguy cơ thanh lý. Nếu muốn sử dụng mã giới thiệu **CASH20**, hãy bắt đầu từ liên kết bên dưới và xác nhận điều kiện hiển thị trên tài khoản trước khi giao dịch:

[👉 Kiểm tra tài khoản OKX và mã CASH20](https://okx.com/join/CASH20)

Futures và đòn bẩy có rủi ro cao. Funding chỉ là một phần của tổng chi phí; biến động giá và thanh lý vẫn là những yếu tố có thể ảnh hưởng lớn hơn nhiều đến kết quả cuối cùng.
