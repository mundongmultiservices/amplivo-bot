# amplivo-bot
from telegram import Update, InlineKeyboardButton, InlineKeyboardMarkup
from telegram.ext import ApplicationBuilder, CommandHandler, ContextTypes
import os

TOKEN = os.getenv("BOT_TOKEN")

async def start(update: Update, context: ContextTypes.DEFAULT_TYPE):
    keyboard = [
        [InlineKeyboardButton("🌍 Juntar-me à Amplivo", url="https://www.amplivo.com/sponsor/mundongmultiservices")],
        [InlineKeyboardButton("📄 Ver Apresentação", url="https://docs.google.com/presentation/d/1Ok3BqVhM-Ir-cD_xeg6_70zBw2FJzW2y")],
        [InlineKeyboardButton("📲 Falar com o Nuno", url="https://t.me/njdg73")]
    ]
    reply_markup = InlineKeyboardMarkup(keyboard)
    
    message = (
        "👋 Olá e bem-vindo ao mundo Amplivo!\n\n"
        "Este bot vai ajudar-te a descobrir uma oportunidade incrível de impacto social e financeiro.\n\n"
        "💎 A Amplivo é mais do que um projeto: é um movimento global pela sustentabilidade e geração de rendimento digital.\n\n"
        "Escolhe uma opção abaixo para começares:"
    )
    python-telegram-bot==20.7

    await update.message.reply_text(message, reply_markup=reply_markup)

if __name__ == "__main__":
    app = ApplicationBuilder().token(TOKEN).build()
    app.add_handler(CommandHandler("start", start))
    print("🤖 Bot Amplivo está online!")
    app.run_polling()
