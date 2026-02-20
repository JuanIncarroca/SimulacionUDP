import React, { useState, useEffect } from 'react';
import { Monitor, Server, Play, RotateCcw } from 'lucide-react';

const App = () => {
  const [visiblePackets, setVisiblePackets] = useState([]);
  const [isPlaying, setIsPlaying] = useState(false);

  // Datos extraídos y procesados del archivo PCAP proporcionado
  const packets = [
    {
      id: 1,
      from: 'client1',
      to: 'server',
      ipOrig: '192.168.0.2',
      ipDest: '192.168.0.1',
      portOrig: '49152',
      portDest: '5000',
      message: '6',
      type: 'request'
    },
    {
      id: 2,
      from: 'server',
      to: 'client1',
      ipOrig: '192.168.0.1',
      ipDest: '192.168.0.2',
      portOrig: '5000',
      portDest: '49152',
      message: 'El numero 6 es PERFECTO',
      type: 'response',
      isPerfect: true
    },
    {
      id: 3,
      from: 'client2',
      to: 'server',
      ipOrig: '192.168.0.3',
      ipDest: '192.168.0.1',
      portOrig: '51234',
      portDest: '5000',
      message: '0',
      type: 'request'
    },
    {
      id: 4,
      from: 'server',
      to: 'client2',
      ipOrig: '192.168.0.1',
      ipDest: '192.168.0.3',
      portOrig: '5000',
      portDest: '51234',
      message: 'El numero 0 NO es perfecto',
      type: 'response',
      isPerfect: false
    }
  ];

  useEffect(() => {
    let interval;
    if (isPlaying && visiblePackets.length < packets.length) {
      interval = setInterval(() => {
        setVisiblePackets((prev) => [...prev, packets[prev.length]]);
      }, 1500);
    } else {
      setIsPlaying(false);
    }
    return () => clearInterval(interval);
  }, [isPlaying, visiblePackets]);

  const reset = () => {
    setVisiblePackets([]);
    setIsPlaying(false);
  };

  const getXPosition = (node) => {
    if (node === 'client1') return '15%';
    if (node === 'server') return '85%';
    if (node === 'client2') return '50%';
    return '0%';
  };

  return (
    <div className="flex flex-col items-center justify-start min-h-screen bg-gray-50 p-8 font-sans">
      <div className="max-w-4xl w-full bg-white rounded-xl shadow-lg p-6 border border-gray-200 overflow-hidden">
        <div className="flex justify-between items-center mb-10 border-b pb-4">
          <div>
            <h1 className="text-2xl font-bold text-gray-800">Simulador de Intercambio UDP</h1>
            <p className="text-sm text-gray-500 italic">Análisis de segmentos: UDPPERFECTO.pcapng</p>
          </div>
          <div className="flex gap-2">
            <button 
              onClick={() => setIsPlaying(true)}
              disabled={isPlaying || visiblePackets.length === packets.length}
              className="flex items-center gap-2 bg-blue-600 hover:bg-blue-700 text-white px-4 py-2 rounded-lg transition-colors disabled:opacity-50 font-medium"
            >
              <Play size={18} /> Simular
            </button>
            <button 
              onClick={reset}
              className="flex items-center gap-2 bg-gray-100 hover:bg-gray-200 text-gray-700 px-4 py-2 rounded-lg transition-colors font-medium"
            >
              <RotateCcw size={18} /> Reiniciar
            </button>
          </div>
        </div>

        {/* Diagrama de Secuencia */}
        <div className="relative min-h-[700px] w-full border-x border-dashed border-gray-200 pt-32 pb-10">
          
          {/* Lifelines / Cabeceras */}
          <div className="flex justify-between items-start absolute top-4 left-0 w-full px-4 z-30">
            <Node icon={<Monitor size={44} />} label="Cliente 1" ip="192.168.0.2" />
            <Node icon={<Monitor size={44} />} label="Cliente 2" ip="192.168.0.3" />
            <Node icon={<Server size={44} color="#4b5563" />} label="Servidor UDP" ip="192.168.0.1" />
          </div>

          {/* Líneas verticales de vida */}
          <div className="absolute top-8 bottom-0 left-[15%] w-px bg-gray-300"></div>
          <div className="absolute top-8 bottom-0 left-[50%] w-px bg-gray-300"></div>
          <div className="absolute top-8 bottom-0 left-[85%] w-px bg-gray-300"></div>

          {/* Contenedor de Mensajes con margen superior extra para evitar solapamiento */}
          <div className="mt-24 space-y-24 flex flex-col items-center relative z-10">
            {visiblePackets.map((pkt) => (
              <PacketArrow 
                key={pkt.id} 
                packet={pkt} 
                startX={getXPosition(pkt.from)} 
                endX={getXPosition(pkt.to)} 
              />
            ))}
          </div>
        </div>
      </div>

      <div className="mt-6 text-sm text-gray-400">
        Los cuadros de encabezado muestran los datos literales extraídos de las cabeceras IP y UDP del archivo.
      </div>
    </div>
  );
};

const Node = ({ icon, label, ip }) => (
  <div className="flex flex-col items-center w-32 bg-white/80 backdrop-blur-sm p-2 rounded-lg">
    <div className="mb-1 text-gray-600">{icon}</div>
    <div className="font-bold text-gray-800 text-xs sm:text-sm">{ip}</div>
    <div className="text-[10px] text-gray-500 font-mono uppercase tracking-wider">{label}</div>
  </div>
);

const PacketArrow = ({ packet, startX, endX }) => {
  // Calculamos el centro entre el origen y el destino para ubicar la tabla
  const startPos = parseFloat(startX);
  const endPos = parseFloat(endX);
  const midPos = (startPos + endPos) / 2;
  
  return (
    <div className="w-full relative py-4 group animate-fade-in">
      {/* Tabla de Cabecera (Estilo solicitado) */}
      <div 
        className="absolute -top-16 bg-white border border-gray-400 text-[10px] z-20 shadow-md transition-all duration-300 hover:scale-105"
        style={{ 
          width: '160px', 
          left: ${midPos}%, 
          transform: 'translateX(-50%)' 
        }}
      >
        <div className="grid grid-cols-2 border-b border-gray-400 bg-gray-100 font-bold text-gray-700">
          <div className="p-1 border-r border-gray-400 text-center">IP dest</div>
          <div className="p-1 text-center">IP orig</div>
        </div>
        <div className="grid grid-cols-2 border-b border-gray-400">
          <div className="p-1 border-r border-gray-400 text-center truncate">{packet.ipDest}</div>
          <div className="p-1 text-center truncate">{packet.ipOrig}</div>
        </div>
        <div className="grid grid-cols-2 border-b border-gray-400 bg-gray-100 font-bold text-gray-700">
          <div className="p-1 border-r border-gray-400 text-center">Pto dest</div>
          <div className="p-1 text-center">Pto orig</div>
        </div>
        <div className="grid grid-cols-2 border-b border-gray-400">
          <div className="p-1 border-r border-gray-400 text-center">{packet.portDest}</div>
          <div className="p-1 text-center">{packet.portOrig}</div>
        </div>
        <div className="p-1 text-center font-bold text-red-600 bg-white min-h-[1.5rem] flex items-center justify-center">
          {packet.message}
        </div>
      </div>

      {/* La flecha */}
      <svg className="w-full h-10 overflow-visible">
        <defs>
          <marker
            id={arrowhead-${packet.id}}
            markerWidth="10"
            markerHeight="7"
            refX="9"
            refY="3.5"
            orient="auto"
          >
            <polygon points="0 0, 10 3.5, 0 7" fill="#4b5563" />
          </marker>
        </defs>
        <line
          x1={startX}
          y1="10"
          x2={endX}
          y2="30"
          stroke="#4b5563"
          strokeWidth="2"
          markerEnd={url(#arrowhead-${packet.id})}
          className="drop-shadow-sm"
        />
      </svg>
    </div>
  );
};

export default App;
