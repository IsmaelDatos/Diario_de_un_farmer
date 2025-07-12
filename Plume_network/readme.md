> ⚠️ **Disclaimer:**  
> Este análisis es solo un proyecto personal y un hobby. No constituye asesoría financiera ni recomendación de inversión.  
> Siempre realiza tu propia investigación (DYOR) antes de tomar cualquier decisión relacionada con criptomonedas o DeFi.  
> ¡Sé responsable y atiende tu propio perfil de riesgo!  

# 🧠 Análisis Plume Network

Este análisis forma parte de la serie `Diario_de_un_farmer`, donde documento mis decisiones como analista y farmer en Web3.

## 🚀 1. ¿Qué es Plume Network?
Plume es una blockchain pública, compatible con la Máquina Virtual de Ethereum (EVM), diseñada para impulsar la próxima evolución de los Activos del Mundo Real (Real World Assets, RWA). No se limita a la simple tokenización de activos: su objetivo es permitir que puedan usarse de forma nativa como criptomonedas — permitiendo staking, intercambios, préstamos, préstamos apalancados (looping) y más.

A través de la integración de activos institucionales con herramientas DeFi, Plume permite que activos tradicionalmente inaccesibles — como crédito privado, ETFs y materias primas — se vuelvan componibles, sin permisos y utilizables con unos pocos clics.

Su misión es sencilla: tender un puente entre las finanzas tradicionales y el ecosistema cripto mediante una adopción impulsada por la demanda, sin sacrificar la transparencia, la apertura ni la experiencia del usuario.
### 🏢 Reconocimiento institucional

Otro punto destacado es que **Grayscale** incluyó a Plume en su listado de activos a evaluar. Esto aporta un respaldo adicional, al estar en el radar de uno de los mayores gestores de activos digitales.

<p align="center">
  <img src="img/grayscale_tweet.png" alt="Tweet de Grayscale mencionando a Plume" width="600"/>
  <br/>
  <em>Fuente: <a href="https://x.com/Grayscale/status/1943365202680123888">tweet de Grayscale</a></em>
</p>

> **Por qué importa:**  
> Estar en la lista de Grayscale significa que Plume entra en una due diligence institucional, lo que mejora su visibilidad y confianza en el mercado.  
> 
---

## 📊 2. Objetivos del notebook

1. **Inventariar y documentar** las APIs de Plume  
2. **Explorar** mis datos de wallet y PP (Plume Points)  
3. **Identificar** las acciones más rentables para farmear PP  
4. **Diseñar** estrategias eficientes para la Season 2 del airdrop  
5. **Extraer insights** prácticos para recursos limitados  

---


## 📖 3. Contexto inicial

- Comencé la Season 2 con **1 000 PP** gracias al airdrop inicial.  

---

## 📅 4. Contexto: Season 2 del Airdrop

- **Asignación total:** 150 000 000 PLUME  
- **Periodo:** 5 de junio 2025 – TBA (por anunciar)  
- **Criterio principal de distribución:** Plume Points (PP)

**¿Qué son los PP?**  
Son puntos otorgados por interactuar con diferentes dApps (Bridge, DEX, Lending, etc.) o participar en campañas. Existen dos categorías:

1. **Self PP:** generados por la propia actividad en la red.  
2. **Referral PP:** obtenidos al invitar usuarios; solo aplican si los referidos realizan acciones.

> ⚠️ La asignación de PP no es lineal ni perfectamente predecible: la misma acción un día puede otorgar distinta cantidad de puntos en otra ocasión.

![Distribución de la Season 2](img/S2Allocation.png)  
*Fuente: [Plume Blog](https://plume.org/blog/plume-airdrop)*

---








## 🔗 5. APIs utilizadas
| Uso                                                  | Notas                                                                                                 | Enlace                                                                                           |
|-------------------------------------------------------|--------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|
| Mostrar el leaderboard general                        | Se pueden modificar los parámetros `offset` (posición inicial) y `count` (cantidad de resultados).    | https://portal-api.plume.org/api/v1/stats/leaderboard?offset=3600&count=10&walletAddress=undefined&overrideDay1Override=false&preview=false |
| Ver las 3 actividades que más generaron PP ayer       | Usa el parámetro `walletAddress=` con cualquier wallet para obtener resultados personalizados.        | https://portal-api.plume.org/api/v1/stats/pp-totals/?walletAddress=0xE3c55E0c1E9170d9531Fb6A5F9c6442AD46D50F4 |

---

## 📌 6. Estadísticas de la Mainnet de Plume

![Estadísticas de la mainnet de Plume](img/PlumeMainnetStats.png)

Con un **TVL** (Total Value Locked) de 120 M USD, Plume confirma su solidez como L2.

*Fuente: [Defillama](https://defillama.com/chain/plume-mainnet)*

---


## ⚙️ 5. Métricas clave para la S2

Antes de definir estrategias, identifiqué **qué actividades generan más PP**:

1. Consulté la API del leaderboard para listar todas las wallets con > 0 XP.  
2. Para cada wallet, extraje sus **tres actividades top** en PP.  
3. Conté la frecuencia de cada acción en el **top 3 global**.

> **Conclusión preliminar:**  
> Las interacciones con protocolos y el staking dominan el top 3. Sin embargo, dado mi capital limitado, no puedo destinar una gran cantidad al staking. Solo una parte, ya que no me parece una opción suficientemente rentable, así que me concentraré en interacciones.

![Top 3 de actividades más frecuentes](img/top3activity.png)

| Wallet | Rank en leaderboard |$PLUME en stake  |
|-----------|-----------|-----------|
| 0xff0...  |  1   | 1,880,000  |
| 0x4ce...  |  2   | 1,080,000   |
| 0x861...  |  3   | 800,000   |
| 0xE3c... (yo)|  1288 | 2110   |

> **Insight:**  
> Estar en el puesto 1 288 de más de 200k+ wallets confirma que mi estrategia con recursos limitados ha funcionado. Mi enfoque será en **interacciones DeFi de bajo costo**, complementadas con **staking** y **bloqueos selectivos** en protocolos clave, sin comprometer la totalidad de mi capital.


---

## 📈 6. PP emitidos por día

La API del leaderboard resulta especialmente valiosa, ya que nos permite extraer los PP diarios de todas las wallets. He estado recopilando estos datos durante varios días; aunque no cuento con información desde el día uno de la Season 2, sí dispongo de los siguientes registros:



| Fecha      | PP totales  | PP/PLUME | Puntos emitidos | Variación diaria (dPP/PLUME(%) |
|------------|-------------|----------|-----------------|----------------------|
| 04/07/2025 | 604 029 201 | 0.2483   | –               | –                    |
| 05/07/2025 | 612 914 321 | 0.2447   |  8 885 120      | –1.44 %              |
| 06/07/2025 | 620 350 895 | 0.2417   |  7 436 574      | –1.19 %              |
| 07/07/2025 | 636 843 843 | 0.2355   | 16 492 948      | –2.58 %              |
| 08/07/2025 | 646 452 841 | 0.2320   |  9 608 998      | –1.48 %              |
| 09/07/2025 | 654 351 972 | 0.2292   |  7 899 131      | –1.20 %              |
> 🧮 **Nota técnica:**  
> La **variación diaria (%)** del ratio **PP/PLUME** la calculé con la siguiente fórmula:
>
> \[
> \text{Variación \%} = \frac{\text{PP/PLUME}_{\text{hoy}} - \text{PP/PLUME}_{\text{ayer}}}{\text{PP/PLUME}_{\text{ayer}}} \times 100
> \]
>
> Esta métrica permite entender qué tan rápido se está diluyendo el valor de los puntos (PP) en relación a la cantidad total de tokens PLUME asignados para la Season 2.


El ratio **PP/PLUME** se calcula de manera directa: basta con dividir la asignación total de 150 M de PLUME entre el total de PP emitidos en cada fecha. Con esto en mano, podemos entender mejor la dinámica de emisión y anticipar cómo se comportará el farming a lo largo de la campaña.

---

## 🔍 7. Análisis de wallets (10 Julio 2025)

- **Wallets únicas analizadas:** 201 993  

#### 📊 Distribución de Plume Points  
![Distribución de niveles](img/tiers.png)  

Se observa un gran número de wallets con menos de 1 000 PP, lo que sugiere la posible presencia de sybils. Detectar y limpiar esas cuentas puede favorecer nuestra posición en el leaderboard.

![Posibles sybils](img/probablesSybils.png)

> De las ~201 K wallets, **39 K** tienen exactamente 200 PP a 30 días del inicio de la S2. Es muy probable que se trate de sybils. Profundizar en este segmento será parte de un análisis futuro.

---

### 🔗 Contratos clave y patrones de interacción

Para enfocar nuestra estrategia sin depender de TVL o stake, filtré las wallets con **referral XP = 0** y alto PP. Luego, identifiqué los contratos más usados por este grupo:

| Uso                | Contrato                                    | Interacciones | Wallets que lo usan |
|--------------------|---------------------------------------------|--------------:|--------------------:|
| Stake              | `0x30c7…fede871`                            |        1 183  |                  71 |
| Daily Spin         | `0xb8e9…73d71`                              |        2 108  |                  67 |
| Nest Alpha Vault   | `0x593c…38db`                               |          645  |                  63 |
| Re7 pUSD           | `0xc0df…5b16`                               |          864  |                  60 |
| PUSD Token         | `0xdddd…6f3f`                               |        4 263  |                  66 |

Con esta información, podremos diseñar rutas de farming basadas en contratos de alta frecuencia, optimizando nuestro esfuerzo y maximizando PP sin necesidad de grandes inversiones en stake o TVL.  

---

## 🎯 8. Mi estrategia

Tras analizar las actividades más comunes de las wallets mejor posicionadas, notamos un patrón claro:

- Hacen **staking** con cantidades considerables de $PLUME.  
- Depositan **pUSD en el nALPHA Vault** y luego esos tokens se usan dentro de **Royco**.

Siguiendo esta lógica —y adaptándola a mi capital limitado— decidí implementar una versión optimizada de esta estrategia.



### 🔒 Staking

Incrementé de forma moderada mi participación en staking, delegando en el validador oficial de **Plume Foundation**. Esta acción, aunque no representa mi principal fuente de puntos, refuerza la consistencia de mi actividad.


### 🧪 Nest + Royco

Después, implementé un ciclo entre protocolos:

1. Deposité **pUSD en el nALPHA Vault**.

<p align="center">
  <a href="https://app.nest.credit/">
    <img src="img/nALPHA.png" alt="nALPHA Vault" width="500"/>
  </a>
</p>

<p align="center">
  👉 <a href="https://app.nest.credit/">Fuente: app.nest.credit</a>
</p>

2. Utilicé los tokens generados para interactuar con **Royco**.

<p align="center">
  <a href="https://plume.royco.org/market/98866/0/0xc41a78d629855b99788af7449020a88eec807be5f26ab050908dd7e633735897">
    <img src="img/nALPHAonRoyco.png" alt="nALPHA en Royco" width="500"/>
  </a>
</p>

<p align="center">
  👉 <a href="https://plume.royco.org/market/98866/0/0xc41a78d629855b99788af7449020a88eec807be5f26ab050908dd7e633735897">Fuente: Royco nALPHA pool</a>
</p>

---

3. Identifiqué también otras **pools** con buen potencial y decidí diversificar ligeramente.

<p align="center">
  <a href="https://plume.royco.org/market/98866/0/0x40bb8b77686fdea111f3e5b369dacd049abb8224550b453b6308b1038638e355">
    <img src="img/WPLUMEonRoyco.png" alt="WPLUME en Royco" width="500"/>
  </a>
</p>

<p align="center">
  👉 <a href="https://plume.royco.org/market/98866/0/0x40bb8b77686fdea111f3e5b369dacd049abb8224550b453b6308b1038638e355">Fuente: Royco WPLUME pool</a>
</p>


> Esta estrategia refleja lo observado en wallets activas y prioriza **movimientos tácticos**, más que volumen.

---

### 📈 Comparativa de puntos

Antes de realizar estos movimientos, mi cantidad de puntos era:

<p align="center">
  <img src="img/MyPlumePoints.png" alt="Puntos antes de los depósitos">
</p>

Después de ejecutar la estrategia:

<p align="center">
  <img src="img/MyPlumePoints2.png" alt="Puntos después de los depósitos">
</p>

---

### 🔁 Actividades diarias mínimas

Para mantener una presencia activa y constante en el ecosistema, realizo diariamente las siguientes acciones:

- ✅ Stakear 1 $PLUME en cualquier validador  
- 🎰 Realizar el **Daily Spin**  
- 🔄 Hacer un **swap**  
- 💧 Depositar nALPHA en **Royco**

> **Nota:** Todas estas últimas acciones pueden hacerse con montos pequeños. Lo importante no es el volumen, sino la **frecuencia** y **actividad registrada** dentro del protocolo.

## 🗂️ 9. Ubicación del código fuente

Todo el análisis y los scripts complementarios están disponibles en el repositorio. Para abrir directamente el notebook con todo el código y las visualizaciones, haz clic aquí:

🔗 [Abrir `Plume_network/Notebook.ipynb`](./Plume_network/Notebook.ipynb)

Si abres este enlace en GitHub, verás el notebook renderizado con las celdas de código y las gráficas integradas

---

## 🧾 10. Conclusión

Este análisis no intenta prometer ganancias rápidas ni vender humo. Es solo una guía basada en mi experiencia real como usuario con recursos limitados. La idea es compartir lo que he aprendido sobre cómo moverse de forma inteligente en Plume y sacarle provecho al ecosistema con decisiones simples, pero pensadas.

Mi enfoque no busca competir con ballenas, sino demostrar que **con estrategia, criterio y participación activa** es posible obtener recompensas significativas sin grandes inversiones.

Este documento evolucionará conforme avance la Season 2 y seguiré agregando nuevos insights, análisis, mejoras y resultados.

¡Gracias por leer y suerte farmeando! 🚀

<p align="center">
  👉 <a href="https://portal.plume.org/?referrer=XanthicReliablePot183">Ir al portal de Plume S2</a>
</p>

---
