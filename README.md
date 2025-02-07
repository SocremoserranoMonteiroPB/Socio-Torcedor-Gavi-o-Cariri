import { useState } from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";
import { Tabs, TabsList, TabsTrigger, TabsContent } from "@/components/ui/tabs";
import { FaTicketAlt, FaNewspaper, FaUser, FaCamera } from "react-icons/fa";

export default function SocremoSerrano() {
  const [email, setEmail] = useState("");

  return (
    <div className="p-6 bg-gray-100 min-h-screen">
      <header className="text-center mb-6">
        <h1 className="text-4xl font-bold text-green-700">Sócio Torcedor - Socremo Serrano</h1>
        <p className="text-gray-600">Seja parte da nossa história!</p>
      </header>

      <Tabs defaultValue="planos" className="w-full max-w-3xl mx-auto">
        <TabsList className="flex justify-between bg-green-700 p-2 rounded-xl">
          <TabsTrigger value="planos" className="text-white flex items-center gap-2">
            <FaUser /> Planos
          </TabsTrigger>
          <TabsTrigger value="noticias" className="text-white flex items-center gap-2">
            <FaNewspaper /> Notícias
          </TabsTrigger>
          <TabsTrigger value="fotos" className="text-white flex items-center gap-2">
            <FaCamera /> Fotos
          </TabsTrigger>
          <TabsTrigger value="ingressos" className="text-white flex items-center gap-2">
            <FaTicketAlt /> Ingressos
          </TabsTrigger>
        </TabsList>

        <TabsContent value="planos">
          <Card className="mt-4">
            <CardContent>
              <h2 className="text-2xl font-semibold">Escolha seu plano</h2>
              <p className="text-gray-600">Apoie o Socremo-Serrano e tenha benefícios exclusivos!</p>
              <div className="grid grid-cols-1 md-grid-cols-3 gap-4 mt-4">
                <div className="p-4 bg-white rounded-lg shadow">
                  <h3 className="font-bold text-lg">Plano Bronze</h3>
                  <p>R$ 14,99/mês</p>
                  <Button className="mt-2">Assinar</Button>
                </div>
                <div className="p-4 bg-white rounded-lg shadow">
                  <h3 className="font-bold text-lg">Plano Prata</h3>
                  <p>R$ 29,99/mês</p>
                  <Button className="mt-2">Assinar</Button>
                </div>
                <div className="p-4 bg-white rounded-lg shadow">
                  <h3 className="font-bold text-lg">Plano Ouro</h3>
                  <p>R$ 44,99/mês</p>
                  <Button className="mt-2">Assinar</Button>
                </div>
              </div>
            </CardContent>
          </Card>
        </TabsContent>

        <TabsContent value="noticias">
          <Card className="mt-4">
            <CardContent>
              <h2 className="text-2xl font-semibold">Últimas Notícias</h2>
              <p className="text-gray-600">Fique por dentro das novidades do Socremo-Serrano!</p>
            </CardContent>
          </Card>
        </TabsContent>

        <TabsContent value="fotos">
          <Card className="mt-4">
            <CardContent>
              <h2 className="text-2xl font-semibold">Galeria de Fotos</h2>
              <p className="text-gray-600">Confira os melhores momentos do nosso time!</p>
            </CardContent>
          </Card>
        </TabsContent>

        <TabsContent value="ingressos">
          <Card className="mt-4">
            <CardContent>
              <h2 className="text-2xl font-semibold">Compra de Ingressos</h2>
              <p className="text-gray-600">Garanta seu lugar no estádio!</p>
              <Input
                className="mt-4"
                type="email"
                placeholder="Digite seu e-mail para receber informações"
                value={email}
                onChange={(e) => setEmail(e.target.value)}
              />
              <Button className="mt-2">Comprar Ingressos</Button>
            </CardContent>
          </Card>
        </TabsContent>
      </Tabs>
    </div>
  );
}


