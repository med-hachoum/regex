
كتيب التعابير القياسية لمبرمج بايثون


# بحث عن عناوين url في النص


import re  
 
text = r"FIREVISION SPORTS features incredible Microprism Technology, which creates a glowing streak of light, day or night. When you activate your FIREVISION ball with a pair of cool FIREVISION Frames, you reveal a glow with a range over 100 feet/30 meters. The FIREVISION football is performance engineered to generate spiraling streaks of light whenever you turn on your FIREVISION Frames and throw it to a friend. Put glow in your game with the power of Microprism Technology and the FIREVISION Football! ​ ![Bright blazing light!](http://images.amazon.com/images/G/01/toys/detail- page/2011/B008592HH2-1.jpg) ​ **_FIREVISION Frames activate your ultra-bright glowing ball, day or night! _** ​ ![No charging!](http://images.amazon.com/images/G/01/toys/detail- page/2011/B008592HH2-2.jpg) ​"

my_regex = re.findall(r"(\(http[s]?:\/\/[\w\-\_\.\/]*)(\n)([\w\-\_\.\/]*\))", text)    

print(my_regex)

-------------------------------



# مطابقة واستخراج النص المتواجد بين الرمز /


import re  
 
text = r"/a1/a2/a3/a4/"

my_regex = re.findall(r"/.*/.*/.*/.*/", text)    

print(my_regex)

-------------------------------



# استخراج النص المتواجد بين وسوم content


import re  
 
text = r"[content] Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec tortor quam, gravida at nibh nec, vestibulum commodo felis. Cras eu ornare massa. Vivamus porta laoreet ullamcorper. Fusce metus ipsum, cursus ut fringilla ac, vulputate in orci. Nulla ultrices porttitor porttitor. Sed consectetur vel velit non sodales. Vivamus mi eros, facilisis et nulla sed, convallis lacinia orci. Morbi nec neque pulvinar tortor porttitor tincidunt. Praesent imperdiet finibus arcu, ac interdum lacus finibus eu. Duis et ante in tellus pulvinar elementum blandit nec mauris. Suspendisse eu lobortis nunc, ut volutpat metus. ​ Proin eu ligula cursus nibh tincidunt laoreet. Aliquam vel luctus metus, at feugiat lacus. Nullam rutrum eros ac nisl efficitur faucibus. Nullam tincidunt libero laoreet fringilla cursus. Curabitur ut fringilla nunc. Integer eget elementum lacus. Fusce mollis, sapien vitae euismod mattis, nisl tellus euismod nisi, in facilisis mi neque et urna. Maecenas sit amet metus blandit, volutpat ipsum sed, scelerisque tortor. Cras molestie euismod tellus, id bibendum enim ullamcorper id. Duis maximus augue orci, et congue ipsum consequat in. Maecenas auctor neque lectus, vitae lobortis lectus dapibus vel. Sed quis leo at odio pharetra sagittis maximus a massa. Nullam luctus rhoncus blandit. ​ Aenean ullamcorper nec augue quis hendrerit. In quis feugiat libero. In nec auctor ante. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis eget metus quis ex cursus blandit quis vel enim. Aliquam erat volutpat. Integer pharetra, nunc sed aliquam suscipit, urna sem vulputate felis, et efficitur dolor eros sed eros. Mauris eleifend orci eu ultricies cursus. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Integer efficitur magna lectus. ​ Morbi feugiat odio a ante dapibus, id pulvinar ex eleifend. Duis lobortis nibh non odio tincidunt convallis. Quisque ultrices et magna eget pretium. Pellentesque tempus sit amet magna quis rhoncus. Aenean a aliquet elit, ac placerat metus. Interdum et malesuada fames ac ante ipsum primis in faucibus. Curabitur pulvinar, urna et vehicula feugiat, augue quam mollis ipsum, eget sodales magna nisi facilisis lectus. Suspendisse fringilla ante nibh, et rhoncus est feugiat sed. Cras ut nisi ipsum. Cras auctor diam ut mi ultricies tincidunt. Fusce imperdiet scelerisque ligula vitae luctus. Pellentesque sodales ante quis ipsum viverra finibus. ​ Pellentesque gravida efficitur neque. Curabitur nec nunc hendrerit nunc rutrum tincidunt. Donec at nunc ut ante ullamcorper cursus quis sed metus. Fusce viverra massa leo, eget sodales metus feugiat at. Morbi vel pellentesque mi, vestibulum iaculis neque. Quisque ut nisl sagittis, auctor sem at, tristique ipsum. Praesent vitae ante ut est tincidunt tincidunt non volutpat justo. Aenean tristique quis lectus ut porttitor. [/content]"

my_regex = re.findall(r"\[content\]([\s\S]*?)\[\/content\]", text)    

print(my_regex)

-------------------------------



# مطابقة كلمات المرور مختلطة (حروف كبيرة وصغيرة ورموز وأرقام)


import re  
 
text = r"Password1_"

my_regex = re.findall(r"(?=^.{10,}$)(?=.*?\d)(?=.*?[a-z])(?=.*?[A-Z])(?=.*?[^a-zA-Z\d])", text)    

print(my_regex)

-------------------------------



# استخراج أرقام الهاتف


import re  
 
text = r"+33 10 69903282"

my_regex = re.findall(r"(^[+]\d+(?:[]\d+)*)", text)    

print(my_regex)

-------------------------------



# استخراج التواريخ كاملة بالاضافة الى الوقت


import re  
 
text = r"58.189.130.8 NULL-AUTH-USER 1/Jul/2013 03:27:12.818 +0900 GET /newnsmw/webresources/org.nns.entity.tenant/7ab0105f74f0cadbb20ddef606865b1c HTTP/1.1 200 2646 ​"

my_regex = re.findall(r"(0?[1-9]|1[0-2])\/(?:Jan|Feb|Mar|Apr|May|Jun|Jul|Aug|Sep|Oct|Nov|Dec)\/(1|2)[0-9]{3}\s((0|1)[0-9]|2[0-3]):([0-5][0-9]):([0-5][0-9])", text)    

print(my_regex)

-------------------------------



# التحقق من صحة الرمز البريدي الأرجنتيني


import re  
 
text = r"1001 1106 x1001abc 1111 AAAA a111111"

my_regex = re.findall(r"(^[a-z]{1}\d{4}[a-z]{3}$|^\d{4}$)", text)    

print(my_regex)

-------------------------------



# العثور على الأرقام الصحيحة


import re  
 
text = r"test 13231 test 123123 123 asdfasdf 1a2a3 a"

my_regex = re.findall(r"([\d]+)", text)    

print(my_regex)

-------------------------------



# استخراج التواريخ الطويلة (dd mmmm yyyy)


import re  
 
text = r"of 19 September 2006 in"

my_regex = re.findall(r"(?P<LongDate>(?P<Day>\d+)[\s]+(?P<Month>January|February|March|April|May|June|July|August|September|October|November|December)[\s]+(?P<Year>\d{4}))", text)    

print(my_regex)

-------------------------------



# IPv4 التحقق من عناوين


import re  
 
text = r"254.121.209.17"

my_regex = re.findall(r"^(([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])\.){3}([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])$", text)    

print(my_regex)

-------------------------------



# استخراج رموز المعيار آيزو 3166 لأسماء الدول والمقاطعات


import re  
 
text = r"BOSNIA AND HERZEGOWINA                          BA      BIH     070 BOTSWANA                                        BW      BWA     072 BOUVET ISLAND                                   BV      BVT     074 BRAZIL                                          BR      BRA     076 BRITISH INDIAN OCEAN TERRITORY                  IO      IOT     086 BRUNEI DARUSSALAM                               BN      BRN     096 BULGARIA                                        BG      BGR     100 BURKINA FASO                                    BF      BFA     854 BURUNDI                                         BI      BDI     108 CAMBODIA                                        KH      KHM     116 CAMEROON                                        CM      CMR     120 CANADA                                          CA      CAN     124 CAPE VERDE                                      CV      CPV     132 CAYMAN ISLANDS                                  KY      CYM     136 CENTRAL AFRICAN REPUBLIC                        CF      CAF     140 CHAD                                            TD      TCD     148 CHILE                                           CL      CHL     152 CHINA                                           CN      CHN     156"

my_regex = re.findall(r"(^.+?)\s+(\w{2})\s+(\w{3})\s+(\d{3})", text)    

print(my_regex)

-------------------------------



# استخراج آخر رقم من النص


import re  
 
text = r"CTRL_RADIOCOLUMNS_1 CTRL_RADIOCOLUMNS_22 CTRL_RADIOCOLUMNS_333 CTRL_RADIOCOLUMNS_4444"

my_regex = re.findall(r".*(\d+).*", text)    

print(my_regex)

-------------------------------



# التقاط متغيرات الاستعلام من روابط url


import re  
 
text = r"?foo=bar&?foo&foo=foo&foo&nonfoo=bar&nonfoo&foo#foofoo ?foo=bar&?foo&foo=foo&foo&nonfoo=bar&nonfoo&foo"

my_regex = re.findall(r"((?<=[\?\&])foo\=[^\&\#]*)|((?<=[\?\&])foo(?=[\&\#]))|((?<=[\?\&])foo(?!.))", text)    

print(my_regex)

-------------------------------



# البحث عن نطاق البريد الإلكتروني واستخراجه


import re  
 
text = r"From: <email@example.com> FROM name fails ​ Closed (fixed) Project: SMTP Authentication Support Version: 6.x-1.0-beta5 Component: Code Priority: Normal Category: Bug report Assigned: José San Martin Reporter: goose2000 Created: July 8, 2008 - 12:54 Updated: October 5, 2012 - 19:01 Log in or register to update this issue Jump to: Most recent attachment Hi, my development site is running on IIS with SMTP server. Mail is working fine when creating new users or getting a password reset. I have built a webform and upon submitting I'll get this error: ​ ​ * warning: mail() [function.mail]: SMTP server response: 501 5.5.4 Invalid Address in C:\Inetpub\wwwroot\BHI_dev\includes\mail.inc on line 193. * Unable to send e-mail. Please contact the site admin, if the problem persists. ​ The address I use in my testing are in fact completely valid. Seems like webform is not playing nice with the core somehow. Further ideas?"

my_regex = re.findall(r".*@(\S+)", text)    

print(my_regex)

-------------------------------



#  مطابقة النصوص فقط


import re  
 
text = r"Hi, you!"

my_regex = re.findall(r"(\w+)([\W+^\s])", text)    

print(my_regex)

-------------------------------

