import telebot
import random
import time
import sqlite3
import pymorphy2

bot = telebot.TeleBot('NUM')

morph = pymorphy2.MorphAnalyzer()

d = '''Австралия\tКанберра
Австрия	Вена
Азербайджан	Баку
Албания	Тирана
Алжир	Алжир
Ангола	Луанда
Андорра	Андорра-ла-Велья
Антигуа и Барбуда	Сент-Джонс
Аргентина	Буэнос-Айрес
Армения	Ереван
Афганистан	Кабул
Багамы	Нассау
Бангладеш	Дакка
Барбадос	Бриджтаун
Бахрейн	Манама
Беларусь	Минск
Белиз	Бельмопан
Бельгия	Брюссель
Бенин	Порто-Ново
Болгария	София
Боливия	Сукре
Ботсвана	Габороне
Бразилия	Бразилиа
Бруней	Бандар-Сери-Багаван
Буркина Фасо	Уагадугу
Бурунди	Бужумбура
Бутан	Тхимпху
Вануату	Порт-Вила
Ватикан	Ватикан
Великобритания	Лондон
Венгрия	Будапешт
Венесуэла	Каракас
Восточный Тимор	Дили
Вьетнам	Ханой
Габон	Либревиль
Гаити	Порт-о-Пренс
Гайана	Джорджтаун
Гамбия	Банжул
Гана	Аккра
Гватемала	Гватемала
Гвинея	Конакри
Гвинея-Бисау	Бисау
Германия	Берлин
Гондурас	Тегусигальпа
Гренада	Сент-Джорджес
Греция	Афины
Грузия	Тбилиси
Дания	Копенгаген
Джибути	Джибути
Доминикан	Розо
Доминиканская Республика	Санто-Доминго
Египет	Каир
Замбия	Лусака
Зимбабве	Хараре
Израиль	Иерусалим
Индия	Нью-Дели
Индонезия	Джакарта
Иордания	Амман
Ирак	Багдад
Иран	Тегеран
Ирландия	Дублин
Исландия	Рейкьявик
Испания	Мадрид
Италия	Рим
Йемен	Сана
Кабо-Верде	Прая
Казахстан	Астана
Камбоджа	Пномпень
Камерун	Яунде
Канада	Оттава
Катар	Доха
Кения	Найроби
Кипр	Никосия
Киргизия	Бишкек
Кирибати	Южная Тарава
Китай	Пекин
Колумбия	Санта-Фе-де-Богота
Коморы	Морони
Коста-Рика	Сан-Хосе
Кот-д’Ивуар	Ямусукро
Куба	Гавана
Кувейт	Эль-Кувейт
Лаос	Вьентьян
Латвия	Рига
Лесото	Масеру
Либерия	Монровия
Ливан	Бейрут
Ливия	Триполи
Литва	Вильнюс
Лихтенштейн	Вадуц
Люксембург	Люксембург
Маврикий	Порт-Луи
Мавритания	Нуакшот
Мадагаскар	Антананариву
Македония	Скопье
Малави	Лилонгве
Малайзия	Куала-Лумпур
Мали	Бамако
Мальдивы	Мале
Мальта	Валлетта
Марокко	Рабат
Маршалловы Острова	Маджуро
Мексика	Мехико
Мозамбик	Мапуту
Молдавия	Кишинев
Монако	Монако
Монголия	Улан-Батор
Мьянма	Найпьидо
Намибия	Виндхук
Непал	Катманду
Нигер	Ниамей
Нигерия	Абуджа
Нидерланды	Амстердам
Никарагуа	Манагуа
Новая Зеландия	Веллингтон
Норвегия	Осло
Объединенные Арабские Эмираты	Абу-Даби
Оман	Маскат
Пакистан	Исламабад
Палау	Мелекеок
Панама	Панама
Новая Гвинея	Порт-Морсби
Парагвай	Асунсьон
Перу	Лима
Польша	Варшава
Португалия	Лиссабон
Россия	Москва
Руанда	Кигали
Румыния	Бухарест
Сальвадор	Сан -   Сальвадор
Самоа	Апиа
Сан - Марино	Сан - Марино
Саудовская Аравия	Эр - Рияд
Свазиленд	Мбабане
Северная Корея	Пхеньян
Сейшелы	Виктория
Сенегал	Дакар
Сент - Люсия	Кастри
Сербия	Белград
Сингапур	Сингапур
Сирия	Дамаск
Словакия	Братислава
Словения	Любляна
Соединенные Штаты Америки	Вашингтон
Соломоновы Острова	Хониара
Сомали	Могадишо
Судан	Хартум
Суринам	Парамарибо
Сьерра - Леоне	Фритаун
Таджикистан	Душанбе
Таиланд	Бангкок
Танзания	Додома
Того	Ломе
Тонга	Нукуалофа
Тувалу	Фунафути
Тунис	Тунис
Туркмения	Ашхабад
Турция	Анкара
Уганда	Кампала
Узбекистан	Ташкент
Украина	Киев
Уругвай	Монтевидео
Федеративные штаты Микронезии	Паликир
Фиджи	Сува
Филиппины	Манила
Финляндия	Хельсинки
Франция	Париж
Хорватия	Загреб
Центрально - Африканская Республика	Банги
Чад	Нджамена
Черногория	Подгорица
Чехия	Прага
Чили	Сантьяго
Швейцария	Берн
Швеция	Стокгольм
Шри - Ланка	Коломбо
Эквадор	Кито
Экваториальная Гвинея	Малабо
Эритрея	Асмэра
Эстония	Таллин
Эфиопия	Аддис - Абеба
Южная Корея	Сеул
Ямайка	Кингстон
Япония	Токио'''
dict_1 = []
dict_2 = []
for line in d.splitlines():
    lst = line.split('\t')
    name = lst[0]
    surname = lst[1]
    dict_1.append([name, surname])
    dict_2.append([surname, name])
c = 0
b = 0
k = 0

db = sqlite3.connect('server.db', check_same_thread=False)
sql = db.cursor()
sql.execute('''CREATE TABLE IF NOT EXISTS database(
    id TEXT,
    answer TEXT)''')
replying = 0


def randomizer():
    b = random.randint(0, 1)
    c = random.randint(0, 193)
    if b == 0:
        return dict_1[c][0], 'capital', dict_1[c][1]
    else:
        return dict_2[c][0], 'country', dict_2[c][1]


@bot.message_handler(content_types=['text'])
def get_text_messages(message):
    global k
    global replying
    mes = message.from_user.id
    if message.text == "Привет" or message.text == "Здраствуй!":
        bot.send_message(mes, "Привет, это угадайка! Проверь свои силы!")
    elif message.text == "/startgame" or replying == 1:
        place = randomizer()
        if place[1] == 'capital':
            final1 = str(place[0])
            final1 = final1.split()
            if len(final1) != 1:
                final = ''
                for elem in final1:
                    final = final + ' ' + morph.parse(elem)[0].inflect({'gent'}).word.capitalize()
            else:
                final = morph.parse(final1[0])[0].inflect({'gent'}).word.capitalize()

            if type(final) != str:
                final = place[0]
            bot.send_message(message.from_user.id, f"Назови мне столицу {final}")
            sql.execute(f"SELECT id FROM database WHERE id = '{mes}'")
            if sql.fetchone() is None:
                sql.execute(f"INSERT INTO database VALUES(?, ?)", (mes, place[2]))
                db.commit()
                print('completed')
            else:
                sql.execute(f'DELETE FROM database WHERE id = "{mes}"')
                db.commit()
                sql.execute(f"INSERT INTO database VALUES(?, ?)", (mes, place[2]))
                db.commit()
                print('ez')
            db.commit()
        else:
            bot.send_message(message.from_user.id, f"Назови мне страну, столицей которой является город: {place[0]}")
            sql.execute(f"SELECT id FROM database WHERE id = '{mes}'")
            if sql.fetchone() is None:
                sql.execute(f"INSERT INTO database VALUES(?, ?)", (mes, place[2]))
                db.commit()
                print('completed')
            else:
                sql.execute(f'DELETE FROM database WHERE id = "{mes}"')
                db.commit()
                sql.execute(f"INSERT INTO database VALUES(?, ?)", (mes, place[2]))
                db.commit()
                print('ez')
        bot.register_next_step_handler(message, guess)
    elif message.text == '/start':
        bot.send_message(message.from_user.id, "Привет! Это бот угадайка!")
    elif message.text.lower() == '/stopgame':
        k = 0
        replying = 0
        bot.send_message(message.from_user.id, "Хорошо! Обязательно поробуй еще!")
    elif message.text == "/help":
        bot.send_message(message.from_user.id, "Напиши 'Привет' или 'Здраствуй!, или '/startgame'")
    else:
        bot.send_message(message.from_user.id, "Я тебя не понимаю. Напиши /help.")


def guess(message):
    global k
    global replying
    mes = message.from_user.id
    sql.execute(f"SELECT answer FROM database WHERE id = '{mes}'")
    a = sql.fetchall()[0][0]
    db.commit()
    if a == message.text.capitalize():
        k += 1
        bot.send_message(message.from_user.id, f"Молодец! Твой стрик - {k}.")
        replying = 1
        get_text_messages(message)
    elif message.text.lower() == '/stopgame':
        bot.send_message(message.from_user.id, "Хорошо! Обязательно поробуй еще! Твой стрик был - k")
        k = 0
        replying = 0
    else:
        k = 0
        replying = 0
        bot.send_message(message.from_user.id, f"Ты не прав! Ответом был: {a}. Чтобы начать игру заново, напиши "
                                               f"'/startgame'")
        bot.register_next_step_handler(message, get_text_messages)


while True:
    try:
        bot.polling(none_stop=True)

    except Exception as e:
        print(e)
        time.sleep(15)
