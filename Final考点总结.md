# Final EXAM Review

## ExamFormat
- 120 mins + 10 mins reading time
- 120 marks
- 6 Questions
  - Covers the 6 key topics from this course
  - 10 marks per week spent;
  - HTML & CSS (20 marks)
  - JavaScript & Vue (20 marks)
  - User Experience (10 marks)
  - Client/Server & NodeJS (30 marks)
  - Databases (30 marks)
  - Security (10 marks)


## [HTML & CSS 点我](html&css&validationSummerize.md)
- HTML
  - Syntax & Semantics  
    tags eg. heading tag, paragraph tag, a tag;  
    attributes eg. href, src of image
    head, body是什么意？它们作用？它们里面放什么？放哪里？
- CSS
  - Syntax
   how do you structure style?不同种类的CSS优先级别？
  - Style Precedence
    理解html和CSS怎样相互作用的
- Validation
  What valid, what invalid? Validation的重要性？what can results if validation is unused?


## [JavaScript&Vue](javaScript&vueSummerize.md)
- JavaScript
  - Syntax & Semantics
  - DOM
  - Script loading
- Vue
  - Basic templating
  >简单的Vue例子？怎样set up它？怎样用它和HTML结合使用（）？
  - Attributes, classes & styles
  - Conditional & List rendering

## UserExperience
- Basic Principles of good website design
- Cognitive & Kinematic Load
  >怎样影响用户界面
- Semantic HTML
  >作用？
- WCAG 4 Principles of Accessibility
  >是什么？implications for a given website.  给定一个网页图，说说他哪里好，符合什么要素？

## Client/Server&NodeJS
- TCP/IP 5-layer model of the Internet
  >5层的作用？，怎样相互连接？
- URLs
  >URL的结构？每个部分的作用？和TCP/IP的关系？Protocol是什么？Protocol是属于哪个层的？hostname的作用？Portnumber?  _Can I run two node.js (express) servers on one machine? 如果可以，限制有哪些？它与哪一个Internet model有联系？_
- HTTP requests and Responses
  - Request types; GET/POST/HEAD etc.
  >熟悉不同的HTTP request种类。它们的简要结构？它们有何不同？它们的目的？认识到HTTP是**唯一**连接客户端和服务端的方法。客户端和服务端的连接方式和作用？  考试会让你demostrate your understanding， review and analys code, 要你做logical leaps
- Client vs Server side code
  - AJAX
  >AJAX和普通动态页面区别？优势和劣势？implications for 不同的TCP/IP层？
- Cookies & Sessions
  >它们的作用？implecations, performance, security,和服务端的
- Express Server architecture
  - Routes
  - Middleware
  >概念？

## Databases
- Basic Principles of Relational Databases
  > Advantages/Disadvantages to other storage methods?为甚不把一堆东西放在一个文件里？
- E-R models
  > Derive an E-R model from a description 看见它要理解它。attributes, relationship, etc......
- Relational Schemas
  > Adapt an E-R model to a relational schema
- Queries
  - Construct basic queries
  > SELECT, INSERT, CREATE, WHERE, JOIN, INNER JOIN, LEFT/RIGHT JOIN, NATURE JOIN, 多个JOIN一起用，选择特定的列, 
- Performance
  - Order of Operations and Performance challenges

## Security 
- Best practice for handling passwords and user data
 >熟悉 best practice fo handling, password hashing, password salting, how do they provide us with the security?
- Diferent types of threats and mitigation
  - Cross-Site Scripting (XSS)
  - SQL Injection
  - Cross-Site Request Forgery (XSRF)
  > 怎样工作的？怎样用它们来实施攻击？为什么能攻击？怎样避免被攻击？  Given a vunerable code, what the code vunerable to? If so, tell how to attack this? 回答一个攻击例子？怎样避免？
