# vk_bot2

Скрипты для выгрузки постов из групп ВКонтакте и скачивания прикреплённых видео.

## Что делает

- `part_one.py` — забирает последние посты со стены группы через `wall.get` (VK API 5.52) и сохраняет их в JSON.
- `part_two.py` — то же плюс скачивание видео из постов через `yt-dlp`.

## Установка

```bash
git clone https://github.com/den1ss666/vk_bot2.git
cd vk_bot2
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
cp auth_data.example.py auth_data.py   # и впиши свой токен
```

Токен VK создаётся на [dev.vk.com](https://dev.vk.com/ru/access-token) с правами `wall`, `video`, `offline`.

## Запуск

```bash
python part_one.py      # только посты
python part_two.py      # посты + видео
```

Группа задаётся доменом (например, `durov`), результат складывается в JSON рядом со скриптом.

## Замечания

- `auth_data.py` в `.gitignore` — реальный токен в репозиторий не попадает.
- VK API 5.52 устарел; если методы начнут отвечать ошибкой, подними версию `v` в URL запроса.
- `youtube_dl` больше не поддерживается, используется `yt-dlp`.
- Скачивание контента — только для своих групп или с разрешения правообладателя.

## Лицензия

MIT, см. [LICENSE](LICENSE).
