# A Comprehensive Review of Data-Driven Co-Speech Gesture Generation

### Abstract

* Gestures that accompany speech are important for natural and efficient embodied human communication.
* Automatic generation of co-speech gestures is a long-standing problem in computer animation and is considered enabling technology for creating believable characters in film, games, and virtual social spaces, as well as for interaction with social robots.
* The problem is challenging due to the idiosyncratic and non-periodic nature of human co-speech gesture motion and the great diversity of communicative functions that gestures encompass.
* There is a surge of interest in gesture generation due to the emergence of larger datasets of human gesture motion and strides in deep-learning-based generative models that benefit from the growing availability of data.
* The article summarizes co-speech gesture generation research, focusing on deep generative models.
* The theory describing human gesticulation and how it complements speech is articulated, and rule-based and classical statistical gesture synthesis is briefly discussed before delving into deep learning approaches.
* Input modalities are employed as an organizing principle, examining systems that generate gestures from audio, text, and non-linguistic input.
* The evolution of related training datasets in terms of size, diversity, motion quality, and collection method is chronicled.
* Key research challenges in gesture generation are identified, including data availability and quality, producing human-like motion, grounding the gesture in the co-occurring speech in interaction with other speakers and the environment, performing gesture evaluation, and integration of gesture synthesis into applications.
* Recent approaches to tackling the key challenges, as well as their limitations, are highlighted, and areas of future development are pointed toward.

## 1. Introduction

* Gesture (cử chỉ) là một phần cần thiết trong giao tiếp nhân thể và có ít nhất ba chức năng chính: giúp các tác nhân nhân tạo trông sống động hơn và thu hút hơn; truyền tải thông tin chức năng; truyền tải thông tin xã hội.
* Sự tồn tại của gesture có thể cải thiện hiệu suất giao tiếp trong các cuộc đàm phán và giao tiếp trực tiếp.
* Các dạng gesture đa dạng và không đều nhau, điều này làm cho việc tự động tạo ra chúng trở nên khó khăn.
* Sự phát triển của deep learning và sự xuất hiện của các tập dữ liệu lớn hơn đã thúc đẩy sự quan tâm đến việc tạo ra cử chỉ đồng hành với lời nói bằng deep learning.
* Các phương pháp tạo ra gesture bao gồm: tạo ra cử chỉ dựa trên quy tắc, các phương pháp thống kê cổ điển và các phương pháp sử dụng deep learning.
* Deep learning cung cấp nhiều tiếp cận khác nhau để tạo ra gesture, trong đó đầu vào có thể là âm thanh, văn bản và các dạng đầu vào phi ngôn ngữ khác.
* Tập dữ liệu dùng để huấn luyện các mô hình gesture cũng phát triển theo thời gian về kích thước, đa dạng, chất lượng chuyển động và phương pháp thu thập dữ liệu.
* Các thách thức chính trong việc tạo ra cử chỉ đồng hành với lời nói bao gồm: sự sẵn có và chất lượng của dữ liệu; tạo ra chuyển động giống như con người; đưa cử chỉ vào ngữ cảnh của đối thoại và môi trường; đánh giá cử chỉ; tích hợp phát hiện cử chỉ vào các ứng dụng.
* Các phương pháp mới gần đây đã đưa ra giải pháp cho các thách thức trên, tuy nhiên vẫn còn hạn chế và cần phát triển thêm.


* The paper focuses on co-verbal gesture, which accompanies speech.
* Gesture plays at least three main functions: making artificial agents and robots look more alive and engaging, communicating functional information, and communicating social information.
* Functional information can include pointing, deictic gesture, emblems, and imagistic metaphoric and iconic gestures.
* Social information communicated through gesture can include personality, emotion, and subtext.
* Gestures communicate in a different way than spoken language and can support a range of applications for virtual agents and robots.
* It has been established that gestures do indeed communicate, and there are three main findings for when gestures communicate according to Hostetter’s meta-analysis: gestures depicting motor actions are more communicative than those depicting abstract topics, gestures that are not completely redundant have a larger impact on communication, and children benefit more from gesture than adults.

