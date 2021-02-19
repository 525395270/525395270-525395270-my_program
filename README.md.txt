在线考试系统的设计与实现

摘 要 在线考试系统旨在实现考试的无纸化管理，基于计算机和网络技术进行在线考试系统的使用，既方便校方对考试的管理，也方便了考生，尤其适合考生分布广，不易集中的远程教育。 基于远程教育的推广和在线考试需求的增加，本文设计并实现了一套在线考试系统。本系统实现了系统管理、考生管理、在线考试、在线制作试卷、控制学生考试、试卷审批等基本功能。同时，为确保系统安全运行和考试信息的机密性、完整性，本系统采用了SSL协议来加密传输的考试数据，并实现对服务器的认证。系统采用B/S开发模式，以JAVA作为开发平台，结合JSP、JavaScript、Html等语言，以Tomcat为服务器和SQL Server 2000为后台数据库。整个系统层次结构简单，操作容易，并具备一定的安全性。考生借助此系统，可以随时随地的进行课程结业考试，同样，老师使用该系统能更高效、便捷的组织在线考试。

关键词：在线考试系统；B/S模式；SSL Design and Implementation of Online Examination System Abstract The online examination system aims at achieving the paperless examination management. The online examination system, which bases on computer and network technology, is convenience for the exam management, but also for the students. Simultaneously, such a system is absolutely suitable for the students in distance education who are dispersive and difficult to concentrate on the course.
As the promotion of distance education and the increasing demand of the online examination, this paper presents the design and implementation of the on-line examination system. The system implements the following functions: system management, examinee management, online examinations, online production of the papers, control examinations and paper processing. Meanwhile, in order to ensure the system operating safe and the examination information confidential as well as integral, the system uses the SSL protocol to encrypt examination data and achieve the server authentication. The system bases on B/S development model, using Java as a development platform, which utilizes JSP, JavaScript, and Html language as well. The web server is Tomcat. Database server is SQL Server 2000. The system structure is simple, easy and safe. Examinee can exam at any time by using the system. Simultaneously teachers can use the system to organize online examination more efficiently and conveniently.

Key words: Online examination system; B/S pattern; SSL 2 系统需求分析 2.1 系统可行性分析 市场可行性分析 　　市场可行性分析主要是分析项目在实现后是否能够在市场中得到广泛应用，具备推广价值。本项目的目标用户主要是教育部门或培训机构等具备选择和判断考题题型的传统考核或未从传统考核方式中解脱出来的贫困山区，目前我国正在大力推进城乡一体化措施，贫困地区的教育资源会逐渐得到补充，传统人工考核的繁琐方式将会被逐渐取代。通过本系统可以解决传统的考核方式中人工计分的繁琐任务，具备一定的市场需求和推广价值。

技术可行性分析 　　技术可行性是通过对本项目实现所涉及的技术进行系统分析，找出技术难念及解决方案，保证系统在技术实现环节不出现灾难性问题而导致无法继续。本系统主要涉及到的是Web技术，这种技术的应用已经非常广泛，自身有着很多技术解决方案的积累，所以遇到问题应该都能找到很多资料进行查阅。Web技术是传统的B/S架构，它具有稳定性、可扩展性等优点，本项目最终决定选用JSP技术进行具体的实现。

应用可行性分析 　　目前我国还具备着传统人工计分的考核方式，教师亟需一种信息技术能够帮助他们解决繁琐的选择判断题型等具备固定答案的试题的批改计分问题，同时信息技术在人们日常生活中也得到广泛的使用，所以无论是管理者还是考生都对这种软件的管理方式熟悉了。所以，本系统在教育方面能够得到应用，并能解决传统教育考核的人工计分繁琐任务。

2.2 功能需求分析 　　在系统中不同类型的角色有着不同的功能需求，角色需要完成哪些工作，达到什么样的目标，系统需要分哪些模块去完成等等都是系统需求分析中需要考虑的重要因素，为了充分了解不同角色对系统的使用需求，我对不同角色进行了需求分析，主要的功能需求包括以下几个方面：

考生需求 　　考生是这个系统中用户量最多的角色，主要通过电脑浏览器进行登录完成考试，可以查看考试信息、完成的考试的成绩及个人信息。考生的登录初始账号统一由管理者进行添加分发，考生通过自行登录后，可以根据需求决定是否更改登录的密码，另外还提供一个个性化的个人信息头像上传功能。

　　考生角色登录系统时要求系统界面简单明了，能够符合大部分的考生的操作。关于最主要的考试功能，在考试期间需要可以导航到任意的题目号进行显示，需要可以显示出已经选择了答案的题目的答案并且能够更改原来选择的答案，需要可以在试题计时结束后自动提交试题答案，需要可以在提交试卷时进行试题的得分计算并且能够导航到成绩显示的页面供考生查看。除此，在考试的页面还需要给出适当的提示，如“离开此页面将没有成绩”等提示。大致的功能需求如图2-1所示：

管理者需求 　　管理者主要需要对整个系统进行管理，需要完成考试的发布和对已发布考试的删除，考生信息的录入、查看、修改、删除。在实际的应用中，一般情况下考生的数量都是大于40个人的，因而有必要在考生管理的页面进行考生信息的分页显示。管理者的需要完成的任务繁多，其中试题的录入这一项工作最为繁琐，因此，需要提供一个excel中间文件完成一次性上传考核的题目。为了保证试题录入的时系统的正确性，提供一个试题的模板给管理者参照录入自己需要考核的题目，并且提供考试相关信息描述的录入，如考试时间，考试的描述（期中考试，期末考试，英语考试，物理考试）。



