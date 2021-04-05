# 💸 b-money: El origen de la tecnología blockchain 

## Estoy fascinado por la _cripto-anarquía_ de Tim May. A diferencia de las comunidades tradicionalmente asociadas con la palabra anarquía, en una _cripto-anarquía_ el gobierno no se destruye temporalmente sino que se prohíbe permanentemente dado que es innecesario. 

La amenaza de violencia es impotente porque la violencia es imposible, y la violencia es imposible porque sus participantes no pueden ser vinculados a sus nombres verdaderos o sus ubicaciones físicas.

 
Hasta ahora no está claro, ni siquiera teóricamente, cómo podría funcionar una comunidad así. Una comunidad se define por la cooperación de sus participantes, y una cooperación eficiente requiere un medio de intercambio (dinero) y una forma para hacer cumplir los contratos. Tradicionalmente, estos servicios han sido proporcionados por el gobierno o instituciones patrocinadas por el gobierno y solo por entidades legales. En este artículo describo un protocolo mediante el cual estos servicios pueden ser proporcionados a entidades imposibles de rastrear por entidades igualmente irrastreables.

 
> ___" En realidad describiré dos protocolos. El primero no es práctico, porque hace un uso intensivo de un canal de transmisión sincrónico, inmaterial y anónimo. Sin embargo, motivará el segundo protocolo más práctico. En ambos casos, supondré la existencia de una  red intrazable, donde los remitentes y receptores se identifican solo por seudónimos digitales (es decir, claves públicas) y cada mensaje está firmado por su remitente y se envia encriptado al receptor ".___


## ⛓ En el primer protocolo, cada participante mantiene una base de datos (separada) de cuánto dinero pertenece a cada seudónimo. Estas cuentas definen la propiedad del dinero en consenso. A continuación se muestra cómo se actualiza tal libro contable distribuido,


## 1. ⛏ Creación de dinero.

Cualquiera puede crear dinero transmitiendo la solución a un problema computacional previamente no resuelto _(Proof of work)_. Las únicas condiciones son que debe ser fácil determinar cuánto esfuerzo informático se necesitó para resolver el problema y la solución no debería tener ningún valor, ya sea práctico o intelectual. El número de unidades monetarias creadas es igual al costo del esfuerzo informático invertido en su creación. Por ejemplo, si un problema tarda 100 horas en resolverse, y se requieren 3 unidades estándar para comprar 100 horas de tiempo de computación en esa computadora en el mercado abierto, luego de la transmisión de la solución a ese problema todos añadiran 3 unidades a la cuenta de quien emitio la solución.
 
## 2. 📫 Transferencia de dinero.

Si Alice (propietaria del seudónimo K_A) desea transferir X unidades de dinero a Bob (propietario del seudónimo K_B), transmite el mensaje "Doy X unidades de dinero a K_B" firmado por K_A. Tras la transmisión de este mensaje, todos debitan la cuenta de K_A por X unidades y acreditan la cuenta de K_B por X unidades, a menos que esto cree un saldo negativo en la cuenta de K_A, en cuyo caso se ignora el mensaje.
 
## 3. ✒ Realización de contratos.

Un contrato válido debe incluir una reparación máxima en caso de incumplimiento para cada participante del mismo. También debe incluir una parte que llevará a cabo un arbitraje en caso de disputa. Todas las partes de un contrato, incluido el árbitro, deben transmitir sus firmas antes de que entre en vigencia. Tras la emisión del contrato y todas las firmas, cada participante carga la cuenta de cada parte por el monto de su reparación máxima y acredita una cuenta especial identificada por un hash seguro del contrato por la suma de las reparaciones máximas. El contrato se hace efectivo si los débitos tienen éxito para todas las partes sin producir un saldo negativo; de lo contrario, el contrato se ignora y las cuentas se revierten. Un contrato de muestra podría verse así:
 
> ___" K_A acepta enviar a K_B la solución al problema P antes de las 00:00:00 del 1/1/2000. K_B acuerda pagar K_A 100 MU (unidades monetarias) antes de las 00:00:00 del 1/1/2000. K_C acepta realizar un arbitraje en caso de disputa ".___
> * ___K_A acepta pagar un máximo de 1000 MU en caso de incumplimiento___ 
> * ___K_B acepta pagar un máximo de 200 MU en caso de incumplimiento___
> * ___K_C acepta pagar un máximo de 500 MU en caso de incumplimiento___ 

 
## 4. 🤝 Celebración de contratos.

Si un contrato concluye sin disputa, cada parte transmite un mensaje firmado "El contrato con SHA-1 hash H concluye sin reparaciones". o posiblemente "El contrato con SHA-1 hash H concluye con las siguientes reparaciones: ..." Tras la emisión de todas las firmas, cada participante acredita la cuenta de cada parte por el monto de su reparación máxima, elimina la cuenta del contrato, luego acredita o debita la cuenta de cada parte de acuerdo con el cronograma de reparación si hay uno.
 
## 5. ⚖ Ejecución de los contratos.

Si las partes de un contrato no pueden llegar a un acuerdo sobre una conclusión adecuada, incluso con la ayuda del árbitro, cada parte transmite un calendario de reparación / multas sugerido y cualquier argumento o evidencia a su favor. Cada participante toma una determinación en cuanto a las reparaciones y / o multas reales, y modifica sus cuentas en consecuencia.


## 💰 En el segundo protocolo, las cuentas de quién tiene cuánto dinero guardan un subconjunto de los participantes (llamados servidores de ahora en adelante) en lugar de todos. Estos servidores están vinculados por un canal de difusión de estilo Usenet. El formato de los mensajes de transacción emitidos en este canal sigue siendo el mismo que en el primer protocolo, pero los participantes afectados de cada transacción deben verificar que el mensaje haya sido recibido y procesado con éxito por un subconjunto de servidores seleccionado al azar.


Dado que los servidores deben ser confiables, se necesita algún mecanismo para mantenerlos honestos. Para esto se requiere que cada servidor deposite una cierta cantidad de dinero en una cuenta especial para usar como posibles multas o recompensas _(conocido hoy como **proof of stake**)_. Además, cada servidor debe comprometerse a publicar periódicamente sus bases de datos, que incluya un registro del dinero creado y sus propietarios. Cada participante debe verificar que los saldos de sus propias cuentas sean correctos y que la suma de los saldos de las cuentas no sea mayor que la cantidad total de dinero creado. Esto evita que los servidores, incluso en colusión total, expandan de manera permanente y sin costo la oferta de dinero (_doble gasto_). Los nuevos servidores que se añadan a la red también podrán usar las bases de datos publicadas por los demas para sincronizarse.
 
> El protocolo propuesto en este artículo permite que las entidades seudónimas no rastreables cooperen entre sí de manera más eficiente, al proporcionarles un medio de intercambio y un método para hacer cumplir los contratos. El protocolo probablemente se puede hacer más eficiente y seguro, pero espero que este sea un paso para hacer de la criptoanarquía una posibilidad práctica y teórica.


## Apéndice A: creación alternativa de ___b-money___ 

Una de las partes más problemáticas en el protocolo ___b-money___ es la creación de dinero. Esta parte del protocolo requiere que todos los administradores de cuentas decidan y acuerden el costo de cálculos particulares. Desafortunadamente, debido a que la tecnología informática tiende a avanzar rápidamente y no siempre públicamente, esta información puede no estar disponible, ser inexacta u obsoleta, lo que podría causar serios problemas para el protocolo.
 
Por lo tanto, propongo un subprotocolo de creación de dinero alternativo, en el que los administradores de cuentas (todos en el primer protocolo o los servidores en el segundo protocolo) deciden y acuerdan la cantidad de ___b-money___ que se creará en cada período, con el costo de crear ese dinero determinado por una subasta. Cada período de creación de dinero se divide en cuatro fases, de la siguiente manera:
 
## 1. Planificación.

Los titulares de cuentas calculan y negocian entre sí para determinar un aumento óptimo en la oferta de dinero para el próximo período. Independientemente de si los titulares de cuentas pueden alcanzar un consenso, cada uno transmite su cuota de creación de dinero y cualquier cálculo macroeconómico realizado para respaldar las cifras.

## 2. Licitación o subasta.

Cualquiera que quiera crear ___b-money___ emite una oferta en forma de ___<x, y>___ donde ___x___ es la cantidad de ___b-money___ que quiere crear, ___y___ es un problema no resuelto de una clase de problema predeterminada. Cada problema en esta clase debe tener un costo nominal (en años MIPS, por ejemplo) que se acuerde públicamente.

## 3. Computación.

Después de ver las ofertas, los que presentaron ofertas en la fase de licitación ahora pueden resolver los problemas en sus ofertas y transmitir las soluciones.

## 4. Creación de dinero.

Cada administrador de cuentas acepta las ofertas más altas (entre las que realmente emitieron soluciones) en términos de costo nominal por unidad de ___b-money___ creado y acredita las cuentas de los licitantes en consecuencia.
 
[Wei Dai - 1998](http://www.weidai.com/bmoney.txt)
 
_Nota: Me he tomado ciertas libertades en la traducción con la intención de acercar el texto al lector procurando no perder rigurosidad técnica._
 
## ¿Deseas colaborar? Enviame un issue 
