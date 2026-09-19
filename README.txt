المحسن ستور - نسخة GitHub جاهزة

المحتويات:
- index.html: واجهة المتجر بنفس التصميم.
- login.html: تسجيل الدخول وإنشاء حساب مشتري أو بائع.
- checkout.html: إتمام الطلب.
- payment.html: صفحة الدفع.
- admin.html: لوحة المدير لإضافة المنتجات ومراجعة طلبات البائعين.
- config.js: إعدادات Supabase.
- database.sql: الجداول والصلاحيات وطلبات البائعين.

إعداد أول مرة:
1) ضع SUPABASE_PUBLISHABLE/ANON KEY في config.js.
2) افتح Supabase > SQL Editor ونفّذ database.sql كاملًا.
3) أنشئ حسابك من login.html.
4) من Supabase > Authentication > Users انسخ User ID لحسابك.
5) نفّذ في SQL Editor:
   insert into public.admin_users(user_id) values ('USER-ID-HERE');
6) سجّل دخولك وافتح admin.html.

البائع:
- عند إنشاء الحساب يختار «بائع» ويكتب الاسم، البريد، الهاتف، اسم المتجر والعنوان.
- يتم إنشاء طلب بائع تلقائيًا في seller_requests.
- المدير يرى التفاصيل من admin.html ويمكنه تغيير الحالة إلى مقبول أو مرفوض.
- كلمة المرور لا يتم حفظها في seller_requests ولا تصل للمدير.

ملاحظة مهمة:
هذه النسخة ترسل تفاصيل البائع إلى لوحة المدير داخل الموقع عبر Supabase. إرسال إشعار بريد إلكتروني تلقائي للمدير يحتاج خدمة بريد (مثل Resend/SMTP) وEdge Function، لذلك لم يتم الادعاء بأنه يعمل تلقائيًا بدون إعداد خدمة بريد.
