- 👋 Hi, I’m @kirfill
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
kirfill/kirfill is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
.:
import telebot
from telebot import types
bot = telebot.TeleBot('5780965558:AAGqFx4BfKaL4Uh7GEhNfg13rZ1_6q9PnbE')

@bot.message_handler(commands=['start'])
def button(message):
    global coin
    coin = 0

    markup = types.InlineKeyboardMarkup(row_width=1)
    start = types.InlineKeyboardButton('Готов', callback_data='start.gotov')
    markup.add(start)
    bot.send_message(message.chat.id, 'Привет, этот бот подсчтывает насколько ты хорош(а). Если готов(a) жми на кнопку.💋', reply_markup=markup)


@bot.callback_query_handler(func=lambda call:call.data.startswith('start.'))
def callback(call):
    if call.data == 'start.gotov':
        global coin
        markup = types.InlineKeyboardMarkup(row_width=2)
        one_1 = types.InlineKeyboardButton('4😈', callback_data='one.one_1')
        one_2 = types.InlineKeyboardButton('3😳', callback_data='one.one_2')
        markup.add(one_1, one_2)

        bot.edit_message_text(chat_id=call.message.chat.id, message_id=call.message.id, reply_markup=markup,
                                  text='Вопрос_1: 2+2:')

@bot.callback_query_handler(func=lambda call:call.data.startswith('one.'))
def callback2(call):

    if call.data == 'one.one_1':
        global coin
        coin = coin+1

        markup = types.InlineKeyboardMarkup(row_width=2)
        two_1 = types.InlineKeyboardButton('10😳', callback_data='two.two_1')
        two_2 = types.InlineKeyboardButton('9😈', callback_data='two.two_2')
        markup.add(two_1, two_2)

        bot.edit_message_text(chat_id=call.message.chat.id, message_id=call.message.id, reply_markup=markup,
                                  text='Вопрос_2: 5+5')

    else:
        markup = types.InlineKeyboardMarkup(row_width=2)
        two_1 = types.InlineKeyboardButton('10😳', callback_data='two.two_1')
        two_2 = types.InlineKeyboardButton('9😈', callback_data='two.two_2')
        markup.add(two_1, two_2)

        bot.edit_message_text(chat_id=call.message.chat.id, message_id=call.message.id, reply_markup=markup,
                                  text='Вопрос_2: 5+5')


@bot.callback_query_handler(func=lambda call:call.data.startswith('two.'))
def callback2(call):

    if call.data == 'two.two_1':
        global coin
        coin = coin+1

        markup = types.InlineKeyboardMarkup(row_width=2)
        three_1 = types.InlineKeyboardButton('10😳', callback_data='three.three_1')
        three_2 = types.InlineKeyboardButton('15😈', callback_data='three.three_2')
        markup.add(three_1, three_2)

        bot.edit_message_text(chat_id=call.message.chat.id, message_id=call.message.id, reply_markup=markup,
                                  text='Вопрос_3: 5+10')

    else:
        markup = types.InlineKeyboardMarkup(row_width=2)
        three_1 = types.InlineKeyboardButton('10😳', callback_data='three.three_1')
        three_2 = types.InlineKeyboardButton('15😈', callback_data='three.three_2')
        markup.add(three_1, three_2)

        bot.edit_message_text(chat_id=call.message.chat.id, message_id=call.message.id, reply_markup=markup,
                                  text='Вопрос_3: 5+10')



@bot.callback_query_handler(func=lambda call:call.data.startswith('three.'))
def callback2(call):

    if call.data == 'three.three_1':



        markup = types.InlineKeyboardMarkup(row_width=2)
        four_1 = types.InlineKeyboardButton('8😳', callback_data='four.four_1')
        four_2 = types.InlineKeyboardButton('1😈', callback_data='four.four_2')
        markup.add(four_1, four_2)

        bot.edit_message_text(chat_id=call.message.chat.id, message_id=call.message.id, reply_markup=markup,
                                  text='Вопрос_4: 4+4')

    else:
        global coin
        coin = coin + 1
        markup = types.InlineKeyboardMarkup(row_width=2)
        four_1 = types.InlineKeyboardButton('8😳', callback_data='four.four_1')
        four_2 = types.InlineKeyboardButton('1😈', callback_data='four.four_2')
        markup.add(four_1, four_2)

bot.edit_message_text(chat_id=call.message.chat.id, message_id=call.message.id, reply_markup=markup,
                                  text='Вопрос_4: 4+4')




@bot.callback_query_handler(func=lambda call:call.data.startswith('four.'))
def callback2(call):

    if call.data == 'four.four_1':
        global coin
        coin = coin + 1


        markup = types.InlineKeyboardMarkup(row_width=2)
        five_1 = types.InlineKeyboardButton('691😳', callback_data='five.five_1')
        five_2 = types.InlineKeyboardButton('682😈', callback_data='five.five_2')
        markup.add(five_1, five_2)

        bot.edit_message_text(chat_id=call.message.chat.id, message_id=call.message.id, reply_markup=markup,
                                  text='Вопрос_5: 234+457')

    else:

        markup = types.InlineKeyboardMarkup(row_width=2)
        five_1 = types.InlineKeyboardButton('681😳', callback_data='five.five_1')
        five_2 = types.InlineKeyboardButton('682😈', callback_data='five.five_2')
        markup.add(five_1, five_2)

        bot.edit_message_text(chat_id=call.message.chat.id, message_id=call.message.id, reply_markup=markup,
                                  text='Вопрос_5: 234+457')

@bot.callback_query_handler(func=lambda call:call.data.startswith('five.'))
def callback2(call):

    if call.data == 'five.five_1':
        global coin
        coin = coin + 1
        bot.edit_message_text(chat_id=call.message.chat.id, message_id=call.message.id,
                              text='Счёт: '+ str(coin))

    if call.data == 'five.five_2':

        bot.edit_message_text(chat_id=call.message.chat.id, message_id=call.message.id,
                              text='О нормально твой счёт: '+ str(coin))


bot.polling()
