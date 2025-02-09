
import React, { useState } from "react";
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";

export default function SocremoSerranoSite() {
  const [name, setName] = useState("");
  const [email, setEmail] = useState("");
  const [plan, setPlan] = useState("");
  const [step, setStep] = useState(1);

  const handleNextStep = () => setStep(2);
  const handleSubmit = (e) => {
    e.preventDefault();
    alert(`Cadastro realizado! Nome: ${name}, Email: ${email}, Plano: ${plan}`);
  };

  return (
    <div className="p-6 max-w-lg mx-auto text-center">
      <h1 className="text-3xl font-bold mb-4">Sócio Torcedor - Socremo Serrano</h1>
      <p className="mb-4">Escolha seu plano e faça parte do nosso time!</p>

      {step === 1 && (
        <div className="space-y-4">
          <h2 className="text-2xl font-bold">Escolha seu Plano</h2>
          <select value={plan} onChange={(e) => setPlan(e.target.value)} className="w-full p-2 border">
            <option value="">Selecione</option>
            <option value="Gavião Verde">Gavião Verde</option>
            <option value="Carcará Vermelho">Carcará Vermelho</option>
            <option value="Elite Serrano Azul">Elite Serrano Azul</option>
          </select>
          <Button onClick={handleNextStep}>Avançar</Button>
        </div>
      )}

      {step === 2 && (
        <form onSubmit={handleSubmit} className="space-y-4">
          <h2 className="text-2xl font-bold">Cadastro</h2>
          <Input placeholder="Nome Completo" value={name} onChange={(e) => setName(e.target.value)} required />
          <Input placeholder="Email" type="email" value={email} onChange={(e) => setEmail(e.target.value)} required />
          <Button type="submit">Finalizar Cadastro</Button>
        </form>
      )}

      <h2 className="text-2xl font-bold mt-6 mb-4">História do Clube</h2>
      <p className="text-left text-sm">
        A Socremo-Serrano representa a cidade de Monteiro-PB no futebol profissional, carregando uma história de tradição.
        Fundada pela união do Serrano-PB e da Socremo, marcou o retorno do futebol profissional em 2024. O time disputa a
        2ª divisão masculina, o campeonato feminino e as categorias de base (Sub-15, Sub-17 e Sub-20).
      </p>

      <h2 className="text-2xl font-bold mt-6 mb-4">Ingressos</h2>
      <p className="text-left text-sm">Compre seu ingresso para os próximos jogos:</p>
      <a href="https://pag.ae/7_mvni32L" className="block text-blue-500">Compra de Ingressos</a>

      <h2 className="text-2xl font-bold mt-6 mb-4">Seja Sócio Torcedor</h2>
      <p className="text-left text-sm">Escolha um plano e apoie o time!</p>
      <a href="https://pag.ae/7_mvwab4s" className="block text-blue-500">Planos de Sócio Torcedor</a>
    </div>
  );
}



