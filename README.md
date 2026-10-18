# Cnpm-2026.1


## Cấu trúc thư mục dự kiến (Project Structure V1)

**Phân công trách nhiệm:**
- TV1: Frontend Lead – Giao diện nhân viên và các thành phần UI chung.
- TV2: Frontend Developer – Giao diện quản trị và báo cáo.
- TV3: Backend Developer – Nghiệp vụ xe vào, xe ra, tính phí, thanh toán.
- TV4: Backend Lead – Kiến trúc, xác thực, quản trị và thống kê.
- TV5: Database & Integration – CSDL, models, repositories và tích hợp dữ liệu.

### Cây thư mục

```text
parking-management-system/
│
├── frontend/                           # TV1 + TV2
│   ├── public/
│   ├── src/
│   │   ├── app/                        # TV1
│   │   │   ├── App.jsx
│   │   │   └── router.jsx
│   │   │
│   │   ├── shared/                     # TV1
│   │   │   ├── components/
│   │   │   ├── layouts/
│   │   │   ├── styles/
│   │   │   └── api/
│   │   │       └── client.js
│   │   │
│   │   └── features/
│   │       ├── auth/                   # TV1
│   │       │   ├── LoginPage.jsx
│   │       │   └── authApi.js
│   │       │
│   │       ├── parking/                # TV1
│   │       │   ├── CheckInPage.jsx
│   │       │   ├── CheckOutPage.jsx
│   │       │   ├── ParkingLookupPage.jsx
│   │       │   └── parkingApi.js
│   │       │
│   │       ├── admin/                  # TV2
│   │       │   ├── ParkingConfigPage.jsx
│   │       │   ├── PricingPage.jsx
│   │       │   ├── UserManagementPage.jsx
│   │       │   └── adminApi.js
│   │       │
│   │       └── reports/                # TV2
│   │           ├── ParkingStatisticsPage.jsx
│   │           ├── RevenueReportPage.jsx
│   │           └── reportApi.js
│   │
│   ├── package.json
│   └── vite.config.js
│
├── backend/                            # TV3 + TV4 + TV5
│   ├── app/
│   │   ├── __init__.py                 # TV4
│   │   │
│   │   ├── core/                       # TV4
│   │   │   ├── config.py
│   │   │   ├── security.py
│   │   │   └── error_handlers.py
│   │   │
│   │   ├── modules/
│   │   │   ├── operations/             # TV3
│   │   │   │   ├── routes.py
│   │   │   │   ├── schemas.py
│   │   │   │   ├── checkin_service.py
│   │   │   │   ├── lookup_service.py
│   │   │   │   ├── checkout_service.py
│   │   │   │   ├── fee_calculator.py
│   │   │   │   └── payment_service.py
│   │   │   │
│   │   │   ├── auth/                   # TV4
│   │   │   │   ├── routes.py
│   │   │   │   └── service.py
│   │   │   │
│   │   │   ├── admin/                  # TV4
│   │   │   │   ├── routes.py
│   │   │   │   └── service.py
│   │   │   │
│   │   │   ├── pricing/                # TV4
│   │   │   │   ├── routes.py
│   │   │   │   └── service.py
│   │   │   │
│   │   │   └── reports/                # TV4
│   │   │       ├── routes.py
│   │   │       └── service.py
│   │   │
│   │   └── persistence/                # TV5
│   │       ├── db.py
│   │       ├── models/
│   │       │   ├── user.py
│   │       │   ├── parking_session.py
│   │       │   ├── parking_config.py
│   │       │   ├── pricing_rule.py
│   │       │   └── payment.py
│   │       │
│   │       └── repositories/
│   │           ├── user_repository.py
│   │           ├── session_repository.py
│   │           ├── config_repository.py
│   │           ├── pricing_repository.py
│   │           └── payment_repository.py
│   │
│   ├── tests/
│   │   ├── unit/
│   │   │   ├── test_operations.py      # TV3
│   │   │   └── test_admin.py           # TV4
│   │   └── persistence/
│   │       └── test_repositories.py    # TV5
│   │
│   ├── requirements.txt
│   └── run.py
│
├── database/                           # TV5
│   ├── migrations/
│   ├── seed/
│   └── diagrams/
│
├── contracts/                          # Cả nhóm
│   ├── openapi.yaml
│   ├── error-codes.md
│   └── data-dictionary.md
│
├── tests/
│   ├── integration/
│   └── e2e/
│
├── docs/                               # Báo cáo IT3180
│   ├── 01-survey/
│   ├── 02-requirements/
│   ├── 03-analysis/
│   ├── 04-design/
│   ├── 05-implementation/
│   ├── 06-testing/
│   └── 07-user-guide/
│
├── .env.example
├── .gitignore
└── README.md
```

- Các thành viên phụ trách module của mình nhưng phải tuân thủ quy ước chung về cấu trúc mã nguồn.
- Những thay đổi ảnh hưởng đến module dùng chung cần được trao đổi và review trước khi tích hợp.
