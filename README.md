import React, { useState } from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";
import { Select, SelectItem } from "@/components/ui/select";

export default function SocremoSerranoSite() {
  const [name, setName] = useState("");
  const [email, setEmail] = useState("");
  const [plan, setPlan] = useState("Gavião Verde");

  const handleSubmit = (e) => {
    e.preventDefault();
    alert(`Cadastro realizado! Nome: ${name}, Email: ${email}, Plano: ${plan}`);
  };

  return (
    <div className="p-6">
      <h1 className="text-3xl font-bold mb-4">Sócio Torcedor - Socremo Serrano</h1>
      <p className="mb-4">Seja um sócio e apoie nosso time! Escolha seu plano abaixo.</p>
      
      <form onSubmit={handleSubmit} className="mb-6 space-y-4">
        <Input placeholder="Nome Completo" value={name} onChange={(e) => setName(e.target.value)} required />
        <Input placeholder="Email" type="email" value={email} onChange={(e) => setEmail(e.target.value)} required />
        <Select value={plan} onChange={(e) => setPlan(e.target.value)}>
          <SelectItem value="Gavião Verde">Gavião Verde</SelectItem>
          <SelectItem value="Carcará Vermelho">Carcará Vermelho</SelectItem>
          <SelectItem value="Elite Serrano Azul">Elite Serrano Azul</SelectItem>
        </Select>
        <Button type="submit">Finalizar Cadastro</Button>
      </form>

      <h2 className="text-2xl font-bold mt-6 mb-4">Notícias</h2>
      <Card>
        <CardContent>
          <p>Em breve, novidades sobre o time!</p>
        </CardContent>
      </Card>
    </div>
  );
}

