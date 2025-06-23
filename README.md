import React, { useState } from "react"; import { Card, CardContent } from "@/components/ui/card"; import { Button } from "@/components/ui/button"; import { Input } from "@/components/ui/input";

export default function StandoffTournament() { const [submitted, setSubmitted] = useState(false);

const handleSubmit = (e) => { e.preventDefault(); setSubmitted(true); };

return ( <div className="min-h-screen bg-gradient-to-br from-gray-900 to-gray-800 text-white p-6"> <header className="text-center mb-10"> <h1 className="text-5xl font-bold text-yellow-400 mb-2">Standoff Tournament</h1> <p className="text-lg text-gray-300">Соревнование лучших игроков в Standoff 2</p> </header>

<main className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
    <Card className="bg-gray-700 text-white shadow-xl rounded-2xl">
      <CardContent className="p-6">
        <h2 className="text-2xl font-semibold mb-2">Регистрация</h2>
        <p className="text-sm mb-4">
          Участие в турнире стоит <span className="font-bold text-yellow-400">10 евро</span>. Переведи сумму на один из указанных счетов и заполни форму ниже.
        </p>
        <div className="bg-gray-800 p-4 rounded-xl mb-4">
          <h3 className="font-semibold text-lg mb-2">Платёжные данные</h3>
          <p className="text-sm">💳 <strong>Банковская карта:</strong><br/>5205 8123 0322 8514<br/>EDUARDS ĻEONOVS</p>
          <p className="text-sm mt-2">💰 <strong>Криптовалюта (Tether USDT, TRC20):</strong><br/>TJSbUFN7dVavssLsWRVffFnxoE44n9UpHP</p>
        </div>
        {submitted ? (
          <p className="text-green-400 font-semibold">Заявка отправлена! Ожидайте подтверждение на edikleonov844@gmail.com</p>
        ) : (
          <form className="space-y-3" onSubmit={handleSubmit}>
            <Input placeholder="Имя команды" className="bg-gray-800 text-white" required />
            <Input placeholder="Капитан (никнейм)" className="bg-gray-800 text-white" required />
            <Input placeholder="Контакт (Telegram или Discord)" className="bg-gray-800 text-white" required />
            <Input placeholder="ID платежа или скрин перевода" className="bg-gray-800 text-white" required />
            <Button type="submit" className="bg-yellow-500 hover:bg-yellow-600 w-full">Отправить заявку</Button>
          </form>
        )}
      </CardContent>
    </Card>

    <Card className="bg-gray-700 text-white shadow-xl rounded-2xl">
      <CardContent className="p-6">
        <h2 className="text-2xl font-semibold mb-2">Призовой фонд</h2>
        <p className="text-sm">
          Общий приз — <span className="font-bold text-yellow-400">300 евро</span>. Победитель турнира получит весь призовой фонд.
        </p>
      </CardContent>
    </Card>

    <Card className="bg-gray-700 text-white shadow-xl rounded-2xl">
      <CardContent className="p-6">
        <h2 className="text-2xl font-semibold mb-2">Информация</h2>
        <p className="text-sm">
          Турнир пройдет онлайн на платформе Standoff 2. Участие платное — 10 евро. Формат — 5x5. Начало: 15 июля 2025 года.
        </p>
        <div className="mt-4">
          <a
            href="https://t.me/sdanioppp2"
            target="_blank"
            rel="noopener noreferrer"
            className="inline-block bg-blue-600 hover:bg-blue-700 text-white text-sm font-semibold px-4 py-2 rounded-xl shadow"
          >
            Присоединиться к Telegram-группе
          </a>
        </div>
      </CardContent>
    </Card>
  </main>

  <footer className="mt-16 text-center text-gray-400 text-sm">
    © 2025 Standoff Tournament. Все права защищены.
  </footer>
</div>

); }

