# نظام حجز الفنادق - Hotel Booking System

نظام شامل لحجز الفنادق مبني باستخدام تقنيات حديثة مع لوحة تحكم إدارية متقدمة.

## التقنيات المستخدمة

### الواجهة الأمامية (Frontend)
- **Next.js 15** - إطار عمل React للتطبيقات الحديثة
- **TypeScript** - للكتابة الآمنة والمنظمة
- **Tailwind CSS** - للتصميم السريع والمتجاوب
- **Lucide React** - مكتبة الأيقونات

### الواجهة الخلفية (Backend)
- **Express.js** - إطار عمل Node.js للخادم
- **MongoDB** - قاعدة بيانات NoSQL
- **Mongoose** - مكتبة ODM لـ MongoDB
- **JWT** - للمصادقة والتفويض
- **bcryptjs** - لتشفير كلمات المرور

## الميزات الرئيسية

### للعملاء
- ✅ تصفح الفنادق والغرف المتاحة
- ✅ البحث والتصفية حسب المعايير المختلفة
- ✅ حجز الغرف مع اختيار التواريخ
- ✅ إدارة الحجوزات الشخصية
- ✅ عرض تفاصيل الفنادق والمرافق

### للمديرين ومديري الفنادق
- ✅ لوحة تحكم شاملة مع الإحصائيات
- ✅ إدارة الفنادق (إضافة، تعديل، حذف)
- ✅ إدارة الغرف والأسعار
- ✅ إدارة الحجوزات (تأكيد، إلغاء)
- ✅ إدارة المستخدمين (للمديرين فقط)

### الأمان والحماية
- ✅ تشفير كلمات المرور
- ✅ نظام JWT للمصادقة
- ✅ حماية المسارات حسب الأدوار
- ✅ التحقق من صحة البيانات

## هيكل المشروع

```
hotel_booking_system/
├── hotel_booking_system_backend/     # الواجهة الخلفية
│   ├── models/                       # نماذج قاعدة البيانات
│   ├── routes/                       # مسارات API
│   ├── controllers/                  # متحكمات العمليات
│   ├── middleware/                   # وسطاء المصادقة
│   └── index.js                      # نقطة البداية
└── hotel_booking_system_frontend/    # الواجهة الأمامية
    ├── src/
    │   ├── app/                      # صفحات Next.js
    │   ├── components/               # المكونات المشتركة
    │   ├── contexts/                 # سياقات React
    │   ├── lib/                      # مكتبات مساعدة
    │   └── types/                    # تعريفات TypeScript
    └── package.json
```

## التثبيت والتشغيل

### المتطلبات الأساسية
- Node.js (الإصدار 18 أو أحدث)
- MongoDB
- npm أو yarn

### 1. تثبيت التبعيات

#### الواجهة الخلفية
```bash
cd hotel_booking_system_backend
npm install
```

#### الواجهة الأمامية
```bash
cd hotel_booking_system_frontend
npm install
```

### 2. إعداد متغيرات البيئة

#### الواجهة الخلفية (.env)
```env
MONGO_URI=mongodb://localhost:27017/hotel_booking
JWT_SECRET=your_jwt_secret_key_here
```

#### الواجهة الأمامية (.env.local)
```env
NEXT_PUBLIC_API_URL=http://localhost:5000/api
```

### 3. إدخال البيانات التجريبية
```bash
cd hotel_booking_system_backend
node seed.js
```

### 4. تشغيل التطبيق

#### تشغيل الواجهة الخلفية
```bash
cd hotel_booking_system_backend
npm start
```
الخادم سيعمل على: http://localhost:5000

#### تشغيل الواجهة الأمامية
```bash
cd hotel_booking_system_frontend
npm run dev
```
التطبيق سيعمل على: http://localhost:3000

## بيانات تسجيل الدخول التجريبية

### مدير النظام
- **البريد الإلكتروني:** admin@example.com
- **كلمة المرور:** admin123
- **الصلاحيات:** إدارة كاملة للنظام

### مدير فندق
- **البريد الإلكتروني:** manager@example.com
- **كلمة المرور:** manager123
- **الصلاحيات:** إدارة الفنادق والحجوزات

### عميل
- **البريد الإلكتروني:** customer@example.com
- **كلمة المرور:** customer123
- **الصلاحيات:** تصفح وحجز الفنادق

## واجهات برمجة التطبيقات (API)

### المصادقة
- `POST /api/auth/register` - تسجيل مستخدم جديد
- `POST /api/auth/login` - تسجيل الدخول

### الفنادق
- `GET /api/hotels` - جلب جميع الفنادق
- `GET /api/hotels/:id` - جلب فندق محدد
- `POST /api/hotels` - إضافة فندق جديد (مديرين فقط)
- `PUT /api/hotels/:id` - تحديث فندق (مديرين فقط)
- `DELETE /api/hotels/:id` - حذف فندق (مديرين فقط)

### الغرف
- `GET /api/rooms` - جلب جميع الغرف
- `GET /api/rooms/hotel/:hotelId` - جلب غرف فندق محدد
- `POST /api/rooms` - إضافة غرفة جديدة (مديرين فقط)
- `PUT /api/rooms/:id` - تحديث غرفة (مديرين فقط)
- `DELETE /api/rooms/:id` - حذف غرفة (مديرين فقط)

### الحجوزات
- `GET /api/bookings` - جلب جميع الحجوزات
- `GET /api/bookings/user` - جلب حجوزات المستخدم الحالي
- `POST /api/bookings` - إنشاء حجز جديد
- `PUT /api/bookings/:id/status` - تحديث حالة الحجز (مديرين فقط)
- `DELETE /api/bookings/:id` - إلغاء حجز

## المساهمة

نرحب بالمساهمات! يرجى اتباع الخطوات التالية:

1. Fork المشروع
2. إنشاء فرع للميزة الجديدة (`git checkout -b feature/AmazingFeature`)
3. Commit التغييرات (`git commit -m 'Add some AmazingFeature'`)
4. Push للفرع (`git push origin feature/AmazingFeature`)
5. فتح Pull Request

## الترخيص

هذا المشروع مرخص تحت رخصة MIT - راجع ملف [LICENSE](LICENSE) للتفاصيل.

## الدعم

إذا واجهت أي مشاكل أو لديك أسئلة، يرجى فتح issue في المستودع.

---

تم تطوير هذا المشروع باستخدام أحدث التقنيات لضمان الأداء والأمان والقابلية للتوسع.

