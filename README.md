kidprogram
==========

เป็นโปรแกรมที่ให้เด็กๆสั่งงานเจ้าแมวด้วยคำสั่งง่ายๆได้แก่

	- เดิน
	- ซ้ายหัน
	- ขวาหัน

โดยใส่คำสั่งละบรรทัดแล้วกดปุ่ม Run เจ้าแมวก็จะทำตามคำสั่งทีละบรรทัด

เครื่องมือที่ใช้สร้าง
==================

สร้างด้วย HTML , Javascript แต่ว่าใช้ library ช่วยสองตัวด้วยกันคือ [Processing JS](http://processingjs.org/) และ [jQuery](http://jquery.com/) โดย processingjs นั่นใช้ช่วยวาดภาพ ส่วน jquery เอาไว้เขียนรับ event

โครงสร้างโค้ด
============

ตอนนี้ที่ทำไปมีโค้ดหลักๆสองส่วนคือ

	- index.html ตรงนี้ทำการ โหลด jQuery และ ProcessingJS เข้ามาผ่าน CDN แล้วก็จัดการสร้าง Canvas แล้วกำหนดว่าสคริปของ ProcessingJS อยู่ที่ไฟล์ไหน เพราะว่า ProcessingJS จำเป็นต้องวาดรูปลงที่ Canvas ที่เหลือคือกำหนดตัวแปร global ไว้สองตัวคือ p ไว้เก็บตำแหน่งจุดซึ่งตอนนี้จุดแนวนอนคือ px และ py มีค่าระหว่าง [0-4] และตัวแปร direction ไว้บอกว่าตอนนี้แมวหันหน้าไปทางไหน ใช้ตัวเลขแทนคือ [บน = 1, ขวา = 2, ล่าง = 3, ซ้าย = 4] แล้วก็อีเว้นของปุ่ม Run เมื่อกดแล้วจะทำการ parse ค่าจาก textarea ให้เป็น array ของคำสั่ง

	- board.pde ไฟล์ pde จะเป็น script ของ ProcessingJS ซึ่งเราจะเตรียมฟังก์ชันต่างๆที่จำเป็นสำหรับการวาดรูปด้วย processingjs เช่น setup จะถูกเรียกครั้งแรกก่อนวาด และ draw จะถูกเรียกทุกครั้งในการวาดแต่ละเฟรม ส่วนฟังก์ชัน walk , turnLeft , turnRight สร้างมาเพื่อปรับทิศทางและตำแหน่งการวาดรูปแมวให้ถูกต้อง ในคำสั่ง draw ก็จะเช็คว่ามีคำสั่งใน array ของคำสั่งหรือไม่ ถ้ามีก็จะเรียกคำสั่ง ที่สร้างมาเมื่อกี้ให้เรียบร้อยก่อน วาดรูปออกไป

Contributors
============

Weerasak Chongnguluam (singpor@gmail.com)
Thanabodee Charoenpiriyakij (wingyminus@gmail.com)
Piyathida Kaewtapan (piyathida.k7@gmail.com)
Hassadee Pimsuwan (hapztron@gmail.com)
