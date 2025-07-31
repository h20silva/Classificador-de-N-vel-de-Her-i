// Classificador de Nível de Herói (versão melhorada)

function obterNivelHeroi(xp) {
  if (typeof xp !== "number" || isNaN(xp)) {
    return "Desconhecido";
  }
  if (xp < 0) {
    return "Desconhecido";
  }

  // Define os níveis em ordem decrescente de requisito mínimo de XP
  const niveis = [
    { nome: "Radiante", minimo: 10001 },
    { nome: "Imortal", minimo: 9001 },
    { nome: "Ascendente", minimo: 8001 },
    { nome: "Platina", minimo: 7001 },
    { nome: "Ouro", minimo: 5001 },
    { nome: "Prata", minimo: 2001 },
    { nome: "Bronze", minimo: 1001 },
    { nome: "Ferro", minimo: 0 },
  ];

  for (const nivel of niveis) {
    if (xp >= nivel.minimo) {
      return nivel.nome;
    }
  }

  return "Desconhecido"; // fallback, não deve acontecer
}

// Exemplo de uso
let nome = "Arthos"; // pode mudar
let xp = 8500;       // pode testar outros valores

let nivel = obterNivelHeroi(xp);
console.log(`O Herói de nome ${nome} está no nível de ${nivel}.`);
