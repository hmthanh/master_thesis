# A Comprehensive Review of Data-Driven Co-Speech Gesture Generation

### Abstract

- Gestures that accompany speech are important for natural and efficient embodied human communication.
- Automatic generation of co-speech gestures is a long-standing problem in computer animation and is considered enabling technology for creating believable characters in film, games, and virtual social spaces, as well as for interaction with social robots.
- The problem is challenging due to the idiosyncratic and non-periodic nature of human co-speech gesture motion and the great diversity of communicative functions that gestures encompass.
- There is a surge of interest in gesture generation due to the emergence of larger datasets of human gesture motion and strides in deep-learning-based generative models that benefit from the growing availability of data.
- The article summarizes co-speech gesture generation research, focusing on deep generative models.
- The theory describing human gesticulation and how it complements speech is articulated, and rule-based and classical statistical gesture synthesis is briefly discussed before delving into deep learning approaches.
- Input modalities are employed as an organizing principle, examining systems that generate gestures from audio, text, and non-linguistic input.
- The evolution of related training datasets in terms of size, diversity, motion quality, and collection method is chronicled.
- Key research challenges in gesture generation are identified, including data availability and quality, producing human-like motion, grounding the gesture in the co-occurring speech in interaction with other speakers and the environment, performing gesture evaluation, and integration of gesture synthesis into applications.
- Recent approaches to tackling the key challenges, as well as their limitations, are highlighted, and areas of future development are pointed toward.

## 1. Introduction

- Gesture (cử chỉ) là một phần cần thiết trong giao tiếp nhân thể và có ít nhất ba chức năng chính: giúp các tác nhân nhân tạo trông sống động hơn và thu hút hơn; truyền tải thông tin chức năng; truyền tải thông tin xã hội.
- Sự tồn tại của gesture có thể cải thiện hiệu suất giao tiếp trong các cuộc đàm phán và giao tiếp trực tiếp.
- Các dạng gesture đa dạng và không đều nhau, điều này làm cho việc tự động tạo ra chúng trở nên khó khăn.
- Sự phát triển của deep learning và sự xuất hiện của các tập dữ liệu lớn hơn đã thúc đẩy sự quan tâm đến việc tạo ra cử chỉ đồng hành với lời nói bằng deep learning.
- Các phương pháp tạo ra gesture bao gồm: tạo ra cử chỉ dựa trên quy tắc, các phương pháp thống kê cổ điển và các phương pháp sử dụng deep learning.
- Deep learning cung cấp nhiều tiếp cận khác nhau để tạo ra gesture, trong đó đầu vào có thể là âm thanh, văn bản và các dạng đầu vào phi ngôn ngữ khác.
- Tập dữ liệu dùng để huấn luyện các mô hình gesture cũng phát triển theo thời gian về kích thước, đa dạng, chất lượng chuyển động và phương pháp thu thập dữ liệu.
- Các thách thức chính trong việc tạo ra cử chỉ đồng hành với lời nói bao gồm:
  - Sự sẵn có và chất lượng của dữ liệu; tạo ra chuyển động giống như con người;
  - Đưa cử chỉ vào ngữ cảnh của đối thoại và môi trường
  - Đánh giá cử chỉ
  - Tích hợp phát hiện cử chỉ vào các ứng dụng.
- Các phương pháp mới gần đây đã đưa ra giải pháp cho các thách thức trên, tuy nhiên vẫn còn hạn chế và cần phát triển thêm.

- The paper focuses on co-verbal gesture, which accompanies speech.
- Gesture plays at least three main functions:
  - Making artificial agents and robots look more alive and engaging
  - communicating functional information
  - And communicating social information.
- Functional information can include pointing, deictic gesture, emblems, and imagistic metaphoric and iconic gestures.
- Social information communicated through gesture can include personality, emotion, and subtext.
- Gestures communicate in a different way than spoken language and can support a range of applications for virtual agents and robots.
- It has been established that gestures do indeed communicate, and there are three main findings for when gestures communicate according to Hostetter’s meta-analysis: gestures depicting motor actions are more communicative than those depicting abstract topics, gestures that are not completely redundant have a larger impact on communication, and children benefit more from gesture than adults.

Overall, our survey makes the following contributions to the field:
A detailed discussion on the theory and motivation for co-verbal gesture synthesis.

- A discussion on rule-based and statistical techniques, illustrating how these approaches can complement the strengths and weak-nesses of recent deep-learning approaches.
- An emphasis on deep-learning-based generation systems using input modality as an organizing principle for the research.
- A discussion on the most commonly used speech-to-gesture datasets, collected via motion capture or pose estimation.
- Identifying and detailing a set of key challenges for co-verbal gesture synthesis and potential research directions.

## 2. Human gesticulation

- Cử chỉ có thể có nhiều hình thái khác nhau và tuân thủ các quy tắc hình thái học khác nhau.

  - Phân loại cử chỉ của Kendon và "Kendon's Continuum" của McNeill phân loại các cử chỉ dựa trên độ từ vựng.
  - Đầu cực độ từ vựng của phổ (ngôn ngữ ký hiệu) có cấu trúc cú pháp chính thức giống như ngôn ngữ nói, trong khi các cử chỉ giao tiếp thường không có cấu trúc và có thể đặc trưng riêng.

- McNeill đề xuất một quan điểm kích thước về cử chỉ, bao gồm kích thước biểu tượng, ẩn dụ, chỉ trỏ và nhịp đập.

  - Một cử chỉ có thể đặt trọng tâm trên nhiều kích thước và có thể truyền đạt tính cách qua tự sự điều chỉnh, được gọi là "adaptors".
  - Một cử chỉ biểu tượng có thể hiển thị kích thước của một chiếc hộp đang được thảo luận bằng cách vẽ nó trên không gian, trong khi một cử chỉ ẩn dụ có thể chỉ ra một khái niệm trừu tượng bằng cách tạo hình dáng ô dù.

- Thách thức trong tổng hợp cử chỉ cho tương tác giữa con người và máy tính.

  - Giả thuyết điểm tăng trưởng cho rằng cử chỉ và ngôn ngữ xuất phát từ cùng một ý đồ giao tiếp.
  - Nhiều phương pháp tổng hợp cử chỉ và phương pháp học sâu không mô hình hóa ý đồ giao tiếp, dẫn đến sự trùng lặp và giới hạn của cử chỉ.

- Tính đặc thù của cử chỉ và sự khác biệt giữa các cá nhân.
  - Các cá nhân khác nhau có thể cử chỉ bằng cách khác nhau, và cùng một người có thể tạo ra các cử chỉ khác nhau cho cùng một văn bản.
  - Cử chỉ được đồng bộ hóa theo thời gian với lời nói của họ, thường xuất hiện trước lời nói đồng cảm khoảng 90% thời gian.
  - Người ta có thể không quá nhạy cảm với sai sót thời gian trong phạm vi +/- 0.6 giây.

## 3. Approaches for gesture synthesis

- Tổng hợp các cử chỉ đồng nói là cần thiết để tạo ra các nhân vật ảo tương tác và đáng tin cậy trong tương tác giữa con người và máy tính (HCI), đồ họa và robot xã hội.

  - Vấn đề chính trong tổng hợp cử chỉ gồm vấn đề xác định cử chỉ và vấn đề tạo động cử chỉ.
  - Có nhiều phương pháp được sử dụng để xác định cử chỉ, bao gồm ngữ 音, văn bản và ý đồ giao tiếp, trong đó các mô hình dựa trên quy tắc, thống kê và học máy đã được sử dụng để xác định cử chỉ phù hợp.
  - Có hai loại chính của mô hình sinh cử chỉ:
    - Mô hình dựa trên quy tắc
    - Và mô hình dữ liệu. Trong mô hình dữ liệu, có hai loại con là
      - Mô hình thống kê
      - Mô hình học máy.

- Các phương pháp mô hình sinh cử chỉ.

  - Các hệ thống dựa trên quy tắc sử dụng các thuật toán heuristics được thiết kế cẩn thận để chọn cử chỉ phù hợp với đầu vào âm thanh được cung cấp.
  - Các hệ thống dữ liệu sử dụng các phương pháp thống kê hoặc mô hình phân bố để xác định cử chỉ phù hợp với đầu vào âm thanh.
  - Các mô hình học máy tối ưu hóa các thông số của một hàm phi tuyến phức tạp để ánh xạ đầu vào âm thanh vào cử chỉ phù hợp.
  - Các phương pháp học sâu có xu hướng tổng hợp chuyển động trên cơ sở từng khung hình.
  - Các phương pháp dựa trên quy tắc và thống kê thường dự đoán một nhãn cử chỉ được sử dụng để chỉ mục các đoạn chuyển động cử chỉ được thực hiện bằng tay hoặc được ghi sẵn. Trong khi đó, các phương pháp học sâu có xu hướng tổng hợp chuyển động trên cơ sở từng khung hình.

