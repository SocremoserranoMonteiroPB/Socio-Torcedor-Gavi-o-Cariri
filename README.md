import React from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";

export default function SocremoSerranoSite() {
  return (
    <div className="p-6 text-center bg-gray-900 text-white min-h-screen relative" style={{ backgroundImage: "url('/logo-socremo.png')", backgroundSize: "cover", backgroundPosition: "center", opacity: 0.9 }}>
      <h1 className="text-4xl font-bold mb-6">Sócio Torcedor - Socremo Serrano</h1>
      
      <section className="mb-8">
        <h2 className="text-3xl font-bold mb-2">História do Clube</h2>
        <p className="max-w-2xl mx-auto text-lg">
          A Socremo-Serrano representa a cidade de Monteiro-PB no futebol profissional, carregando uma história de tradição e retorno ao cenário estadual. O clube nasceu da parceria entre o Grêmio Recreativo Serrano-PB e a Sociedade Recreativa Monteirense (Socremo). Após 24 anos, a Socremo-Serrano retornou ao futebol profissional em 2024, disputando a 3ª divisão do Campeonato Paraibano.
        </p>
      </section>
      
      <section className="mb-8">
        <h2 className="text-3xl font-bold mb-2">Planos de Sócio-Torcedor</h2>
        <div className="flex flex-wrap justify-center gap-4">
          <Card className="p-4 bg-gray-800">
            <CardContent>
              <h3 className="text-xl font-bold">Gavião Verde</h3>
              <p>R$ 15,00 - 15% de desconto nos ingressos e sorteio de brindes.</p>
              <Button className="mt-2 bg-green-600" onClick={() => window.open('https://pag.ae/7_mvni32L')}>Assinar</Button>
            </CardContent>
          </Card>
          <Card className="p-4 bg-gray-800">
            <CardContent>
              <h3 className="text-xl font-bold">Carcará Vermelho</h3>
              <p>R$ 30,00 - 30% de desconto nos ingressos e sorteio de brindes.</p>
              <Button className="mt-2 bg-red-600" onClick={() => window.open('https://pag.ae/7_mvwab4s')}>Assinar</Button>
            </CardContent>
          </Card>
          <Card className="p-4 bg-gray-800">
            <CardContent>
              <h3 className="text-xl font-bold">Elite Serrano Azul</h3>
              <p>R$ 45,00 - 50% de desconto nos ingressos e sorteio de brindes.</p>
              <Button className="mt-2 bg-blue-600" onClick={() => window.open('https://pag.ae/7_mvwDpup')}>Assinar</Button>
            </CardContent>
          </Card>
        </div>
      </section>
      
      <section className="mb-8">
        <h2 className="text-3xl font-bold mb-2">Ingressos</h2>
        <p className="text-lg">Garanta seu ingresso para os próximos jogos da Socremo-Serrano e apoie nosso time!</p>
        <Button className="mt-4 bg-yellow-500" onClick={() => alert('Em breve disponível!')}>Comprar Ingressos</Button>
      </section>
    </div>
  );
}
