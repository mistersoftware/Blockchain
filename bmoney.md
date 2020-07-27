I am fascinated by Tim May's crypto-anarchy. Unlike the communities traditionally associated with the word "anarchy", in a crypto-anarchy the government is not temporarily destroyed but permanently forbidden and permanently unnecessary. It's a community where the threat of violence is impotent because violence is impossible, and violence is impossible because its participants cannot be linked to their true names or physical locations.

> Estoy fascinado por la criptoanarquía de Tim May. A diferencia de las comunidades tradicionalmente asociadas con la palabra "anarquía", en una criptoanarquía el
el gobierno no se destruye temporalmente sino que se prohíbe permanentemente dado que es innecesario. Es una comunidad donde la amenaza de violencia es impotente porque la violencia es imposible, y la violencia es imposible porque sus participantes no pueden ser vinculados a sus nombres verdaderos o sus ubicaciones físicas.


Until now it's not clear, even theoretically, how such a community could operate. A community is defined by the cooperation of its participants, and efficient cooperation requires a medium of exchange (money) and a way to enforce contracts. Traditionally these services have been provided by the government or government sponsored institutions and only to legal entities. In this article I describe a protocol by which these services can be provided to and by untraceable entities.

> Hasta ahora no está claro, ni siquiera teóricamente, cómo una comunidad así podría funcionar _(Nota del traductor: Al año 1998)_. Una comunidad se define por la cooperación de sus participantes, y una cooperación eficiente requiere un medio de intercambio (dinero) y una forma para hacer cumplir los contratos. Tradicionalmente, estos servicios han sido proporcionados por el gobierno o instituciones patrocinadas por el gobierno y solo por entidades legales. En este artículo describo un protocolo mediante el cual estos servicios pueden ser proporcionados por y hacia entidades imposibles de rastrear.


I will actually describe two protocols. The first one is impractical, because it makes heavy use of a synchronous and unjammable anonymous broadcast channel. However it will motivate the second, more practical protocol. In both cases I will assume the existence of an untraceable network, where senders and receivers are identified only by digital pseudonyms (i.e. public keys) and every messages is signed by its sender and encrypted to its receiver.

> En realidad describiré dos protocolos. El primero no es práctico, porque hace un uso intensivo de un canal de transmisión sincrónico, inmaterial y anónimo. Sin embargo, motivará el segundo protocolo más práctico. En ambos casos, supondré la existencia de una red no rastreable, donde los remitentes y receptores se identifican solo por seudónimos digitales (es decir, claves públicas) y cada mensaje está firmado por su remitente y [se envia] encriptado  a su receptor.

In the first protocol, every participant maintains a (seperate) database of how much money belongs to each pseudonym. These accounts collectively define the ownership of money, and how these accounts are updated is the subject of this protocol.

> En el primer protocolo, cada participante mantiene una base de datos (separada) de cuánto dinero pertenece a cada seudónimo. Estas cuentas colectivamente definen la propiedad del dinero, y cómo se actualizan estas cuentas es el tema de este protocolo.


1. The creation of money. Anyone can create money by broadcasting the solution to a previously unsolved computational problem. The only conditions are that it must be easy to determine how much computing effort it took to solve the problem and the solution must otherwise have no value, either practical or intellectual. The number of monetary units created is equal to the cost of the computing effort in terms of a standard basket of commodities. For example if a problem takes 100 hours to solve on the computer that solves it most economically, and it takes 3 standard baskets to purchase 100 hours of computing time on that computer on the open market, then upon the broadcast of the solution to that problem everyone credits the broadcaster's account by 3 units.

> 1. La creación de dinero. Cualquiera puede crear dinero transmitiendo la solución a un problema computacional previamente no resuelto. Las únicas condiciones son que debe ser fácil determinar cuánto esfuerzo informático se necesitó para resolver el problema y la solución no debería tener ningún valor, ya sea práctico o intelectual. El número de unidades monetarias creadas es igual al costo del esfuerzo informático en términos de una canasta estándar de productos. Por ejemplo, si un problema tarda 100 horas en resolverse en la computadora que lo resuelve más económicamente, y se requieren 3 canastas estándar para comprar 100 horas de tiempo de computación en esa computadora en el mercado abierto, luego de la transmisión de la solución a ese problema todos acreditan la cuenta de la emisora por 3 unidades.




2. The transfer of money. If Alice (owner of pseudonym K_A) wishes to transfer X units of money to Bob (owner of pseudonym K_B), she broadcasts the message "I give X units of money to K_B" signed by K_A. Upon the broadcast of this message, everyone debits K_A's account by X units and credits K_B's account by X units, unless this would create a negative balance in K_A's account in which case the message is ignored.

> 2. La transferencia de dinero. Si Alice (propietaria del seudónimo K_A) desea transferir X unidades de dinero a Bob (propietario del seudónimo K_B), transmite el mensaje "Doy X unidades de dinero a K_B" firmado por K_A. Tras la transmisión de este mensaje, todos debitan la cuenta de K_A por X unidades y acreditan la cuenta de K_B por X unidades, a menos que esto cree un saldo negativo en la cuenta de K_A, en cuyo caso se ignora el mensaje.



3. The effecting of contracts. A valid contract must include a maximum reparation in case of default for each participant party to it. It should also include a party who will perform arbitration should there be a dispute. All parties to a contract including the arbitrator must broadcast their signatures of it before it becomes effective. Upon the broadcast of the contract and all signatures, every participant debits the account of each party by the amount of his maximum reparation and credits a special account identified by a secure hash of the contract by the sum the maximum reparations. The contract becomes effective if the debits succeed for every party without producing a negative balance, otherwise the contract is ignored and the accounts are rolled back. A sample contract might look like this:

> 3. La realización de contratos. Un contrato válido debe incluir una reparación máxima en caso de incumplimiento para cada participante del mismo. También debe incluir una tercera parte que llevará a cabo un arbitraje en caso de disputa. Todas las partes de un contrato, incluido el árbitro, deben transmitir sus firmas antes de entrar en vigencia. Tras la emisión del contrato y todas las firmas, cada participante carga la cuenta de cada parte por el monto de su reparación máxima y acredita una cuenta especial identificada por un ___hash___ seguro del contrato por la suma de las reparaciones máximas. El contrato se hace efectivo si los débitos tienen éxito para todas las partes sin producir un saldo negativo; de lo contrario, el contrato se ignora y las cuentas se revierten. Un contrato de muestra podría verse así:

K_A agrees to send K_B the solution to problem P before 0:0:0 1/1/2000. K_B agrees to pay K_A 100 MU (monetary units) before 0:0:0 1/1/2000. K_C agrees to perform arbitration in case of dispute. K_A agrees to pay a maximum of 1000 MU in case of default. K_B agrees to pay a maximum of 200 MU in case of default. K_C agrees to pay a maximum of 500 MU in case of default.

> K_A acepta enviar a K_B la solución al problema P antes de las 00:00:00 del 1/1/2000. K_B acuerda pagar K_A 100 MU (unidades monetarias) antes de las 00:00:00 del 1/1/2000. K_C acepta realizar un arbitraje en caso de disputa. K_A acepta pagar un máximo de 1000 MU en caso de incumplimiento. K_B acepta pagar un máximo de 200 MU en caso de incumplimiento. K_C acepta pagar un máximo de 500 MU en caso de incumplimiento.

4. The conclusion of contracts. If a contract concludes without dispute, each party broadcasts a signed message "The contract with SHA-1 hash H concludes without reparations." or possibly "The contract with SHA-1 hash H concludes with the following reparations: ..." Upon the broadcast of all signatures, every participant credits the account of each party by the amount of his maximum reparation, removes the contract account, then credits or debits the account of each party according to the reparation schedule if there is one.

> 4. La celebración de contratos. Si un contrato concluye sin disputa, cada parte transmite un mensaje firmado "El contrato con SHA-1 hash H concluye sin reparaciones". o posiblemente "El contrato con SHA-1 hash H concluye con las siguientes reparaciones: ..." Tras la emisión de todas las firmas, cada participante acredita la cuenta de cada parte por el monto de su reparación máxima, elimina la cuenta del contrato, luego acredita o debita la cuenta de cada parte de acuerdo con el cronograma de reparación si hay uno.

5. The enforcement of contracts. If the parties to a contract cannot agree on an appropriate conclusion even with the help of the arbitrator, each party broadcasts a suggested reparation/fine schedule and any arguments or evidence in his favor. Each participant makes a determination as to the actual reparations and/or fines, and modifies his accounts accordingly.

> 5. La ejecución de los contratos. Si las partes de un contrato no pueden llegar a un acuerdo sobre una conclusión adecuada, incluso con la ayuda del árbitro, cada parte transmite un calendario de reparación / multas sugerido y cualquier argumento o evidencia a su favor. Cada participante toma una determinación en cuanto a las reparaciones y / o multas reales, y modifica sus cuentas en consecuencia.


In the second protocol, the accounts of who has how much money are kept by a subset of the participants (called servers from now on) instead of everyone. These servers are linked by a Usenet-style broadcast channel. The format of transaction messages broadcasted on this channel remain the same as in the first protocol, but the affected participants of each transaction should verify that the message has been received and successfully processed by a randomly selected subset of the servers.

> En el segundo protocolo, las cuentas de quién tiene cuánto dinero guardan un subconjunto de los participantes (llamados servidores de ahora en adelante) en lugar de todos. Estos servidores están vinculados por un canal de difusión de estilo _Usenet_. El formato de los mensajes de transacción emitidos en este canal sigue siendo el mismo que en el primer protocolo, pero los participantes afectados de cada transacción deben verificar que el mensaje haya sido recibido y procesado con éxito por un subconjunto de servidores seleccionado al azar.

Since the servers must be trusted to a degree, some mechanism is needed to keep them honest. Each server is required to deposit a certain amount of money in a special account to be used as potential fines or rewards for proof of misconduct. Also, each server must periodically publish and commit to its current money creation and money ownership databases. Each participant should verify that his own account balances are correct and that the sum of the account balances is not greater than the total amount of money created. This prevents the servers, even in total collusion, from permanently and costlessly expanding the money supply. New servers can also use the published databases to synchronize with existing servers.

> Dado que los servidores deben ser confiables hasta cierto punto, se necesita algún mecanismo para mantenerlos honestos. Se requiere que cada servidor deposite una cierta cantidad de dinero en una cuenta especial para usar como posibles multas o recompensas como prueba de mala conducta. Además, cada servidor debe comprometerse a publicar sus bases de datos actualizadas periódicamente con la información del dinero creado y a quien le pertenece. Cada participante debe verificar que los saldos de sus propias cuentas sean correctos y que la suma de los saldos de las cuentas no sea mayor que la cantidad total de dinero creado. Esto evita que los servidores, incluso en colusión total, expandan de manera permanente y sin costo la oferta de dinero. Los nuevos servidores también pueden usar las bases de datos publicadas para sincronizar con los servidores existentes.



The protocol proposed in this article allows untraceable pseudonymous entities to cooperate with each other more efficiently, by providing them with a medium of exchange and a method of enforcing contracts. The protocol can probably be made more efficient and secure, but I hope this is a step toward making crypto-anarchy a practical as well as theoretical possibility.

> El protocolo propuesto en este artículo permite que las ___entidades seudónimas no rastreables___ cooperen entre sí de manera más eficiente, al proporcionarles un medio de intercambio y un método para hacer cumplir los contratos. El protocolo probablemente se puede hacer más eficiente y seguro, pero espero que este sea un paso para hacer de la criptoanarquía una posibilidad práctica y teórica.


-------

Appendix A: alternative b-money creation

One of the more problematic parts in the b-money protocol is money creation. This part of the protocol requires that all of the account keepers decide and agree on the cost of particular computations. Unfortunately because computing technology tends to advance rapidly and not always publicly, this information may be unavailable, inaccurate, or outdated, all of which would cause serious problems for the protocol.

> Apéndice A: creación alternativa de _b-money_
> 
> Una de las partes más problemáticas en el protocolo b-money es la creación de dinero. Esta parte del protocolo requiere que todos los administradores de cuentas decidan y acuerden el costo de cálculos particulares. Desafortunadamente, debido a que la tecnología informática tiende a avanzar rápidamente y no siempre públicamente, esta información puede no estar disponible, ser inexacta u obsoleta, lo que podría causar serios problemas para el protocolo.



So I propose an alternative money creation subprotocol, in which account keepers (everyone in the first protocol, or the servers in the second protocol) instead decide and agree on the amount of b-money to be created each period, with the cost of creating that money determined by an auction. Each money creation period is divided up into four phases, as follows:

> Por lo tanto, propongo un subprotocolo de creación de dinero alternativo, en el que los administradores de cuentas (todos en el primer protocolo o los servidores en el segundo protocolo) deciden y acuerdan la cantidad de b-money que se creará en cada período, con el costo de crear ese dinero determinado por una subasta. Cada período de creación de dinero se divide en cuatro fases, de la siguiente manera:



1. Planning. The account keepers compute and negotiate with each other to determine an optimal increase in the money supply for the next period. Whether or not the account keepers can reach a consensus, they each broadcast their money creation quota and any macroeconomic calculations done to support the figures. 

> 1. Planificación. Los titulares de cuentas calculan y negocian entre sí para determinar un aumento óptimo en la oferta de dinero para el próximo período. Independientemente de si los titulares de cuentas pueden alcanzar un consenso, cada uno transmite su cuota de creación de dinero y cualquier cálculo macroeconómico realizado para respaldar las cifras.


2. Bidding. Anyone who wants to create b-money broadcasts a bid in the form of <x, y> where x is the amount of b-money he wants to create, and y is an unsolved problem from a predetermined problem class. Each problem in this class should have a nominal cost (in MIPS-years say) which is publicly agreed on.

> 2. Licitación. Cualquiera que quiera crear _b-money_ emite una oferta en forma de <x, y> donde x es la cantidad de _b-money_ que quiere crear, _y_ es un problema no resuelto de una clase de problema predeterminada. Cada problema en esta clase debe tener un costo nominal que se acuerde públicamente (en años MIPS, por ejemplo).


3. Computation. After seeing the bids, the ones who placed bids in the bidding phase may now solve the problems in their bids and broadcast the solutions.

> 3. Computación. Después de ver las ofertas, los que presentaron ofertas en la fase de licitación ahora pueden resolver los problemas en sus ofertas y transmitir las soluciones.


4. Money creation. Each account keeper accepts the highest bids (among those who actually broadcasted solutions) in terms of nominal cost per unit of b-money created and credits the bidders' accounts accordingly.

> 4. Creación de dinero. Cada administrador de cuentas acepta las ofertas más altas (entre las que realmente emitieron soluciones) en términos de costo nominal por unidad de dinero b creado y acredita las cuentas de los licitantes en consecuencia.

_b-money_ by Wei Dai - 1998
