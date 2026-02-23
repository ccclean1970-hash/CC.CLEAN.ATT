import React, { useState } from 'react';
import { 
  Menu, 
  X, 
  Droplets, 
  ShieldCheck, 
  Car, 
  Wind, 
  CheckCircle2, 
  Instagram, 
  Facebook,
  Phone
} from 'lucide-react';

export default function App() {
  const [isMenuOpen, setIsMenuOpen] = useState(false);

  const services = [
    {
      title: "Remoção de Manchas",
      desc: "Tratamento especializado para manchas difíceis em diversos tecidos.",
      icon: <Droplets className="w-8 h-8 text-blue-600" />
    },
    {
      title: "Sofás & Poltronas",
      desc: "Higienização profunda que remove sujidade e devolve o aspeto de novo.",
      icon: <CheckCircle2 className="w-8 h-8 text-blue-600" />
    },
    {
      title: "Colchões",
      desc: "Eliminação total de ácaros e bactérias para um sono mais saudável.",
      icon: <ShieldCheck className="w-8 h-8 text-blue-600" />
    },
    {
      title: "Setor Automotivo",
      desc: "Limpeza detalhada de bancos e estofados do seu veículo.",
      icon: <Car className="w-8 h-8 text-blue-600" />
    }
  ];

  const whatsappLink = "https://wa.me/5500000000000"; // Substitua pelo seu número

  return (
    <div className="min-h-screen bg-slate-50 font-sans text-slate-900">
      {/* Navigation */}
      <nav className="fixed w-full z-50 bg-white/90 backdrop-blur-md border-b border-slate-200">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="flex justify-between h-20 items-center">
            
            {/* LOGO ATUALIZADO AQUI */}
            <div className="flex items-center">
              <img 
                src="/logo.png" 
                alt="CC Clean Higienizações" 
                className="h-16 w-auto object-contain" 
              />
            </div>
            
            {/* Desktop Menu */}
            <div className="hidden md:flex items-center space-x-8">
              <a href="#inicio" className="text-sm font-semibold hover:text-blue-600 transition">Início</a>
              <a href="#servicos" className="text-sm font-semibold hover:text-blue-600 transition">Serviços</a>
              <a href="#tecnologia" className="text-sm font-semibold hover:text-blue-600 transition">Tecnologia</a>
              <a 
                href={whatsappLink}
                className="bg-blue-600 text-white px-6 py-2.5 rounded-full text-sm font-bold hover:bg-blue-700 transition shadow-lg shadow-blue-200"
              >
                Orçamento Grátis
              </a>
            </div>

            {/* Mobile Toggle */}
            <div className="md:hidden">
              <button onClick={() => setIsMenuOpen(!isMenuOpen)} className="p-2 text-slate-600">
                {isMenuOpen ? <X /> : <Menu />}
              </button>
            </div>
          </div>
        </div>

        {/* Mobile Menu */}
        {isMenuOpen && (
          <div className="md:hidden bg-white border-b border-slate-200 p-4 space-y-4 shadow-xl">
            <a href="#inicio" onClick={() => setIsMenuOpen(false)} className="block text-lg font-medium">Início</a>
            <a href="#servicos" onClick={() => setIsMenuOpen(false)} className="block text-lg font-medium">Serviços</a>
            <a href={whatsappLink} className="block w-full text-center bg-blue-600 text-white py-3 rounded-xl font-bold">WhatsApp</a>
          </div>
        )}
      </nav>

      {/* Hero Section */}
      <section id="inicio" className="pt-32 pb-20 lg:pt-48 lg:pb-32 px-4 bg-gradient-to-br from-slate-900 via-blue-900 to-blue-800 text-white overflow-hidden relative">
        <div className="absolute top-0 right-0 w-1/3 h-full bg-blue-500/10 blur-3xl rounded-full -mr-20 -mt-20"></div>
        <div className="max-w-7xl mx-auto relative z-10">
          <div className="flex flex-col lg:flex-row items-center gap-12">
            <div className="lg:w-3/5 text-center lg:text-left">
              <div className="inline-flex items-center gap-2 bg-blue-500/20 border border-blue-400/30 px-4 py-2 rounded-full text-blue-200 text-sm font-bold mb-6">
                <span className="relative flex h-2 w-2">
                  <span className="animate-ping absolute inline-flex h-full w-full rounded-full bg-blue-400 opacity-75"></span>
                  <span className="relative inline-flex rounded-full h-2 w-2 bg-blue-500"></span>
                </span>
                Especialistas em Limpeza Profissional
              </div>
              <h1 className="text-4xl md:text-6xl lg:text-7xl font-extrabold leading-[1.1] mb-6">
                Dê uma vida nova aos seus <span className="text-blue-400">estofados.</span>
              </h1>
              <p className="text-lg md:text-xl text-blue-100/80 mb-10 max-w-2xl mx-auto lg:mx-0">
                Higienização profunda, impermeabilização e esterilização com Ozônio. 
                Sua casa mais limpa e livre de ácaros e bactérias.
              </p>
              <div className="flex flex-col sm:flex-row gap-4 justify-center lg:justify-start">
                <a 
                  href={whatsappLink}
                  className="bg-green-500 hover:bg-green-600 text-white px-8 py-4 rounded-2xl font-bold text-lg transition flex items-center justify-center gap-3 shadow-xl shadow-green-900/20"
                >
                  <Phone className="w-5 h-5" /> Falar com Especialista
                </a>
                <a 
                  href="#servicos"
                  className="bg-white/10 hover:bg-white/20 backdrop-blur-sm text-white px-8 py-4 rounded-2xl font-bold text-lg transition border border-white/20"
                >
                  Ver Serviços
                </a>
              </div>
            </div>
            <div className="lg:w-2/5 flex justify-center">
              <div className="relative">
                <div className="w-64 h-64 md:w-80 md:h-80 bg-blue-600 rounded-3xl rotate-6 absolute inset-0 opacity-20"></div>
                <div className="w-64 h-64 md:w-80 md:h-80 bg-white/10 backdrop-blur-md rounded-3xl border border-white/2
