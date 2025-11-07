// Configuración global del generador de D.N.I.
(function globalDNISetup(){
  
  const style = document.createElement('style');
  style.type = 'text/css';
  style.textContent = `
    html, body { height: 100%; margin: 0; }
    body { font-family: Arial, sans-serif; background: #0b1220; }
    .dni-top-left { position: fixed; left: 18px; top: 18px; font-weight: 700; font-family: Arial, sans-serif; color: #ffffff; z-index: 9999; font-size: 20px; }
    .dni-center-wrap { position: fixed; left: 0; top: 0; width: 100%; height: 100%; display: flex; align-items: center; justify-content: center; }
    .dni-card { background: #4da2c4ff; border-radius: 14px; padding: 28px 40px; box-shadow: 0 10px 30px rgba(2,6,23,0.6); user-select: none; display: flex; align-items: center; justify-content: center; max-width: 90%; }
    .dni-card-text { font-family: Arial, sans-serif; color: #ffffff; font-size: 28px; font-weight: 700; text-align: center; white-space: nowrap; }
    @media (min-width:980px){ .dni-card{ width:520px; height:120px } .dni-card-text{ font-size:32px } }
    @media (max-width:979px){ .dni-card{ width:86%; height:96px } .dni-card-text{ font-size:22px } }
  `;
  document.head.appendChild(style);

  // Crear elemento superior izquierdo
  const topLeft = document.createElement('div');
  topLeft.className = 'dni-top-left';
  topLeft.textContent = 'Generador de D.N.Is';
  document.body.appendChild(topLeft);

  // Crear contenedor central y tarjeta
  const centerWrap = document.createElement('div');
  centerWrap.className = 'dni-center-wrap';

  const card = document.createElement('div');
  card.className = 'dni-card';
  card.setAttribute('role', 'group');
  card.setAttribute('aria-label', 'Área para generar D.N.I. (sin control de clic)');

  const cardText = document.createElement('div');
  cardText.className = 'dni-card-text';
  cardText.textContent = 'Haz clic para generar...';

  card.appendChild(cardText);
  centerWrap.appendChild(card);
  document.body.appendChild(centerWrap);

  // Exportar referencia en window para usos posteriores si se desea
  window._GeneradorDNI = { root: centerWrap, topLeft, card, cardText };
})();
 let abc = false
 // Agregar evento para generar el DNI al hacer clic
 const card = _GeneradorDNI.card;
 const cardText = _GeneradorDNI.cardText;

 card.addEventListener('click', () => {
  // Generar número aleatorio de 8 dígitos
  const numeroDNI = Math.floor(Math.random() * (99999999 - 10000000 + 1)) + 10000000
  const letras = "TRWAGMYFPDXBNJZSQVHLCKE"
  const letraDNI = letras[numeroDNI % 23]
abc = true
  // Mostrar resultado en el rectángulo
  cardText.textContent = `D.N.I: ${numeroDNI}${letraDNI}`;
})


if (abc == true) {

document.body.appendChild(topRight)
   console.log ("Clic para descargar un D.N.I. aleatorio")
   style.fontFamily = "Arial, sans-serif"
   
}
