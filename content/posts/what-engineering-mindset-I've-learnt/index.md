---
weight: 1
title: "What engineering mindsets I've learnt in big tech company?"
date: 2023-09-05T09:00:00+07:00
lastmod: 2023-09-05T09:00:00+07:00
draft: false
description: "Discover what engineering mindsets I've learnt in GxS"
images: []
resources:
- name: "featured-image"
  src: "featured-image.jpg"

tags: ["mindset"]

lightgallery: true

toc:
  auto: false
---

<!--more-->

Wow, thời gian trôi qua nhanh thiệt. Chớp mắt 1 cái mà đã đến lúc hành trình 1 năm với GxS của mình đã kết thúc. Tuy thời gian không quá dài, nhưng mình cảm thấy tự hào khi được đóng góp công sức để xây dựng lên 1 trong những digital bank đầu tiên ở Singapore.

Trong thời gian ở đây, mình đã học được rất nhiều võ công mới, có nhiều thứ mà mình mới chỉ nghe thấy lần đầu tiên. Điều làm mình thấy khác biệt so với những gì mình đã từng trải qua ở các công ty ở Việt Nam đó là mindset làm việc. 

Tin rằng những mindset làm việc này là quan trọng để giúp anh em đi xa hơn trong công việc, cũng như mình thấy tiếc vì mình đã không được học những mindset này sớm hơn, cho nên mình viết post này để chia sẻ lại cho anh em những góc nhìn mới.

Đầu tiên thì xin 1 phút giới thiệu về GxS :3 

## What is GxS?

Được thành lập bởi Grab và Singtel, GxS Bank là 1 trong 2 digital bank đầu tiên ở Singapore. Vậy điều gì làm GxS Bank khác biệt so với các ngân hàng khác?

<a href="https://www.youtube.com/watch?v=SV9sl5hBfcI" title="GxS"><img src="gxs.jpg" alt="GxS Bank" /></a>

Tầm nhìn của GxS là redefne trải nghiệm ứng dụng ngân hàng của người dùng. GxS nhắm tới xây dựng hành vi quản lý tiền thông minh cho người dùng, giúp người dùng sử dụng dịch vụ ngân hàng một cách dễ dàng, ... Với tầm nhìn đó, các engineers của GxS luôn nỗ lực hết mình để mang lại trải nghiệm tốt nhất cho người dùng.

Bên cạnh đó, vì được thành lập bởi Grab, nên GxS thừa kế được lượng user lớn, những bài học & công nghệ từ Grab, qua đó giúp GxS đi nhanh và xa hơn.

Check out thêm về GxS ở đây nha: https://www.gxs.com.sg/

Okay, chuyển qua tiết mục chính thôi.

## Automation test is essential

{{< admonition tip "Lesson" >}}
Nếu bạn muốn dự án của mình tốt hơn và tiến xa hơn về lâu dài, hãy viết automation test. Đừng hoàn toàn dựa vào QA.
{{< /admonition >}}

Mình đã trải qua một số dự án trước khi gia nhập GxS và không có dự án nào yêu cầu viết automation test cả. Tất nhiên là mình cũng đã đọc vài articles về lợi ích của automation tests, tại sao chúng lại quan trọng, nhưng vì chưa bao giờ áp dụng vào 1 project nên mình cũng không để tâm quá nhiều và có mindset là cứ nhờ QA test là được rồi. Có dự án mà PO cũng phải nhảy vào test vì công ty không có quá nhiều QA 😂   

Công việc chính của anh em trong team bên cạnh dev feature mới là fix bug, fix bug và bug fix. Lí do vì:
- Mỗi lần update 1 đoạn logic để fix bug này thì nó lại tạo ra bug mới ở chỗ khác
- Bug fix rồi thì sau 1 thời gian lại bị reopen bởi 1 engineer nào đó thay đổi logic, …

Mọi chuyện còn tệ hơn khi dự án quá lớn theo thời gian và nó ***gần như không khả thi khi muốn refactor 1 phần business logic***.

{{< admonition note "Story" >}}
Có lần mình đã phải refactor 1 feature của app, và mình đã phải sửa gần 3000 lines of code. Lúc đó mình còn đang là sinh viên vẫn đang còn đi học & chưa có quá nhiều knghiem, và project thì không hề có unit tests 🥲 Sau vụ refactor đó thì team phải nhờ team QAs test lại toàn bộ app và tin tưởng rằng mọi thứ vẫn sẽ ổn (vì ngoài niềm tin ra thì mình không còn gì cả 🙂)
{{< /admonition >}}

Ở GxS nói riêng và các tech company nói chung, automation tests là 1 trong những phần quan trọng. Sau 2 năm bắt đầu dự án, project đã có hơn 3000 unit tests & UI tests với coverage ~90%. Ngoài ra team cũng thảo luận rất nhiều để đảm bảo mỗi ***unit test đều mang lại thêm protection cho codebase***    
(Mình đã có cơ hội xem codebase của 1 cty khác ở Singapore, cũng có coverage ~90%, tuy nhiên rất nhiều test chỉ để cho vui chứ không mang lại 1 chút lợi ích gì 🙂) 
   
Nhờ việc chú trọng vào automation tests, ***nó giảm bớt rất nhiều công việc cho QA và ngăn chặn các hidden bugs, tiết kiệm rất nhiều thời gian và tiền bạc cho công ty + đem lại trải nghiệm tốt hơn cho người dùng***.

1 trường hợp đặc biệt là đối với công ty out source, khách hàng là người đưa ra quyết định. Nhiều khi họ không biết nhiều về tech, nghĩ việc develop 1 cái app là đơn giản nên yêu cầu release liên tục và quyết định không cần test. Cho đến 1 thời điểm khi app quá lớn và việc thêm 1 tính năng hay refactor app gần như trở nên bất khả thi và quá tốn chi phí, khách hàng sẽ blame bạn vì đã để điều đó xảy ra.

## Be responsible, proactive, and be open

{{< admonition tip "Lesson" >}}
Nếu bạn muốn tiến xa hơn trong công việc, hãy có trách nhiệm, chủ động và open với lời khuyên từ người khác
{{< /admonition >}}

Khi mới gia nhập GxS, mình rất ấn tượng với thái độ làm việc của các kỹ sư ở đây. Mỗi cá nhân có thể làm việc hoàn toàn độc lập, chủ động và có trách nhiệm. Họ thể hiện như thế nào?

**Responsible**
- Với task mà họ đã pick và commit, họ sẽ luôn đưa ra 1 solution scalable và thực chứ không phải chỉ 1 solution tạm thời.
- Luôn cố gắng đảm bảo hoàn thành task trước deadline, nếu không kịp thì sẽ thông báo với team sớm để kịp thời để tìm hướng giải quyết.
- Luôn ready support ngay cả 11h đêm... Đúng kiểu gọi là có mặt, đến là đón.. 🫡
...

**Proactive** 
- Bên cạnh feature task, team có 1 dashboard chứa các ticket cần làm để cải thiện chất lượng project / cải thiện engineer experience / cải thiện performance (Mình thấy riêng vụ dashboard này cũng khá là hay 👍🏻). Các engineers trong team luôn chủ động pick các task trong board này khi họ có thời gian rảnh rỗi. 
- Trong project thì luôn proactive tìm hiểu về business của app, đóng góp ý kiến với backend, PM, designer để thay đổi requirement cho phù hợp, thay vì chỉ làm theo yêu cầu của PM 1 cách mù quáng.
...

**Be open**

Well, nói thật thì khi ở Việt Nam, có lúc mình đã gặp trường hợp những engineer không muốn nhận feedback từ engineer ít tuổi hơn, bạn bè mình cũng đã từng chia sẻ nhiều trường hợp như vậy. Ở GxS, mình thấy ai cũng rất open với mọi lời góp ý. Các engineers luôn tôn trọng lắng nghe và thảo luận với nhau. A leader của mình ở GxS hay bảo là “Không ai là biết hết mọi thứ” :3

> “In every man there is something wherein I may learn of him, and in that I am his pupil.” - Ralph Waldo Emerson”

## Working as a real team

{{< admonition tip "Lesson" >}}
If you want your team to become more effective, start working as a team, not coding "heroes"
{{< /admonition >}}

Trong những dự án mình từng trải qua, mỗi dự án phụ thuộc rất nhiều vào 2 hoặc 3 core engineers của team, trong khi các engineers khác trong nhóm chỉ làm những tasks không quá quan trọng.
Những core engineers này **làm tất cả những features khó nhất, review mọi MR + giữ quyền merge, chịu trách nhiệm chính về mọi features của dự án**. Tệ hơn nữa, khi các junior/middle engineer làm không tốt, **thì những core engineers này sẽ im lặng mà đập đi hết và xây lại từ đầu mà không cần discuss với junior/middle engineer để chỉ rằng họ đang làm sai ở đâu**.   

Vậy điều này thì có gì không tốt?    
- Điều này **cướp đi cơ hội học hỏi của junior/middle engineer**
- Core engineers nắm quá nhiều việc thì dần dần họ trở thành 1 phần không thể thay thế trong dự án, và cuối cùng thì họ **trở thành bottlneck của dự án**.
- core engineers blame juniors/middlé code chán nên họ phải làm thêm 1 đống việc, juniors trở nên tự ti hơn
...  

-> Team thiếu sự gắn kết + tin tưởng nhau.

> 1 vài articles hay về chủ đề này:    
> - Ex-leader của mình đã share bài viết này: [How to prevent coding "heroes" from destroying the team](https://hackernoon.com/thoughts-on-software-development-heroes-5ec656c2e31a)   
> - [True story: Công ty sa thải nhân viên giỏi nhất của họ](https://www.freecodecamp.org/news/we-fired-our-top-talent-best-decision-we-ever-made-4c0a99728fde/)

Ở GxS, các engineers luôn tin tưởng và tôn trọng lẫn nhau.   
Ví dụ như 1 junior engineer chưa đến 1 năm exp vẫn được giao cho take care cả 1 feature chính, reviews MR của middle/senior engineer, nhận trách nhiệm on-call, ... Hay khi 1 MR được raise lên, mọi người sẽ cùng nhau vào review + góp ý để engineer tự improve code của mình, …

> Teamwork makes dream work

## Sharing culture

{{< admonition tip "Lesson" >}}
Sharing is learning
{{< /admonition >}}

Bất cứ khi nào thấy điều gì cần được chia sẻ với team, chúng tôi sẽ đưa ra. Đó có thể là một issue, điều gì đó chưa tốt trong project, hoặc những điều mới có thể áp dụng để cải thiện chất lượng project,… Không đổ lỗi cho ai gây ra vấn đề mà cùng nhau thảo luận, tìm ra giải pháp và cùng nhau rút ra bài học.

Một số ví dụ về những gì chúng tôi đã làm:

- Trong quá trình review code, nếu implementation của bạn cần được ỉmprove, reviewer sẽ cho bạn biết lý do tại sao nó không tốt, một số tài liệu tham khảo bạn có thể xem qua, ...
- Trong khi fix bugs, nếu có issue nào cần team acknowledge và rút kinh nghiệm, chúng tôi sẽ raise lên để cùng discuss và học hỏi.
- Trước đây khi còn ở Việt Nam, có 1 cty mình làm cũng chia project ra thành nhiều team khác nhau. Tuy nhiên, engineer của team này hoàn toàn không biết team khác đang làm gì. Điều đó dẫn đến ***giới hạn sự học hỏi lẫn nhau của các engineers, mỗi engineer khi bị chuyển team thì cần thời gian thích nghi***, ...  
Ở GxS, project cũng chia thành nhiều team nhỏ khác nhau, tuy nhiên ***chúng tôi có team meeting hai tuần một lần để mỗi squad có thể chia sẻ về những gì họ đang làm và những điều mới họ đã học được trong quá trình thực hiện***, …

## Wrap up

Trên đây là những tư duy mình đã học được và tôi ước mình có thể học chúng sớm hơn. Nhưng không bao giờ là quá muộn để học. Hy vọng các bạn thấy nó hữu ích và áp dụng cho bản thân và nhóm của mình.
Enjoy!
