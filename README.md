# ДЗ 1 «Фотолаборатория»

Инструмент `photolab.py` (Python 3, зависимости — `pip install -r requirements.txt`). Самопроверка: `pytest tests -q`.
Отчёт с числами и ответами — `REPORT.md`. Все файлы в `out/` получены командами ниже (из корня репозитория):

```bash
python photolab.py gamma data/dark.jpg --gamma 0.5 -o out/dark_g05.jpg --hist out/dark_g05_hist.png
python photolab.py gamma data/dark.jpg --gamma 2.0 -o out/dark_g20.jpg --hist out/dark_g20_hist.png
python photolab.py wb data/bright.jpg --method grey-world -o out/bright_gw.jpg --hist out/bright_gw_hist.png
python photolab.py wb data/bright.jpg --method white-patch -o out/bright_wp.jpg --hist out/bright_wp_hist.png
python photolab.py wb data/bg.jpg --method grey-world -o out/window_gw.jpg
python photolab.py clahe data/dark.jpg --clip 2 --tiles 8 -o out/dark_clahe.jpg --compare out/dark_cmp.jpg --hist out/dark_clahe_hist.png
python photolab.py chromakey data/object.jpg --bg data/bg.jpg --sample 466,815,233,233 -o out/object_on_bg.jpg --mask out/object_mask.png
python photolab.py rotate data/poster.jpg --deg 30 -o out/poster_rot30.jpg
python photolab.py rotate data/poster.jpg --deg -137 -o out/poster_rot-137.jpg
python photolab.py resize data/text.jpg --scale 0.25 --report -o out/text_x025.jpg
python photolab.py resize data/text.jpg --scale 0.25 --method naive -o out/text_x025_naive.jpg
python photolab.py resize data/text.jpg --scale 0.25 --method blur -o out/text_x025_blur.jpg
python photolab.py resize data/text.jpg --scale 2 -o out/text_x2.jpg
python photolab.py rectify data/poster.jpg --corners 1417,1132,97,553,553,1627,726,314 --aspect 0.647 -o out/poster_front.jpg
python photolab.py rectify data/poster.jpg --corners 97,553,726,314,1417,1132,553,1627 -o out/poster_front_by_sides.jpg
python photolab.py sheet data/dark.jpg data/bright.jpg data/object.jpg data/bg.jpg data/poster.jpg data/text.jpg out/dark_clahe.jpg out/bright_gw.jpg out/object_on_bg.jpg out/poster_front.jpg out/poster_rot30.jpg out/text_x025.jpg --cols 4 -o out/sheet.jpg
```

Команды для кадров курса (`out/course/`) — в `REPORT.md`, раздел 4.
