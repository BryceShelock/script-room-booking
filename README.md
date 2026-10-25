# Script Room Booking

剧本杀房间的预订、评价和推荐系统。后端是 Django REST API，另有一个桌面客户端。

## 能力

- **预订**：剧本房间和预约（`booking/`）
- **评价**：用户评价，并用 TextBlob 做情感分析（`reviews/`）
- **推荐**：内容匹配、SVD 协同过滤和热度按 0.4 / 0.4 / 0.2 加权（`recommendation/services.py`，scikit-surprise）
- **用户**：账号、偏好和积分相关数据（`users/`）
- **桌面端**：`desktop_app/`

## 运行

```bash
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```

接口前缀：

| 前缀 | 模块 |
| --- | --- |
| `/api/users/` | 用户 |
| `/api/booking/` | 房间与预订 |
| `/api/reviews/` | 评价 |
| `/api/recommendation/` | 推荐 |
| `/admin/` | Django 后台 |

开发库是 SQLite。推荐在有评分数据后才会给出协同过滤结果；数据少时主要靠内容和热度。

课程项目里完成的可本地运行原型。MIT License。
