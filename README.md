import React, { useState } from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";

export default function SocremoSerranoSite() {
  const [name, setName] = useState("");
  const [email, setEmail] = useState("");
  const [plan, setPlan] = useState("");
  const [payment, setPayment] = useState("");
  const [step, setStep] = useState(1);

  const handleNextStep = () => {
    if (plan && payment) {
      setStep(2);
    } else {
      alert("Por favor, selecione um plano e uma forma de pagamento.");
    }
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    alert(`Cadastro realizado! Nome: ${name}, Email: ${email}, Plano: ${plan}, Pagamento: ${payment}`);
  };

  return (
    <div className="p-6 max-w-lg mx-auto bg-white shadow-lg rounded-lg">
      <h1 className="text-3xl font-bold mb-4 text-center text-blue-600">Sócio Torcedor - Socremo Serrano</h1>
      <p className="mb-4 text-center text-gray-600">Escolha seu plano e faça parte do nosso time!</p>

      {step === 1 && (
        <div className="space-y-4">
          <h2 className="text-2xl font-bold text-gray-700">Escolha seu Plano</h2>
          <select
            value={plan}
            onChange={(e) => setPlan(e.target.value)}
            className="w-full p-2 border rounded-lg"
            required
          >
            <option value="">Selecione um plano</option>
            <option value="Gavião Verde">Gavião Verde</option>
            <option value="Carcará Vermelho">Carcará Vermelho</option>
            <option value="Elite Serrano Azul">Elite Serrano Azul</option>
          </select>

          <h2 className="text-2xl font-bold text-gray-700">Forma de Pagamento</h2>
          <select
            value={payment}
            onChange={(e) => setPayment(e.target.value)}
            className="w-full p-2 border rounded-lg"
            required
          >
            <option value="">Selecione um método</option>
            <option value="Cartão de Crédito">Cartão de Crédito</option>
            <option value="Boleto Bancário">Boleto Bancário</option>
            <option value="Pix">Pix</option>
          </select>

          <Button onClick={handleNextStep} className="w-full bg-green-600 text-white">Avançar</Button>
        </div>
      )}

      {step === 2 && (
        <form onSubmit={handleSubmit} className="space-y-4">
          <h2 className="text-2xl font-bold text-gray-700">Cadastro</h2>
          <Input placeholder="Nome Completo" value={name} onChange={(e) => setName(e.target.value)} required />
          <Input placeholder="Email" type="email" value={email} onChange={(e) => setEmail(e.target.value)} required />
          <Button type="submit" className="w-full bg-blue-600 text-white">Finalizar Cadastro</Button>
        </form>
      )}

      <h2 className="text-2xl font-bold mt-6 mb-4 text-gray-700">Notícias</h2>
      <Card>
        <CardContent>
          <p className="text-gray-600">Em breve, novidades sobre o time!</p>
        </CardContent>
      </Card>
    </div>
  );
}

