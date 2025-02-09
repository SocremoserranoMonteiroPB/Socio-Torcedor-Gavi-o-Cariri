import React, { useState } from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";
import { Select, SelectItem } from "@/components/ui/select";

export default function SocremoSerranoSite() {
  const [name, setName] = useState("");
  const [email, setEmail] = useState("");
  const [plan, setPlan] = useState("");
  const [payment, setPayment] = useState("");
  const [step, setStep] = useState(1);

  const handleNextStep = () => setStep(2);
  const handleSubmit = (e) => {
    e.preventDefault();
    alert(`Cadastro realizado! Nome: ${name}, Email: ${email}, Plano: ${plan}, Pagamento: ${payment}`);
  };

  return (
    <div className="p-6 max-w-lg mx-auto relative" style={{
      backgroundImage: "url('/logo.png')",
      backgroundSize: "cover",
      backgroundPosition: "center",
      backgroundRepeat: "no-repeat",
      opacity: 0.2
    }}>
      <div className="absolute inset-0 bg-white bg-opacity-80 p-6 rounded-lg">
        <h1 className="text-3xl font-bold mb-4 text-center">Sócio Torcedor - Socremo Serrano</h1>
        <p className="mb-4 text-center">Escolha seu plano e faça parte do nosso time!</p>

        {step === 1 && (
          <div className="space-y-4">
            <h2 className="text-2xl font-bold">Escolha seu Plano</h2>
            <Select value={plan} onChange={(e) => setPlan(e.target.value)} required>
              <SelectItem value="Gavião Verde">Gavião Verde</SelectItem>
              <SelectItem value="Carcará Vermelho">Carcará Vermelho</SelectItem>
              <SelectItem value="Elite Serrano Azul">Elite Serrano Azul</SelectItem>
            </Select>
            <h2 className="text-2xl font-bold">Forma de Pagamento</h2>
            <Select value={payment} onChange={(e) => setPayment(e.target.value)} required>
              <SelectItem value="Cartão de Crédito">Cartão de Crédito</SelectItem>
              <SelectItem value="Boleto Bancário">Boleto Bancário</SelectItem>
              <SelectItem value="Pix">Pix</SelectItem>
            </Select>
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
        <Card>
          <CardContent>
            <p>A Socremo-Serrano representa a cidade de Monteiro-PB no futebol profissional, carregando uma história de tradição e retorno ao cenário estadual...</p>
          </CardContent>
        </Card>

        <h2 className="text-2xl font-bold mt-6 mb-4">Notícias</h2>
        <Card>
          <CardContent>
            <p>Em breve, novidades sobre o time!</p>
          </CardContent>
        </Card>
      </div>
    </div>
  );
}


