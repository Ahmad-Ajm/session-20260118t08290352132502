# Features Map – Project Feature Inventory

## Overview
هذه الخريطة تجمع ميزات المنتج (MVP) لتطبيق إنشاء سيرة ذاتية مع تسجيل/تسجيل دخول.

**Stack (افتراض منطقي لحين التأكيد):**
- Backend: .NET 8 (ABP-style) + REST API
- Frontend: Angular 17
- DB: PostgreSQL

---

## Features Table

| FeatureId | FeatureName | FeatureType | Summary | Personas | SpecFolders | Priority | Status |
|---|---|---|---|---|---|---|---|
| FEAT-001-UXUI | UX/UI Baseline (Shell) | CRUD | هيكل واجهة أساسي (Layout + Routing + صفحات Placeholder) بدون منطق معقد | User, Admin | psec-kit-file/FEAT-001-UXUI | P0 | Planned |
| FEAT-USER-REGISTRATION | User Registration & Auth | Security | تسجيل/تسجيل دخول/خروج + جلسة + حراسة مسارات | User | psec-kit-file/FEAT-USER-REGISTRATION | P0 | In-Progress |
| FEAT-CV-CREATION | CV Creation | CRUD | إنشاء/تعديل/معاينة السيرة الذاتية مع أقسام التعليم/الخبرات/المهارات | User | psec-kit-file/FEAT-CV-CREATION | P0 | In-Progress |

---

## Feature Details

### FEAT-001-UXUI – UX/UI Baseline (Shell)
**Type:** CRUD  
**Summary:** تجهيز واجهة التطبيق الأساسية (Routing, Layout, Navigation, صفحة رئيسية) وشاشات Placeholder للميزات الأخرى.  
**Personas:** User, Admin  
**Spec Folders / Files:**
- `psec-kit-file/FEAT-001-UXUI/*`

**Dependencies / Relations:**
- تؤثر على: كل الميزات (الواجهة أساس لها)

**KPI Template:** `specifications/12-testing/kpi-crud-template.md`

**Notes:**
- لا نحتاج تفاعل معقد في هذه الميزة؛ الهدف Shell يعمل.

### FEAT-USER-REGISTRATION – User Registration & Auth
**Type:** Security  
**Summary:** تسجيل مستخدم جديد، تسجيل الدخول، إدارة الجلسة، صفحة الملف الشخصي الأساسية، وحماية المسارات.  
**Personas:** User  
**Spec Folders / Files:**
- `psec-kit-file/FEAT-USER-REGISTRATION/*`

**Dependencies / Relations:**
- تعتمد على: FEAT-001-UXUI (routing/layout)
- تؤثر على: FEAT-CV-CREATION (يتطلب مستخدم)

**KPI Template:** `specifications/12-testing/kpi-security-template.md`

### FEAT-CV-CREATION – CV Creation
**Type:** CRUD  
**Summary:** CRUD لسيرة ذاتية واحدة أو متعددة لكل مستخدم + محرر أقسام + معاينة/تصدير (لاحقًا).  
**Personas:** User  
**Spec Folders / Files:**
- `psec-kit-file/FEAT-CV-CREATION/*`

**Dependencies / Relations:**
- تعتمد على: FEAT-USER-REGISTRATION (هوية المستخدم)

**KPI Template:** `specifications/12-testing/kpi-crud-template.md`
