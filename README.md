# MLOps. Практическое задание №1

ЭТАПЫ ВЫПОЛНЕНИЯ ЗАДАЧИ:

1. Создать git репозиторий на github.com<br />
   ВЫПОЛНЕНО
   
2. Создать две виртуальные машины в virtualbox: для хранения данных (data_srv), для обучения модели ML (ml_srv)
      <img src="https://github.com/PrintSmart/MLOps_HW1/blob/main/screen/VB.JPG" />
Установить ОС (linux, рекомендуемая Ubuntu).
Настроить сетевые интерфейсы (NAT).
Прокинуть порт, запустить sshd и сделать подключение по ssh.

3. В хранилище данных data_srv:

Загрузить датасет (произвольный, свой).
Клонировать репозиторий проекта.
Инициализировать git и dvc, сохранить в git (commit -m “Init project”).
Организовать удаленное ssh хранилище, сохранить настройки в git и dvc(commit -m “Remote ssh server configuration”).

4. В виртуальной машине ml_srv:
Установить dvc, осуществить клонирование репозитория из git и загрузку датасетов из dvc.
Установить venv, запустить виртуальное окружение.
Установить VSCode и сделать удаленное подключение к ml_srv через прокинутый порт по ssh, открыть рабочий репозиторий.
Создать в dvc этап (stage) отбора признаков, сохранить в features.
Создать в dvc этап (stage) преобразования признаков, сохранить в prepared.
Проверить качество работы пайплайна данных командой dvc repro.
Осуществить сохранение полученных артефактов в git иdvc (commit -m “Data pipeline”).
Создать в dvc этап (stage) обучения модели, гиперпараметры использовать из файла params.yaml.
Выполнить обучение модели dvc командой dvc repro, проверить правильность, сохранить результаты в git и dvc (commit -m “ML model with parameters”).
Добавить скрипт для оценки метрики, сохранение в файл evaluate.json, метрику добавить под контроль dvc (флаг -M), проверить правильность, результаты сохранить в git и dvc(commit -m “Baseline”).
Осуществить запуск пайплайна модели с изменением параметров, сохранением метрик, контролем экспериментов, добиться лучшей метрики, сохранить в git и dvc (commit-m “Experiment 1”).
