# ДЗ1: Attention своими руками
# ДЗ1: охота за багами

Сыылка на Google Colab для "dz1_attention.ipynb": https://colab.research.google.com/drive/1_Emz5A67V4sAxvZ5c7Jcb-TJWaak06YE?usp=sharing

Сыылка на Google Colab для "dz1_bughunt.ipynb": https://colab.research.google.com/drive/1MD9czv6FzFAV1HARCy6xk8byVusxBQcQ?usp=sharing


Далее расписано как запустить запустить локально  в виртуальном окружении.

## Требования

- Python 3.10 или новее
- pip
- Доступ к интернету для первичной установки зависимостей

## Создание виртуального окружения

Из корня проекта выполните:

```bash
python -m venv .venv
```

Активируйте окружение:

### Linux / macOS

```bash
source .venv/bin/activate
```

### Windows PowerShell

```powershell
.\.venv\Scripts\Activate.ps1
```

### Windows CMD

```cmd
.venv\Scripts\activate.bat
```

## Установка зависимостей

Обновите pip и установите зафиксированные зависимости:

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

Для CPU-only версии PyTorch вместо предыдущей установки выполните:

```bash
pip install torch==2.5.1 --index-url [https://download.pytorch.org/whl/cpu](https://download.pytorch.org/whl/cpu)
```

## Запуск ноутбука

Установите Jupyter и запустите ноутбук:

```bash
pip install jupyterlab
jupyter lab
```

Затем откройте `dz1-attention.ipynb` и выполните ячейки сверху вниз.

Альтернативно, в VS Code установите расширение **Jupyter**, выберите интерпретатором `.venv/bin/python`
(Linux/macOS) или `.venv\Scripts\python.exe` (Windows) и запускайте ячейки в ноутбуке.

## Проверка задания

В конце ноутбука находится ячейка:

```python
failures = run(implementation)
```

Выполните её после реализации всех `TODO`. Ожидаемый результат:

```text
пройдено 18 из 18
Все проверки зелёные.
```

## Воспроизводимость

- Все сторонние зависимости зафиксированы в `requirements.txt`.
- Виртуальное окружение изолирует установленные пакеты от глобального Python.
- Для одинаковых численных результатов в проверках заданы `torch.manual_seed(...)`.
- Не меняйте версии PyTorch без необходимости: результаты тестов рассчитаны на совместимость с современными стабильными версиями.