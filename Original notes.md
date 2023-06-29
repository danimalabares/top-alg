# Topología Algebraica

Notas del curso básico impartido por Luis Jorge Sánchez Saldaña durante el semestre 2023-2. El material está basado en el Hatcher y en los videos del profesor disponibles en YouTube. Seguiré trabajando con el profesor sobre este documento (que fue escrito usando el software Typora): ¡cualquier comentario es bienvenido!

dag@ciencias.unam.mx

Daniel GCA

## Grupo fundamental

### Consecuencias del grupo fundamental del círculo

##### Teorema del punto fijo de Brouwer

Toda función $f:D^2\to D^2$ tiene un punto fijo.

*Dem* Supongamos que existe $f:D^2\to D^2$ que no tiene puntos fijos. Entonces podemos definir la función
$$
r:D^2\to \partial D^2
$$
definida por tomar el rayo que empieza en $f(x)$ y termina en $\partial D^2$ pasando por $x$. Resulta que $r$ es continua y que es un retracto, ie restringida a la frontera es la identidad. Entonces $r_*$ es supra, pero eso es imposible. $\qquad\square$

*Obs* También es cierto para toda dimensión usando grupos de homología.

##### Proposición

##### $\pi_1(X\times Y,(x_0,y_0))\cong \pi_1(X,x_0)\times\pi_1(Y,y_0)$

*Dem*ostración. Si $[f]\in\pi_1(X\times Y,(x_0,y_0))$, debe ser cierto que
$$
\begin{align*}
f:I&\to X\times Y\\
t&\mapsto (t_x(t),f_y(t))
\end{align*}
$$
Definamos $[f]\mapsto ([f_x],[f_y])$ y veamos que está bien definida. Bueno, si $f\cong g \text{	rel	} 0,1$, la homotopía que las relaciona tiene por funciones coordenadas las dos homotopías que necesitamos.

La inversa es $([f],[g])\mapsto[(f,g)]$.

Para ver que son morfismos, basta escribir con cuidado las definiciones.$\qquad\square$

### Grupos fundamentales de esferas y $\mathbb{R}^n$

##### Lema

Sea $X=\bigcup_{\alpha\in\ I} A_\alpha$ tal que

* $A_\alpha$ son abiertos (es una cubierta abierta)
* Existe $x_0\in\bigcap A_\alpha$
* $A_\alpha$ es arco conexo
* $A_\alpha\cap A_\beta$ también es arcoconexo $\forall\alpha,\beta$.

Entonces todo lazo $\gamma$ en $X$ es homotópico rel 0,1 a un producto (concatenación) de lazos de la forma
$$
\gamma\cong\gamma_1...\gamma_n
$$
tal que toda $\gamma_i$ está en algún $A_\alpha$.

*Demostración.* Sea $\gamma$ un lazo en $X$ basado en $x_0$. Si $\gamma$ ya es un lazo en algún $A_\alpha$, terminamos. Si no, tomemos $\gamma(t)\in\text{img }{\gamma}$. Como $A_\alpha$ es abierto, existe una vecindad $U\subset A_\alpha$ de $\gamma(t)$ en la imagen de $\gamma$. Luego $\{\gamma^{-1}(U_t)\}$ es una cubierta abierta de $I$, y como es compacto, existe una subcubierta finita $\{U_1,...,U_\ell\}$. De hecho existen $t_0=0,t_1,...,t_m=1$ partición de $I$ tales que $\gamma[t_i,t_{i+1}]\subset A_\alpha$ para alguna $\alpha$.

Definimos $\gamma'_i=\gamma\vert_{[t_i,t_{i+1}]}$. Entonces, $\gamma=\gamma'_0...\gamma'_{m-1}$. No hemos terminado porque estos $\gamma'$ no necesariamente son lazos.

Nos fijamos en $\gamma(t_i)$. Bueno este punto es el final de $\gamma'_{i-1}$ y el inicial de $\gamma'_i$, por lo que debe estar en la intersección de los correspondientes $A_\alpha$'s. Por la última condición del lema, existe un camino $h:I\to A_{\alpha_{i-1}}\cap A_ {\alpha_i}$ que conecta $\gamma(t_1)$ con $x_0$.

Notemos que $\gamma_0:=\gamma'_0\bar{h}_0$ es un lazo en $A_{\alpha_1}$ basado en $x_0$ (la barra denota recorrer en sentido contrario). Para el que sigue, $\gamma_1:=h_0\gamma'_1\bar{h}_1$ hace la chamba en $A_{\alpha_1}$. El último es $\gamma_{m-1}:=h_{m-2}\gamma'_{m-1}$.

Por fin, 
$$
\gamma=\gamma_0\gamma_1...\gamma_{m-1}=(\gamma'_0\bar{h}_0)(h_0\gamma'_1\bar{h}_1)(h_1\gamma'_2\bar{h}_2)...(h_{m-2}\gamma_{m-1})\cong\gamma'_0...\gamma'_{m-1}=\gamma
$$
ya que se cancelan los $h$'s en medio, ie. se homotopean al $\gamma(t_i)$.

##### Corolario (para grupos fundamentales triviales)

Sea $X=\bigcup A_\alpha$ como en el lema. Supongamos que $\pi_1(A_\alpha,x_0)$ es trivial $\forall\alpha$. Entonces $\pi_1(X,x_0)\cong1$.

*Demostración.* Sea $[\gamma]\in\pi_1(X,x_0)$. Por el lema, $[\gamma]=[\gamma_1...\gamma_n]$ tal que cada $\gamma_i$ está en algún $A_\alpha$. Entonces, $\gamma_i\cong c_{x_0}$ en $A_\alpha$ y de hecho esa homotopía también vale en todo $X$. Entonces, $\gamma\cong c_{x_0}$.

##### Proposición $\pi_1(S^2,x_0)\cong 1$.

*Demostración.* Basta ver que se satisfacen las condiciones del lema y y la del corolario

Consideremos la función altura de la esfera en $\mathbb{R}$, digamos $p$. Sea $\varepsilon>0$. Definimos $A_1=p^{-1}((-\varepsilon,\infty))$, una vecindad del hemisferio norte. Análogamente, sea $A_2=p^{-1}((-\infty,\varepsilon))$. Estos dos conjuntos satisfacen las primeras tres condiciones para toda $n$ fácilmente. Para la última, sólo notamos que $A_1\cap A_2\cong S^{n-1}\times(-\varepsilon,\varepsilon)$.

##### Definición. Simplemente conexo.

Un espacio $X$ es simplemente conexo (1-conexo) si

* es arco-conexo
* $\pi_1(X,x_0)=1$

##### Teorema. $\mathbb{R}\cong\mathbb{R}^n\iff n=1$

*Demostración.* Si existiera un homeomorfismo $f:\mathbb{R}\to\mathbb{R}^n$, también lo sería $f:\mathbb{R}-\{0\}\to\mathbb{R}^n-\{f(0)\}$ , que no es posible.

##### Teorema. $\mathbb{R}^2\cong\mathbb{R}^n\iff n=2$.

*Demostración.* Si $n=1$, usamos el teorema anterior así que mejor supongamos que $n\geq3$. Supongamos que hay un homeomorfismo $f:\mathbb{R}^2\to\mathbb{R}^n$ y entonces Supongamos que hay un homeomorfismo $f:\mathbb{R}^2-\{0\}\to\mathbb{R}^n-\{0\}$. Luego, $\mathbb{Z}\cong\pi_1(S^1\times\mathbb{R})\cong\pi_1(S^{n-1}\times\mathbb{R})\cong1$, que no es posible.$\qquad\square$

##### Teorema. $\mathbb{R}^n\cong\mathbb{R}^m\iff n=m$.



##### Definición (Funciones homotópicas rel A)

Consideremos $A\subseteq X$ y $B\subseteq Y$. Usaremos la notación
$$
\begin{align*}
f:(X,A)&\to(X,B)

\end{align*}
$$
si $f:X\to X$ es tal que $f(a)\in B$ para toda $a\in A$.

Dos funciones $f,g:(X,A)\to (Y,B)$ son homotópicas $\text{rel }A$ si $\exists H:X\times I\to Y$ tal que
$$
H(x,0)=f(x)\qquad \forall x\in X\\
H(x,1)=g(x)\qquad \forall x\in X\\
H(a,t)\in B\qquad\forall a\in A
$$



##### Proposición

Si $f,g:(X,x_0)\to(Y,y_0)$ son homotópicas $\text{rel }x_0$, entonces $f_*,g_*:\pi_1(X,x_0)\to\pi_1(Y,y_0)$ son iguales.

*Demostración.* Tomamos un elemento $[\gamma]\in\pi_1(X,x_0)$. Queremos ver que
$$
f_*[\gamma]=g_*[\gamma]\iff[f\gamma]=[g\gamma]
$$
Y bueno tenemos la homotopía $H$ entre las funciones. Usaremos la función $G:I\times I\to X\times I$. La homotopía ganadora es $HG$.

##### Lema. Homeomorfismo salvo punto base usando funciones homotópicas

Sean $f,g:(X,x_0)\to(Y,y_0)$ son homotópicas $\text{rel }x_0$ mediante $H:X\times I\to Y$. Definamos $h:I\to Y$ tal que $h(t)=H(x_0,t)$, la trayectoria de un punto $x_0$. Entonces el siguiente diagrama conmuta (la flecha del beta va pa arriba):

<img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230215150129323.png" alt="image-20230215150129323" style="zoom:70%;" />

donde $\beta_h$ es el homeomorfismo de cambio de punto base.

*Demostración.* Queremos ver que $\beta_h\circ g_*=f_*$. Sea pues $\gamma$ un lazo basado en $x_0$. Queremos ver que $f\gamma\cong\beta_h(g\gamma)$. *Detalles*.

### Grupos libres y productos libres

<u>Construcción del grupo libre</u>

Tomemos un conjunto por ahora finito $S=\{a_1,...,a_n\}$. Tomemos también $\bar{S}=\{a_1^{-1},...,a_n^{-1}\}$. Y las palabras $P_S=\{\text{Palabras en }S\cup\bar{S}\}$. Ahí está también la palabra vacía, $\empty$. Definamos la concatenación: la palabra vacía es el neutro y es asociativa. Pero no podemos definir a lo loco que $aa^{-1}=\empty$, sino que debemos definir unaon de relación equivalencia: decimos que $w_1aa^{-1}w_2\sim w_1w_2$ para cualesquiera dos palabras $w_1,w_2$. Por álgebra, podemos encontraínr la mínima relación de equivalencia generada por esas relaciones de equivalencia para cualquier letra $a\in S$. Bueno ya, tenemos
$$
P_S/\sim{}\quad:=F_S
$$
**Proposición** $F_S$ es un grupo con la operación $[w_1][w_2]=[w_1w_2]$, cuyos inversos son $[s_1...s_n]^{-1}=[s_n^{-1}...s_1^{-1}]$.



##### Proposición. Propiedad universal del grupo libre

Sea $f:S\to G$ una función. Entonces, existe un único homomorfismo $\bar{f}:F_S\to F$ tal que $f=\bar{f}\circ i$, donde $i:S\xhookrightarrow{} F_S$.

*Demostración.* $\bar{f}[s_1...s_n]=[f(s_1)*...*f(s_n)]$. Tomando en cuenta asociar al inverso de $f(s_i)$ si $s_i\in\bar{S}$.



<u>Construcción del producto libre</u>

Tomemos una familia arbitraria de grupos $\{G_\alpha\}$. Definimos
$$
\bigstar G_\alpha=\{\text{Palabras en el alfabeto unión disjunta de los }G_\alpha\}
$$
con la condición de que para una palabra $g_1g_2...g_m$ con $g_i\in G_i$ no tenga dos elementos consecutivos en el mismo grupo. La operación será concatenación, con el detalle de considerar el producto de los elementos final e inicial si resultan estar en el mismo grupo.

**Proposición ** Hemos definido un grupo. (Demostración análoga que para grupos libres).

##### Proposición. Propiedad universal del producto libre

Sean $\varphi_\alpha:G_\alpha\to G$ homomorfismos de grupos. Entonces, existe un único homomorfismo $\varphi:\bigstar G_{\alpha}\to G$ tal que $\varphi_\alpha=\varphi\circ i$, donde $i:G_\alpha\xhookrightarrow{} \bigstar G_\alpha$.

*Demostración.* $\varphi(g_1...g_m)=\varphi_{\alpha_1}(g_1)*...*\varphi_{\alpha_m}(g_m)$.

## Espacios cubrientes

Resumen del tiempo perdido:

##### Espacios cubrientes

$Y$ es cubriente de $X$ si existe un mapeo $p:Y\to X$ tal que $\forall p\in X$, hay una vecindad abierta $U$ de $p$ tal que $p^{-1}(p)$ es la unión disjunta de abiertos en $Y$ y $p$ restringindo a cada uno de estos abiertos es un homeomorfismo.

**Levantamiento de funciones para cubrientes**. Una función $f:Y\to X$ se levanta a una función $\bar{f}:Y\to \bar{X}$ sobre el cubriente si y sólo si el grupo fundamental de $Y$ empujado con $\bar{f}_*$ está contenido en el grupo fundamental de $Y$ empujado con $p_*$. 

****

##### Unicidad del levantamiento de funciones

Si $\tilde{f}_1$ y $\tilde{f}_2$ son dos levantamientos de una función $f$ y coinciden en un punto y $Y$ es conexo, entonces son iguales.

**Prop.** Un espacio es simplemente conexo si y sólo si existe una única clase de homotopía de caminos que unen $x$ a $y$.

##### El cubriente universal

El cubriente universal de un espacio topológico conexo $X$ es un espacio simplemente conexo $Y$ junto con un mapeo cubriente $p:Y\to X$. El cubriente universal existe si y sólo si $X$ es conexo, localmente arco conexo y semilocalmente simplemente conexo.

##### El teorema de clasificación de cubrientes

$X$ con cubriente universal. Entonces para cualquier subgrupo $H$ del grupo fundamental de $X$ existe un cubriente $p_*:X_H\to X$ tal que el grupo fundamental de $X_H$ empujado con $p_*$ es igual a $H$.

##### El teorema de clasificación de cubrientes

Dos cubrientes cuyos espacios $\tilde{X}_1$ y $\tilde{X}_2$ son homeomorfos son "cubrientes isomorfos". Dos cubrientes son isomorfos si y sólo si los grupos fundamentales de cada cubriente empujado bajo $p_{i*}$ son iguales.

##### El teorema de clasificación de cubrientes bueno

La colección de espacios cubrientes punteados salvo isomorfismo está en correspondencia con los subgrupos del grupo fundamental.

##### El teorema de clasificación de cubrientes buenísimo

La colección de espacios cubrientes no punteados salvo isomorfismo está en correspondencia con los subgrupos del grupo fundamental salvo conjugación.

*El truco* está en que cambiar de punto base usando un camino en el cubriente universal es equivalente a conjugar los grupos fundamentales en cada punto empujados por $p_*$ mediante el lazo del camino del cambio de punto de base empujado por $p_*$.

**Definición.** Una transformación de cubierta es un automorfismo de cubierta que conmuta con la proyección. $G(\tilde{X})$ es el grupo de transformaciones de cubierta.

<img src="https://upload.wikimedia.org/wikipedia/commons/8/85/Diagramm_Decktrafo.png" alt="Diagramm Decktrafo.png" style="zoom:50%;" />

**Definición.** Un cubriente es normal si el grupo de transformaciones de cubierta actúa transitivamente en la fibra.

**Proposición.** Dos transformaciones de cubierta definidas en un espacio arco-conexo que coinciden en un punto son iguales.

**Teorema** Supongamos que $p:(\tilde{X},\tilde x_0)\to (X,x_0)$ es un cubriente, donde $\tilde X$ y $X$ son arcoconexos y $X$ además es localmente arcoconexo. Si $G=\pi_1(X,x_0)$ y $H=p_*\pi_1(\tilde{X},\tilde{x}_0)$, entonces

1. $p$ es normal $\iff$ $H\trianglelefteq G$
2. $G(\tilde{X})\cong N_G(H)/H$ donde $N_G(H):=\{g\in G|gHg^{-1}=H\}$
3. En part. si $p$ es normal $\implies G(\tilde{X})=G/H$
4. Y si $p$ es el cubriente universal $\implies G(\tilde{X})=G=\pi_1(X,x_0)$

*El truco* es usar el **teorema de clasificación de cubrientes**. Proposición 1.40 del Hatcher.

**Definición** Acción de grupo. Decimos que $G$ actúa en $X$ si hay un homomorfismo de grupos
$$
\begin{align*}
\varphi:G\to\text{Homeo}(X)\\
g\mapsto\varphi(g):X\to &X\\
x\mapsto&\varphi(g)(x)
\end{align*}
$$
de forma que

* $\varphi(g_1g_2)=\varphi(g_1)\varphi(g_2)$
* $(g_1g_2)x=g_1(g_2(x))$
* $\varphi(1_G)=id_X$

#### **Proposición** Si $p$ es normal entonces $\tilde{X}/G(\tilde{X})\cong X$.

+ Sí porque cada fibra tiene una sóla órbita.

**Definción** Sean $G$ un grupo, $Y$ un espacio topológico y $\varphi:G\to \text{Homeo}(Y)$ una acción. Decimos que $\varphi$ es una **acción cubriente** si se cumple cualquiera de las siguientes condiciones equivalentes:

+ $\forall y\in Y\exists U\subseteq Y$ vecindad de $y$ tal que $(g_1U\cap g_2U)\neq\empty\implies g_1=g_2$
+ $\forall y \in Y\exists U\subseteq Y$ vecindad de $y$ tal que $gU\cap U\neq\empty\implies g=1_G$.

##### **Proposición.** Acciones cubrientes.

Sea $G\curvearrowright Y$ una acción cubriente.

1. $p:Y\to Y/G$ es un cubriente normal.
2. Si $Y$ es arco-conexo entonces $G=G(Y)$
3. Si $Y$ es ___________________ y localmente arco conexo, entonces $G\cong \pi_1(Y/G,y_0)/p_*\pi_1(Y,\tilde{y}_0)$

##### Corolario. Acción cubriente con grupo fundamental trivial.

$\tilde{y}_0\in Y$ arco conexo y localmente arco-conexo con $\pi_1(Y,\tilde{y}_0)=1$ y $G\curvearrowright Y$ acción cubriente. Entonces $G(\tilde{Y})\cong\pi_1(Y/G,y_0)$.



## Homología

### Categoría de $R$-complejos de cadenas

1930's, después de Noether...

**Definición** Un $R$-complejo de cadenas es una sucesión de $R$-módulos y morfismos de la siguiente forma:
$$
(C_\bullet,\partial):=\quad...\xrightarrow[]{} C_p\xrightarrow[]{\partial_p} C_{p-1}\xrightarrow[]{\partial_{p-1}} C_{p-2}\to...
$$
tal que $\partial_{p-1}\partial_p=0$ para toda $p\in \mathbb{Z}$, que es equivalente a que $\text{img }\partial_p\subseteq\ker{\partial_{p-1}}$.

**Definición** Un morfismo de $R$-complejos de cadenas es $(C_\bullet{},\partial)\to(D_\bullet{},\delta)$ es una sucesión de $R$-homomorfismos $C_p\xrightarrow[]{f_p} D_p$ tal que
$$
\xymatrix{&...\ar[r]&C_{p+1}\ar[r]^{\partial_{p+1}}\ar[d]^{f_{p+1}}&C_{p}\ar[r]^{\partial_{p}}\ar[d]^{f_p}&C_{p-1}\ar[r]\ar[d]^{f_{p-1}}&...\\&...\ar[r]&D_{p+1}\ar[r]^{\delta_p}&D_{p}\ar[r]^{\delta_p}&D_{p-1}\ar[r]&...
}
$$
es decir $f_{p-1}\partial_p=\delta_pf_p$ para toda $p\in\mathbb{Z}$.

**Definición** Decimos que $(D_\bullet,\delta)$ es un subcomplejo de $(C_\bullet,\partial)$ si $D_p\leq C_p$ para toda $p\in\mathbb Z$ y $\partial|_{D_p}=\delta_p$. El cociente $(C_\bullet/D_\bullet,\partial)$ es el complejo de cadenas dado por 
$$
...\xrightarrow[]{} C_{p+1}/D_{p+1}\xrightarrow[]{\partial_{p+1}} C_{p}/D_p\xrightarrow[]{\partial_{p}} C_{p-1}/D_{p-1}\to...
$$
donde los mapeos frontera son de la forma $\partial_p/\delta_p([c])=[\partial_p(c)]$.

**Definición**

* Los elementos en $C_p$ se llaman **cadenas de dimensión $p$**.
* Los elementos en $\ker\partial_p:=Z_p$ se llaman **ciclos de dimensión $p$**.
* Los elementos en $\text{img }\partial_{p+1}:=F_p:=B_p$ se llaman **fronteras de dimensión $p$**.

Veamos una figura de dos ciclos homólogos:

<img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230528100750613.png" alt="image-20230528100750613" style="zoom:50%;" />

**Definición** El $p$-ésimo grupo de homogía de $(C_{\bullet{}},d)$ es
$$
H_p(C_{\dot{}}):=Z_p/B_p=\ker\partial_p/\text{img }\partial_{p+1}
$$

**Ejercicio**: Si $(C_\bullet{},\partial)\xrightarrow f(C'_\bullet{},\partial')$ es un homeomorfismo, entonces $f(Z_p)\subseteq Z'_p$ y $f(B_p)\subseteq B'_p$ así que la flecha inducida
$$
\begin{align*}
\bar f_p:H_p(C_\bullet{})\to & H_p(C_\bullet{})\\
a+B_p\mapsto& f_p(a)+B'_p
\end{align*}
$$
está bien definida.

Si además tenemos un segundo homomorfismo $(C'_\bullet,\partial')\xrightarrow{g}(C''_\bullet,\partial'')$, entonces $\overline{g\circ f}=\bar g\circ\bar f$. Y por último, $\overline{Id}_{C_p}=Id_{H_p(C)}$.

### Sucesiones exactas

**Definición** Decimos que la sucesión 
$$
...\xrightarrow[]{} C_p\xrightarrow[]{f_p} C_{p-1}\xrightarrow[]{f_{p-1}} C_{p-2}\to...
$$
es exacta en $C_p$ si  $\text{img }f_p=\ker{f_{p-1}}$. Y la sucesión es exacta si es exacta en todos los $C_p$. Esto sucede si y sólo si $H_p(C_\bullet{})=0$ $\forall p\in\mathbb{Z}$.

> El grupo de homología mide qué tan lejos está la sucesión de ser exacta.

> La sucesión puede ser "finita", o sea pueden haber muchos módulos que son cero.

**Proposición**

1. $0\to A\xrightarrow{\alpha}B$ es exacta si y sólo si $\ker{\alpha}=0$, es decir $\alpha $ es inyectiva.

2. $A\xrightarrow{\alpha}B\to 0$ es exacta si y sólo si $\text{img }{\alpha}=B$, es decir $\alpha $ es suprayectiva.

3. $0\to A\xrightarrow{\alpha}B\to 0$ es exacta si y sólo si $\alpha $ es un isomorfismo por los dos incisos anteriores.

4. $0\to A\xrightarrow{\alpha}B\xrightarrow{\beta} C\to0$ es exacta si y sólo si $\alpha$ es inyectiva, $\beta$ es suprayectiva y $\ker\beta=\text{img }\alpha$, de manera que $\beta$ induce un isomorfismo $C\cong B/\text{img }\alpha$.

   Si pensamos que $\alpha$ es la inclusión de $A$ como subgrupo de $B$, podemos escribir $C\cong B/A$ .

**Observación** (Primer teorema de isomorfismo) Si $M'\subseteq M$, entonces
$$
0\to M'\xhookrightarrow{}M\xtwoheadrightarrow{}M/M'\to0
$$
es una sucesión exacta.

### Homotopía

**Definición** Homotopía entre morfismos.
$$
\begin{align*}
(C_\dot{},\partial)\xrightarrow f&(C'_\dot{},\partial')
\end{align*}
$$
Decimos que $f$ y $g$ son homotópicas si existen homomorfismos
$$
\begin{align*}
C_p\xrightarrow {h_{p}} C_{p+1}
\end{align*}
$$
tales que $f_p-g_p=\partial'_{p+1}h_p+h_{p-1}\partial_p$.

**Proposición** Funciones homotópicas inducen el mismo mapeo en grupos de homología, o sea $f_{p*}=g_{p*}$.

### Lema de la serpiente

Dado el diagrama conmutativo de $R$-módulos con filas exactas en tinta negra,

<img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230329150336071.png" alt="image-20230329150336071" style="zoom:30%;" />

**Observación **$\text{coker}\partial=N/\text{img }\partial $ mide que tan lejos está un homomorfismo de ser suprayectivo.

### Teorema fundamental del álgebra homológica

Sea
$$
0\to A.\xrightarrow{i}B.\xrightarrow{j}C.\to0
$$
una sucesión exacta corta de complejos de cadenas, entonces existe **el homomorfismo de conexión**, que está dado $\forall p\in\mathbb{Z}$ por
$$
\partial_{*p}:H_p(C.)\to H_{p-1}(A.)
$$
tales que
$$
...\to H_p(C.)\xrightarrow{\delta_{*p+1}}H_p(A.)\xrightarrow{\phi_{*p}}H_p(B.)\xrightarrow{\psi_{*p}}H_p(C.)\xrightarrow{\delta_{*p-1}}H_{p-1}(A.)\xrightarrow{\phi_{*p-1}}H_{p-1}(B.)\to...
$$
es una sucesión exacta larga.

**Otra manera de ponerlo es que** dado el siguiente diagrama
$$
\xymatrix{
&&0\ar[d]&0\ar[d]&0\ar[d]&&\\
&...\ar[r]&A_{p+1}\ar[r]^{\partial_{p+1}}\ar[d]^{i_{p+1}}& A_p\ar[r]^{\partial_p}\ar[d]^{i_{p}}&A_{p-1}\ar[r]\ar[d]^{i_{p-1}}&...\\
&...\ar[r]&B_{p+1}\ar[r]^{\partial_{p+1}}\ar[d]^{j_{p+1}}&B_p\ar[r]^{\partial_p}\ar[d]^{j_{p}}&B_{p-1}\ar[r]\ar[d]^{j_{p-1}}&...\\
&...\ar[r]&C_{p+1}\ar[r]^{\partial_{p+1}}\ar[d]&C_p\ar[r]^{\partial_p}\ar[d]&C_{p-1}\ar[r]\ar[d]&...\\
&&0]&0&0&&\\}
$$
resulta que la sucesión
$$
...\to H_n(A)\xrightarrow{i_{*p}}H_n(B)\xrightarrow{j_{*p}}H_n(C)\xrightarrow{\partial_p}H_{p-1}(A)H_n(A)\xrightarrow{i_{*p-1}}H_n(B)\xrightarrow{j_{*p-1}}H_n(C)\to...
$$
es exacta larga.

### Naturalidad del homomorfismo de conexión

Dado el diagrama
$$
0\to A.\xrightarrow{\phi}B.\xrightarrow{\psi}C.\to0\\
0\to A'.\xrightarrow{\phi'}B'.\xrightarrow{\psi'}C'.\to0
$$
(Faltan las flechas $f:A.\to  A'.$, $g:B.\to B.'$ y $h:C.\to C.'$)

conmutativo de complejos de cadenas con filas exactas, podemos considerar todo en los grupos de homología más o menos así:
$$
...\to H_p(C.)\xrightarrow{\delta_{*p+1}}H_p(A.)\xrightarrow{\phi_{*p}}H_p(B.)\xrightarrow{\psi_{*p}}H_p(C.)\xrightarrow{\delta_{*p-1}}H_{p-1}(A.)\xrightarrow{\phi_{*p-1}}H_{p-1}(B.)\to...\\
...\to H_p(C'.)\xrightarrow{\delta'_{*p+1}}H_p(A'.)\xrightarrow{\phi'_{*p}}H_p(B'.)\xrightarrow{\psi'_{*p}}H_p(C'.)\xrightarrow{\delta'_{*p-1}}H_{p-1}(A'.)\xrightarrow{\phi'_{*p-1}}H_{p-1}(B'.)\to...
$$
(Faltan las flechas $f_{*p},g_{*p},h_{*p},f_{*p-1},g_{*p-1},h_{*p-1}$).

Entonces todos los cuadrados son conmutativos excepto la parte
$$
H_p(C.)\xrightarrow{\delta_{*p-1}}H_{p-1}(A.)\\
H_p(C'.)\xrightarrow{\delta'_{*p-1}}H_{p-1}(A'.)
$$
que es conmutativo y ese es este teorema.

**Demostración.** Diagrama 3D. El punto clave es definir la $y'$.$\qquad\square$

### Lema de los cinco

Consideremos el diagrama conmutativo de módulos con filas exactas
$$
M_5\xrightarrow{f_5} M_4\xrightarrow{f_4}M_3\xrightarrow{f_3}M_2\xrightarrow{f_2}M_1\\
N_5\xrightarrow{g_5} N_4\xrightarrow{g_4}N_3\xrightarrow{g_3}N_2\xrightarrow{g_2}N_1\\
$$
(Faltan las flechas $h_i:M_i\to N_i$).

Si $h_5,h_4,h_2$ y $h_1$ son isomorfismos, entonces $h_3$ también.



**Siguientes ideas**

**Objetivo:** Definir los grupos de homología para $n\geq0$, que son funtores de la forma
$$
H(X,R):\text{Top}\to\text{Ab}
$$
donde $X$ es un espacio topológico y $R$ es un anillo conmutativo con unidad.

### Homología simplicial

1. Un $n$**-simplejo** es la envolvente convexa en $\mathbb{R}^m$ de $n+1$ vértices tales que $v_1-v_0,...,v_n-v_0$ son linealmente independientes. Es equivalente a que $v_0,v_1,...,v_n$ sean afinmente independientes, es como un espacio lineal de dimensión $n$ con "origen" en $v_0$. Se denota por $[v_0,...,v_n]$.

1. El simplejo estándar es $\Delta^n=\{t_0,...,t_n\}\in\mathbb R^{n+1}|\sum_it_i=1\text{ y } t_i\geq0\forall i\}$. Y será denotado por $\Delta^n=[e_1,e_2,...,e_{n+1}]$.



<img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230412152511087.png" alt="image-20230412152511087" style="zoom:30%;" />

3. Un **$n$-simplejo singular** es una función $\sigma:\Delta^n\to X$.

4. Definimos el homomorfismo frontera
   $$
   \partial_n:C_n(X;R)\to C_{n-1}(X;R)\\
   \partial_n(\sigma)=\sum_{i=1}^{n+1}(-1)^i\sigma|_{[e_1,e_2,...,\hat{e}_i,...,e_{n+1}]}
   $$
   

Considerando que $[e_1,e_2,...,\hat{e}_i,...,e_{n+1}]\cong\Delta^{n-1}$.

7. La frontera de un $n$- simplejo es de hecho una de estas cadenitas de acuerdo a:

<img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230410161220380.png" alt="image-20230410161220380" style="zoom:40%;" />

**Lema** $\partial_{n-1}\circ\partial_n=0$.

**Definición** (Homología singular) Por el lema, podemos definir para cualquier espacio topológico $X$ un complejo de cadenas $C_\bullet(X)$ de la forma
$$
\quad...\xrightarrow[]{} C_p\xrightarrow[]{\partial_p} C_{p-1}\xrightarrow[]{\partial_{p-1}} C_{p-2}\to...\to C_1\xrightarrow[]{\partial_1}C_0\xrightarrow[]{\partial_0}0
$$


​		y con él la homología simplicial, cuyo n-ésimo grupo de homología es
$$
H_n(X;R):=H_n(C_\bullet(X))
$$

### Homología de las componentes arco conexas

**Ejercicio** Si $(C_\bullet^\alpha,\partial^\alpha)$ son una familia de complejos de cadenas de $R$-módulos, entonces
$$
...\to \bigoplus_{\alpha\in I}C_n^\alpha\xrightarrow{\bigoplus_\alpha\partial_n^\alpha}\bigoplus_{\alpha\in I}C_{n-1}^\alpha\xrightarrow{\bigoplus_\alpha\partial_{n-1}^\alpha}...
$$
es un complejo de cadenas. Además, la homología de este complejo está dada por
$$
H_n\Big(\bigoplus_{\alpha\in I}C_n^\alpha\Big)=\bigoplus_{\alpha\in I}H_n(C_n^\alpha)\qquad\forall n
$$
**Proposición.** Sea $X=\bigsqcup X_i$ la descomposición en componentes arco-conexas del espacio topológico $X$, entonces
$$
H_n(\bigsqcup X_i,R)\cong \bigoplus H_n(X_i,R)
$$

### El 0-ésimo grupo de homología

**Proposición** Para cualquier espacio $X$, $H_0(X;R)$ es un suma directa de copias de $R$, una por cada componente arcoconexa.

### Funtorialidad

**Definición. Morfismo de cadenas. **Dado un mapeo $f:X\to Y$, podemos considerar dos descomposiciones en complejos simpliciales de los espacios $X$ y $Y$ y consideramos los mapeos inducidos para cada $n$ dados por $f_\sharp:C_n(x)\to C_n(Y)$. Esto produce el diagrama conmutativo

<img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230410163822882.png" alt="image-20230410163822882" style="zoom:50%;" />

es decir resulta que $f_\sharp\partial=\partial f_\sharp$. Este resultado implica que $f_\sharp$ lleva ciclos en ciclos y fronteras en fronteras.

Así, tenemos un **homomorfismo inducido** bien definido en los grupos de homología de la forma $f_{*,n}=f_*:H_n(X)\to H_n(Y)$. Y además,

* $(fg)_\sharp=f_\sharp g_\sharp$
* $id_\sharp=id_{C_\bullet(X)}$
* $(fg)_*=f_*g_*$
* $id_*=id_{H_n(X)}$

### La homología de un punto

> Es casi imposible calcular la homología de un espacio directamente de la definición.

**Proposición** Si $X$ consiste de un sólo punto, entonces
$$
H_n(X;R)=\begin{cases}R\qquad\text{si   } n=0\\
0\qquad\text{si   } n\neq0
\end{cases}
$$

### Homología reducida

Considera
$$
\quad...\xrightarrow[]{} C_p\xrightarrow[]{\partial_p} C_{p-1}\xrightarrow[]{\partial_{p-1}} C_{p-2}\to...\to C_1\xrightarrow[]{\partial_1}C_0\xrightarrow[]{\partial_0}R\xrightarrow[]{\varepsilon}0
$$
donde $\varepsilon(\sum n_i\sigma_i)=\sum n_i$ es el **mapeo de aumentación**.

Va a resultar que $\tilde H_n(X;R)=H_n(X;R)$ para toda $n\geq 1$.



**Sobre la homología reducida del espacio que es un sólo punto**

Sabemos por la proposición de la homología de un punto que si $X=\{x\}$, entonces $H_0(X)=R$, es decir, $\ker{\partial_0}/\text{img }\partial_1=R$. Esto implica que la sucesión corta $0\to \text{img }\partial_1\xrightarrow[]{\partial_1}\ker\partial_0\xrightarrow[]{\partial_0}R\xrightarrow[]{\varepsilon}0$ es exacta.

*¿Cómo deducimos de aquí que $\tilde H_0(X;R)=0$?* Bueno resulta que como el espacio es un punto, $\partial_1=0$, así que de entrada $\text{img }\partial_1=0$. Luego, en realidad tenemos la sucesión exacta corta $0\to\ker\partial_0\xrightarrow[]{\partial_0}R\xrightarrow[]{\varepsilon}0$ que hace a $\partial_0$ un isomorfismo que en particular es inyectivo.

Como $\tilde H_0=\ker\partial_0/\text{img }\partial_1$, entonces $\tilde H_0(X;R)=0$.

**Y en general**

$H_0(X;R)=\tilde H_0(X;R)\oplus R$

### **Invarianza homotópica**

**Teorema** Si dos funciones $f,g:X\to Y$ son homotópicas, entonces inducen el mismo homomorfismo $f_*=g_*:H_n(X)\to H_n(Y)$.

**Corolario** Las funciones $f_*:H_n(X)\to H_n(Y)$ inducidas por una equivalencia homotópica $f:X\to Y$ son isomorfismos para toda $n$.

### Homología relativa

Sean $A\subseteq X$ espacios topológicos. Diremos que $(X,A)$ es una buena pareja. Notemos que $(C_\bullet(A))$ es un subcomplejo de $C_\bullet (X)$, así que podemos definir el complejo relativo
$$
C_\bullet(X,A)=C_\bullet(X)/C_\bullet(A)
$$
Y esto simplemente quiere decir que para toda $n$,
$$
C_n(X,A)=C_n(X)/C_n(A)
$$
de forma que las cadenas en $A$ se vuelven triviales.

Es claro que el n-ésimo operador frontera restringido a $C_n(A)$ se mapea a $C_{n-1}(A)$, (pues la frontera de una cadena en $A$ no podría salirse de $A$). Esto quiere decir que el mapeo frontera está bien definido en el cociente. 
$$
...\to C_{n+1}(X,A)\xrightarrow{\partial_{n+1}}C_n(X,A)\xrightarrow{\partial_n}C_{n-1}(X,A)\to...
$$
Esto induce la homología dada por
$$
H_n(X,A)=\ker\partial_n/\text{img }\partial_{n-1}
$$
**Ejemplo/Ejercicio** $H_n(X,\{x_0\})=H_n(X)$.

Ahora lo primero que pasa es que tenemos una sucesión exacta corta a la que aplicaremos el teorema fundamental del álgebra homológica:
$$
0\to C_\bullet(A)\xhookrightarrow{ i}C_\bullet(X)\xtwoheadrightarrow{j}C_\bullet(X,A)\to0
$$
Así que obtenemos la **sucesión exacta larga de la pareja**

$$
...\to H_n(A)\xrightarrow{i_{*n}}H_n(X)\xrightarrow{j_{*n}}H_n(X,A)\xrightarrow{\partial_n}H_{n-1}(A)\xrightarrow{i_{*n-1}}H_{n-1}(X)\xrightarrow{i_{*p-1}}...
$$
Como primera observación notemos que si los grupos de homología de la pareja $C_p(X,A)$ fueran triviales, autimáticamente tedríamos que el mapeo inducido por la inclusión sería un isomorfismo. De hecho, esto es un si y sólo si. Así, los grupos de homología miden qué tan diferentes son los grupos de homología de $A$ y los de $X$.

Finalmente agregamos el comentario de que aunque el mapeo $\partial$ que usamos para completar la sucesión exacta larga de la pareja viene del teorema fundamental del álgebra homológica, y al recordar la demostración del teorema nos damos cuenta de que este mapeo actúa exactamente como el operador frontera original de $X$.



**Teorema de escisión (p.119, 126)**

Sean $Z\subseteq A\subseteq X$ tales que la cerradura de $Z$ está contenida en el interior de $A$. Entonces
$$
(X-Z,A-Z)\hookrightarrow (X,A)
$$
induce un isomorfismo
$$
H_n(X-Z,A-Z)\to H_n(X,A)\qquad\forall n
$$
Equivalentemente, para subespacios $A,B\subseteq X$ cuyos interiores cubren a $X$, la inclusión
$$
(B,A\cap B)\hookrightarrow (X,A)
$$
induce un isomorfismo
$$
H_n(B,A\cap B)\to H_n(X,A)\qquad\forall n
$$
**Definición.** Decimos que $(X,A)$ es un buen par si $A$ es cerrado y es retracto fuerte por deformación de una vecindad en $X$.

* El arete hawaiiano no es un buen par porque cualquier vecindad del punto de pegado contiene un círculo entero, así que no se puede retraer por deformación.

**Teorema.** Sea $(X,A)$ un buen par, entonces
$$
q:(X,A)\to(X/A,A/A)
$$
induce isomorfismos para toda $n$ de la forma
$$
q_{*}:H_n(X,A)\to H_n(X/A,A/A)\cong \tilde{H}_n(X/A)
$$
donde la tilde denota la homología reducida.

*Demostración.* Se usa lema de los 5, invarianza homotópica, etc.

**Corolario.** Sea $(X,A)$ un buen par. Entonces tenemos la siguiente sucesión exacta larga:
$$
…\to\tilde H_n(A)\to\tilde H_n(X)\to \tilde H_n(X/A)\to \tilde H_{n-1}(A)\to\tilde H_{n-1}(X)\to \tilde H_{n-1}(X/A)\to…
$$
**Teorema**
$$
\tilde H_i(S^n;R)=\begin{cases}R\qquad\text{si   } n=i\\
0\qquad\text{si   } n\neq i
\end{cases}
$$
**Teorema** del punto fijo de Bruwer. Sean $n\geq2$ y  $f:D^n\to D^n$, entonces $f$ tiene un punto fijo.

### La sucesión de Mayer-Vietoris

Sea $X$ un espacio topológico y $A,B\subseteq X$ tales que $X=\text{int } A\cup \text{int } B$. Entonces tenemos la siguiente sucesión larga en homología reducida:
$$
…\to\tilde H_{n+1}(X)\to\tilde H_n(A\cap B)\to \tilde H_n(A)\oplus \tilde H_n(B)\to \tilde H_{n}(X)\to\tilde H_{n-1}(A\cap B)\to \tilde H_{n-1}(A)\oplus \tilde H_{n-1}(B)\to…
$$

**Ejemplo: el toro**

Veamos el toro $S^1\times S^1$ visto como en el examen, con $A=D^2$ y $B=S^1\vee S^1$, casi todos los grupos de homología se hacen cero (aquí hay que usar que la homología de la cuña es la suma de las homologías de los "cuñandos"), y que la homología de $S^1$ es cero cuando el subíndice es mayor o igual que 2. En fin, para $m>2$, $\tilde H_m(X)=0$.

Ahora para la parte que sí nos toca,
$$
…\to\tilde H_{2}(S^1)\to\tilde H_2(S^1)\oplus H_2(S^1)\to  \tilde H_{2}(X)\to\tilde H_{1}(S^1)\to \tilde H_{1}(S^1)\oplus \tilde H_{n-1}(S^1)\to \tilde H_1(X)\to 0…\\ \\
…\to\qquad0 \qquad\to\qquad0\qquad\to  \qquad?\qquad\to\qquad \mathbb Z\qquad\to \qquad\mathbb Z\oplus\mathbb Z\qquad\to \qquad?\qquad\to0…
$$
¿Qué falta para completa este diagrama?

**Proposición** Homología de cuñas. Consideremos $(X_\alpha,\{x_\alpha\})$ con $\alpha\in I$, tales que son buenas parejas. La cuña es
$$
\bigvee _{\alpha\in I}X_\alpha=\bigsqcup X_\alpha\Big/\bigsqcup\{x_\alpha\}
$$
Entonces
$$
\tilde H_n\Big(\bigvee_{\alpha\in I}X_\alpha\Big)\cong\bigoplus_{\alpha\in I}\tilde H_n(X_\alpha)
$$
*Demostración.* Primero notemos que  $(\sqcup X_\alpha,\sqcup\{X_\alpha\})$ es una buena pareja. Luego por el corolario del teorema de escisión tenemos para $n>0$, 
$$
…\to\tilde H_n\Big(\bigsqcup\{x_\alpha\}\Big)\to H_n\Big(\bigsqcup X_\alpha\Big)\to \tilde H_n\Big(\bigvee X_\alpha\Big)\to \tilde H_{n-1}\Big(\bigsqcup\{x_\alpha\}\Big)\to…
$$
Pero ahí en los extremos las homologías son la suma directa de homologías que son cero, por lo que se tiene el isomorfismo para grados positivos.

Ahora calculémoslo para $n=0$.
$$
…\to \tilde H_1\Big(\bigvee X_\alpha\Big)\to\tilde H_0\Big(\bigsqcup\{x_\alpha\}\Big)\to \tilde H_0\Big(\bigsqcup X_\alpha\Big)\to \tilde H_0\Big(\bigvee X_\alpha\Big)\to 0
$$

> La homología reducida es como la homología usual salvo en grado 0.

**Teorema** Sean $U\subseteq\mathbb R^n$ y $V\subseteq\mathbb R^m$ abiertos. Si $U$ y $V$ son homeomorfos, entonces $n=m$.

*Demostración.* Supongamos que $f:U\to V$ un homeomorfismo. Sea $x_0\in U$. Luego, $f:U\backslash \{x_0\}\to V\backslash \{f(x_0)\}$ es un homeomorfismo. Luego $f_*:H_n(U\backslash\{x_0\})\to H_n(V\backslash\{f(x_o)\})$ es un isomorfismo $\forall n$.

Además, tenemos una función de parejas $f:(U,U\backslash\{x_0\})\to (V,V\backslash\{f(x_0)\})$. Que induce dos sucesiones como las del corolario de escisión (creo), y usando el lema de los cinco obtengo que de hecho
$$
f_*:H_n(U,U\backslash\{x_0\})\to H_n(V,V\backslash\{f(x_o)\})
$$
 es también un isomorfismo.

Pero resulta que las homologías $H_n(U,U\backslash\{x_0\})$ son exactamente los de la esfera $S^n$ que ya conocemos.

> Una variedad $M^n$ es orientable $\iff$ $H_n(M^n,\mathbb Z)\cong\mathbb Z$

### Representantes de la homología de la esfera

En esta sección usaremos $R=\mathbb Z$.

**Proposición** $Id:\Delta^n\to\Delta^n$ representa un generador de $H_n(\Delta^n,\partial\Delta^n)$

*Demostración.* Por inducción en $n$. Si $n=0$, entonces $\Delta^0=\{e_0\}$ es un punto y su frontera es el vacío. Luego $H_0(\Delta^0,\partial\Delta^0)=H_0(\Delta^0)=\mathbb Z=\langle[e_0]\rangle$.

Ahora supongamos para $n$ y demostremos para $n+1$. Definamos $\Lambda$ como la unión de todas las $n-1$ caras en la frontera salvo alguna. Luego
$$
H_n(\Delta^n,\partial\Delta^n)\to^\delta H_n(\partial\Delta^n,\Lambda)\leftarrow^{\iota}H_{n-1}(\Delta^{n-1},\partial\Delta^{n-1})
$$
Luego como puedo retraer el simplejo en el $\Lambda$,
$$
H_{n-1}(\Delta^{n-1},\partial\Delta^{n-1})=0
$$
Así que (creo que) incluyendo el de en medio la primera ecuación en este anterior, obtenemos que $\delta$ es un isomorfismo.

Para checar $\iota$, 
$$
H_{n-1}(\Delta^{n},\Lambda)\cong H_{n-1}(\partial\Delta^n/\Lambda)\\
H_{n-1}(\Delta^{n-1},\partial\Delta^{n-1})\cong H_{n-1}(\partial\Delta^{n-1}/\partial\Delta^{n-1})
$$
Y los dos de la derecha deben ser isomorfos. Hay un cuadrado conmutativo abajo de la inclusión $\iota$. Luego $\iota_{n-1}$ genera por hipótesis inductiva…

### Generadores para la homología de la esfera

Hace dos observaciones básicas:

* $H_i(D^n,\partial D^n)\cong H_i(S^n)$
* Usaremos los homeomorfismos $(D^n,\partial D^n)\cong (\Delta ^n,\partial\Delta ^n)$

**Proposición** $\iota_n:\Delta^n\to\Delta^n$ la función identidad es un ciclo que genera a $H_n(\Delta^n,\partial\Delta^n)\cong\mathbb Z$.

Y luego

**Proposición** Pensando que que $S^n$ es $\Delta^n\bigcup_{\partial\Delta^n}\Delta^n$, y denotado cada copia de $\Delta^n$ con un subíndice, tenemos que $\Delta^n_1-\Delta^n_2$ es un generador de $H_n(S^n)$ para $n>0$.

### Grado de una función entre esferas

Consideremos $f:S^n\to S^n$, que induce una función $f_*:\tilde H_n(S^n)\cong \mathbb Z\to \tilde H_n(S^n)\cong\mathbb Z$ de manera que $f_*$ no tiene de otra que ser de la forma $f_*(n\alpha)=dn\alpha$.

**Definición** En la notación de arriba, el grado de $f$ es $d$.

**Proposición**

1. $\text{deg }Id=1$

   *Demostración* Por funtorialidad.

2. $f$ no suprayectiva entonces $\text{deg }(f)=0$.

   *Demostración* Como $f$ no es suprayectiva puedo escoger un punto $x\notin\text{img }f$. Entonces puedo pensar en el diagrama y su inducido.
   $$
   \xymatrix{
   &S^2-x  \ar@{^{(}->}[rd]\\
   &S^2\ar[u]^f\ar[r]_f& S^2
   }\qquad\qquad
   \xymatrix{
   &\tilde H_n(S^2-x)\cong 0  \ar@{^{(}->}[rd]\\
   &\tilde H_n(S^2)\ar[u]^{f_*}\ar[r]_{f_*}& \tilde H_n(S^2)
   }
   $$
   Y como el primero es conmutativo, el segundo también, y entonces $f_*$ es constante.

3. $f\simeq g$ entonces $\deg f=\deg g$

   *Demostración* Por invarianza homotópica las funciones inducidas son iguales.

4. $\deg(fg)=\deg(f)\deg(g)$
5. Si $f$ es una reflexión que intercambia los hemisferios, entonces $\deg(f)=-1$.
6. La función antipodal $-Id:S^n\to S^n$ tiene grado $(-1)^{n+1}$. Es decir,

$$
\deg (-Id)=\cases{1\qquad\text{ si }n\text{ es impar}\\
-1\qquad\text{ si }n\text{ es par}}
$$

7. Si $f$ no tiene puntos fijos, entonces $\deg (f)=(-1)^{n+1}$

#### Grado local

Siguiendo a Hatcher,

**Definición** Supongamos que $f:S^n\to S^n$ es tal que la imagen inversa de algún $y\in S^n$ consiste de una cantidad finita de puntos, digamos $f^{-1}(y)=\{x_1,...,x_m\}$. Tomemos una familia de abiertos disjuntos $U_1,...,U_m$ que contengan a cada $x_i$, y que vayan a dar a una vecindad $V$ de $y$ bajo $f$. Mediante un diagrama conmutativo, usando escisión y la sucesión exacta larga, Hatcher argumenta que el homomorfismo $f_*$ originalmente definido así:
$$
H_n(S^n,S^n-x_i)\xleftarrow{\cong}H_n(U_i,U_i-x_i)\xrightarrow{f_*}H_n(V,V-y)
$$
es de la forma $f_*:\Z \to \Z$, la multiplicación por un número que se llama el **grado local** de $f$ y se denota $\deg f|x_i$.

Y luego:

**Teorema** $\deg f=\sum_i\deg f|_{x_i}$

### Bola peluda

**Teorema** $S^n$ tiene un campo vectorial que no se anula en ningún punto $\iff$ $n$ es impar.

### Acciones libres en la esfera

**Proposición** El único grupo que puede actuar libremente (sin puntos fijos) en una esfera de dimensión par es $\mathbb Z_2$.

### Complejos CW

#### Definición

Establezcamos algo de notación

* $D^n=\{x\in\mathbb R^n:|x|\leq1\}$ es el $n$-disco cerrado.
* $S^n=\{x\in\mathbb R^n:|x|=1\}$ es la $n$-esfera.
* $e^n=\{x\in\mathbb R^n:|x|<1\}$ es la $n$-célula abierta o sólo la $n$-célula.

De tal forma que

* $\partial D^n=S^{n-1}$
* $D^n=e^n\cup S^{n-1}$ como conjuntos (no se usa la topología de la unión disjunta)
* Y bueno debe ser cierto que $e^0=\{pt\}$.

**Definición** Un espacio $X$ es un complejo $CW$ si se puede construir mediante el siguiente procedimiento:

1. Comenzamos con un espacio discreto $X^0$ que se llama el 0-esqueleto.

2. El $n$-esqueleto $X^n$ lo obtengo a partir del $n-1$-esqueleto $X^{n-1}$ pegando $n$-células $e^n_\alpha$ vía funciones $\varphi_\alpha:S^{n-1}\to X^{n-1}$. Formalmente tenemos el espacio
   $$
   X^n=X^{n-1}\bigsqcup_\alpha D_\alpha^n\Big/\sim\qquad\qquad x\sim\varphi_\alpha(x)\quad\text{ si }\quad x\in\partial D^n_\alpha
   $$

   > Realmente es tomar puntos y unir líneas entre ellos, y luego pegar puntos o líneas con discos, etc...

3. Podríamos terminar en una cantidad finita de pasos, digamos $m$, y obtenemos que $X=X^m$, pero también puedo continuar pegando células de dimensión arbitrariamente grande y obtenemos $X=\bigcup_n X^n$. En este caso $X$ tiene la topología débil: $X\subseteq X^n$ es abierto (cerrado) $\iff A\cap X^n$ es abierto (cerrado) $\forall n$.

**Definición** Si $X=X^n$ para algún $n\in\mathbb N$, decimos que $X$ es de dimensión finita y definimos la dimensión de $X$ como la dimensión de la célula más grande que adjunté. Formalmente, $\dim X=\min \{n:X^n=X\}$.

#### Ejemplos

* Los 0-complejos CW son gráficas.

* $S^n$ es un complejo CW.

* Los espacios proyectivos
   $$
   \begin{align*}
   \mathbb RP^n&=\mathbb R^{n+1}-\{0\}/x\sim\lambda x,\qquad\lambda\in\mathbb R\\
   &=S^n/x\sim-x\\
   &=D^n/x\sim-x,\qquad x\in\partial D^n=S^{n-1}\\
   &=\mathbb RP^{n-1}\cup e^n\\
   &=\mathbb RP^{n-2}\cup e^{n-1}\cup e^n\\
   &=e^0\cup e^1\cup...\cup e^n
   \end{align*}
   $$
   donde las funciones de pegado son justamente las antipodales, que ya conocíamos por ser el cubriente universal.

* $\{0\}\cup \{\frac{1}{n}:n\in\mathbb N\}\subseteq\mathbb R\}\subseteq \mathbb R$ no es un complejo $CW$ porque (1) cualquier complejo de dimensión mayor que 1 no es numerable y (2) tiene que ser un espacio discreto y este no es discreto.

* El arete Hawaiiano tampoco. Tomamos los puntos medios de todas las 1-células que vamos a pegar, que es un conjunto discreto, y al proyectar al cociente ese conjunto discreto de pronto tiene un punto de acumulación. Esto no es posible. Aún así, hay un argumento por cubriente universal:

**Ejercicio ** Todo complejo $CW$ es semilocalmente simplemente conexo. Es decir, todo complejo $CW$ tiene cubriente universal.

**Definición** La función característica es $\Phi_\alpha$:
$$
\xymatrix{
&e^n_\alpha\ar[rd]\ar[d]_{\text{inclusión}}&X^{n-1}\sqcup D_\alpha^n\ar[d]^{\text{proyección al cociente}}\\
&D^n_\alpha\ar[ur]\ar[r]_{\Phi_\alpha}& X^n
}
$$
**Definición** Sea $X$ un complejo $CW$. Un subcomplejo $Z$ es un subespacio cerrado que además es unión de células de $X$.

**Observación** Para un subcomplejo $Z$,

* $Z\subseteq X$ es una buena pareja ($Z$ es retracto por deformación de una vecindad de $X$)
* $X/Z$ es un complejo $CW$.

**Observación** Muy importante. $X$ complejo $CW$. El cociente por el $n-1$ esqueleto es una cuña de esferas, tantas como células en el $n-1$ esqueleto. En símbolos, $X^n/X^{n-1}=\bigvee_{\alpha\in I_n}S^n$, donde $I_n$ es el conjunto que indexa las $n-1$-celdas.

#### Homología

**Lema** Sea $X$ un complejo $CW$. Entonces:

1. 
   $$
   H_k(X^n,X^{n-1})=\begin{cases}0\qquad\quad\qquad\text{si }k\neq0\\
   \bigoplus_{\alpha\in I_n}R\qquad \text{si } k=n
   \end{cases}
   $$
   *Demostración express* $H_k=\tilde H_k(X^n/X^{n-1})=\tilde H_k(\bigvee_{\alpha \in I_n}S^n)=\bigoplus_{\alpha\in I_n}H_k(S^n)$

2. $H_k(X^n)=0\qquad\forall k>n$

   Nuevamente, la homología, lo que aclance a ver la homología, lo ve solamente hasta la dimensión del espacio

3. La inclusión $X^n\hookrightarrow X$ induce un isomorfismo $H_k(X^n)\hookrightarrow H_k(X)\qquad k>n$.

   Aquí la idea es que adjuntar células de dimensión mayor que la homología que estamos calculando no cambia la homología. Es decir, para $n>k$ se tiene que $H_k(X\cup D^n)=H_k(X)$.

**Demostración**

Fijémonos en $(X^n,X^{n-1})$, hay una sucesión exacta corta de la pareja:
$$
H_{k+1}(X^n,X^{n-1})\to H_k(X^{n-1})\to H_k(X^n)\to H_k(X^n,X^{n-1})
$$
Usando el inciso 1, si $k\neq n,n-1$ entonces $H_k(X^{n-1})\cong H_k(X^n)$.

Bueno para demostrar (2), justamente tenemos $k>n$ y entonces resultará, fijando $k$ y bajando uno por uno, $H_k(X^n)\cong H_k(X^0)$ que es un espacio discreto y la homología de grado mayor que cero en espacios discretos es cero. Terminamos el inciso (2).

Para (3), si $k<n<n+1<n+2<...$, simplemente tenemos que
$$
H_k(X^n)\cong H_k(X^{n+1})\cong...\cong H_k(X^{n+m})
$$
y si pedimos que $X$ sea de dimensiónó finita entonces terminaremos en algún punto y listo. El caso de dimensión infinita queda para el futuro. $\qquad\square$



**Definición** Tomemos 
$$
\xymatrix{
&&H_{n-1}(X^{n-1}) \ar[rd]^{j_{n-1}}\\
& H_{n}(X^n,X^{n-1})\ar[ru]^{\partial_n}\ar[rr]^-{d_n}&& H_{n-1}(X^{n-1},X^{n-2})\ar[rd]_{\partial_{n-1}}\ar[rr]^-{d_{n-1}}&&H_{n-2}(X^{n-2},H^{n-3})\\
&&&&H_{n-2}(X^{n-2})\ar[ru]_{j_{n-2}}
}
$$
Y luego resultará que las flechas horizontales son un complejo de cadenas, es decir, con los triangulitos definimos la diferencial $d$ y resulta que
$$
d_{n+1}d_n=0
$$
así podemos bautizar $C_\bullet^{CW}(X,R)$. Y ahora podemos definir la homología celular:
$$
H^{CW}_n(X;R)=H_n(C_\bullet^{CW}(X))
$$


**Teorema**
$$
H_n^{CW}(X;R)\cong H_n(X;R)\qquad\forall n\geq0
$$

> El primero depende de la estructura celular del espacio $X$, pero el segundo no. Así, la homología de un complejo $CW$ es independiente de la estructura celular.

**Observación** Estos grupos $H_n(X^n,X^{n-1})$ son las sumas directas de $R$, uno por cada n-celula de $X$ ie $\bigoplus_{n-\text{células de }X}R=\{\sum r_\alpha e^n_\alpha|e^n_\alpha \text{ es una }n\text{-célula }r_\alpha\in R\}$.

Bueno, ahora tratemos de entender cómo es $d$. Consideremoe sl siguiente diagrama:
$$
\xymatrix{& S^{n-1}_\alpha\ar[r]^{\varphi_\alpha}\ar@{..>}[d]^{\varphi_{\alpha\beta}}& X^{n-1}\ar[d]\\
& S^{n-1}_\beta & \bigvee_{\gamma\in I_n}S^{n-1}_\gamma=X^{n-1}/X^{n-2}\ar[l]}
$$
Ésta función que descubrimos $\varphi_{\alpha\beta}$ es una función entre esferas que tiene un grado $d_{\alpha\beta}$.

##### Ejemplos

**Teorema** Para $n\geq 2$, la diferencial $d_n$ manda $e^{n}_\alpha\mapsto\sum d_{\alpha\beta}e^{n-1}_\beta$.

**Ejemplo** Calculamos de dos maneras distintas la homología de $X=\bigvee_{\alpha\in I}S_\alpha^1$, por un lado usando directamente que $H_0(X)=R$ y otro usando el teorema anterior. Para el teorema anterior, descubrimos que para como sólo hay una 0-célula, para cualquier $\alpha$, $e_\alpha^1\mapsto x_0-x_0=0$, así que de hecho $d_1=0$. Resulta que $H_1=\bigoplus_IR$.

De hecho, esto es cierto en general:

**Lema** Si $X$ es un complejo con una única 0-célula, entonces $d_1=0$.

**Ejemplo** El toro. Hemos visto que hay una descomposición del toro pegando los lados de un cuadrado. Eventualemente se descubre que $d_2=0$.

**Teorema (extra del curso)** Una superficie compacta y conexa sólo puede ser una esfera, un toro, una suma conexa de toros, el plano proyectivo o una suma conexa de planos proyectivos.

Las primeras tres son orientables y las últimas dos no lo son. 

**Ejemplo** El toro de género $g$. Resulta que el toro doble se puede ver como el cociente de un octágono identificando aristas. Y en general, el $g$-toro es el cociente de un $4g$-ágono. El resultado final es que $H_0(S_g)=\Z, H_1(S_g)=\Z^{2g}$ y $H_2(S_g)=\Z$.

**Ejemplo** El plano proyectivo. Aquí, $d_2=2$. $H_2(\R P^2)=0$ y $H_1(\R P^2)=\Z/2$.

> Esta clase de ejercicios vienen en los exámenes generales.

**Ejemplo** $\R P^n$. Recordemos la descomposición de $\R P^n$ como complejo $CW$: $\R P^n=e_0\cup e_1\cup...\cup e_n$. El diagrama de arriba se vuelve:
$$
\xymatrix{& S^{k-1}\ar[r]^{\varphi}\ar@{..>}[d]^{\bar\varphi}& \R P^{k-1}\ar[d]^q\\
& S^{k-1} & \R P^{k-1}/\R P^{k-2}\ar[l]}
$$
Las funciones de pegado $\varphi_\alpha$ son la proyección al cociente función antipodal en la esfera (el cubriente del plano proyectivo). Estas funciones son dos a dos, y esto hace que el hemisferio norte de $S^{k-1}$ se mapee homeomorfamente a $S^{k-1}$ menos un punto (a donde va a dar el hemisferio sur).

Ahora observemos que la funciones que obtenemos cuando restringimos $\bar\varphi$ a cada hemisferio difieren una de la otra por el mapeo antipodal. A la hora de calcular el grado, obtenemos la fórmula $\deg (q\varphi)=1+(-1)^k$ usando que de alguna forma, escogiendo una orientación, podemos hacer que estos mapeos tengan grado $\pm1$ (Hatcher usa lo del grado local).

En fin,
$$
\deg\bar\varphi=\cases{2\quad\text{si }k\text{ es par}\\0\quad\text{si }k\text{ es impar}}
$$
Esto genera la homología siguiente:
$$
0\to\Z\xrightarrow{0}\Z\xrightarrow{2}...\xrightarrow{2}\Z\xrightarrow{0}\Z\xrightarrow{2}\Z\xrightarrow{d_1=0}\Z\to0
$$
Para $\R P^3$, $H_1=\Z/2\Z$, $H_2=0$ y $H_3=\Z$.

**Ejemplo** (Primer ejemplo donde cambian las cosas si cambiamos de anillo). Tomemos $\R P^n$ y el anillo $R=\Q$.
$$
0\to\Q\xrightarrow{0}\Q\xrightarrow{2}...\xrightarrow{2}\Q\xrightarrow{0}\Q\xrightarrow{2}\Q\xrightarrow{d_1=0}\Q\to0
$$
Pero ahora la función multiplicar por 2 manda $\Q$ en todo $\Q$, algo que no pasaba con $\Z$. Esto hace que la homología sea trivial, es decir, $H_n(\R P^n,\Q)=0$ para toda $n\geq1$.

**Ejemplo** ¿Y si tomamos $R=\Z/2$? Multiplicar por 2 es la función 0, así que $H_m(\R P^n,\Z/2)=\Z/2$ para $0\leq m\leq n$.

#### Característica de Euler

Sea $Y$ un complejo $CW$ finito (con un número finito de células). De hecho esta propiedad es equivalente a que el espacio $Y$ sea compacto. Definimos la característica de Euler como
$$
\begin{align*}\chi(Y)&=(\#\text{ 0-células})-(\#\text{ 1-células})+(\#\text{ 2-células})-...\\
&=\sum_{i=0}^\infty(-1)^i(\#\text{ }i\text{-células})\in\Z\end{align*}
$$
**Ejemplos** Pensando en las estructuras celulares que hemos dado en ejemplos anteriores,

* $\chi(S^n)=\cases{0\qquad n\quad\text{ impar}\\2\qquad n\quad\text{ par}}$
* $\chi(\R P^n)=\cases{0\qquad n\quad\text{ impar}\\1\qquad n\quad\text{ par}}$
* $\chi(\bigvee_{i=0}^nS^1)=1-n$
* $\chi(S_g)=1-2g+1=2-2g$

Se nos antoja que la $\chi$ no dependa de la estructura celular. Esto es cierto, y además:

**Teorema** Sean $X,Y$ complejos $CW$-finitos Si $X\simeq Y$ entonces $\chi(X)=\chi(Y)$.

**Proposición** Sea $Y$ un complejo $CW$ finito. Entonces,
$$
\chi(Y)=\sum_{i=0}^\infty(-1)^i\text{ran }H_i(Y;\Z)
$$
Para entender qué es $\text{ran }H_i$, notemos que el complejo de cadenas está hecho por grupos abelianos finitamente generados, ya que $Y$ es finito. De hecho, la homología de $Y$ es una sucesión exacta de grupos finitos finitamente generados. Luego, por el teorema de clasificación de grupos abelianos finitamente generados podemos descomponer un grupo en una expresión de la forma
$$
A=\underbrace{\bigoplus_{i=1}^r\Z}_\text{libre de torsión}\oplus\underbrace{\text{finito}}_{\text{torsión}}
$$
donde $r=\text{ran}(A)$ es el rango del grupo. Éste es el número que aparece en la proposición.

**Ejercicio** Sea $0\to A\to B\to C\to 0$ una sucesión exacta de grupos abelianos finitamente generados. Entonces $\text{ran }B=\text{ran }A+\text{ran }C$.

Bueno, demostremos la proposición

*Demostración* Tomemos el complejo de cadenas
$$
0\to C_k\xrightarrow{d_k}C_{k-1}\xrightarrow{d_{k-1}}...\xrightarrow{d_2}C_1\xrightarrow{d_1}C_0\to0
$$
y recordemos que $Z_n=\ker d_n$ y $B_n=\text{img }d_{n+1}$ y $H_n=Z_n/B_n$. Sólo por eso tenemos las sucesiones exactas
$$
0\to Z_n\to C_n\to B_{n-1}\to 0\\
0\to B_n\to Z_n\to H_n\to 0
$$
Usando el ejercicio, tenemos que
$$
\text{ran }C_n=\text{ran }Z_n+\text{ran }B_{n-1}\\
\text{ran }Z_n=\text{ran }B_n+\text{ran }H_{n}
$$
Ahora primero por definición y luego usando lo anterior,
$$
\begin{align*}\chi(Y)=&\sum_{i=0}^\infty(-1)^i\text{ran }C_i\\
=&\sum_{i=0}^\infty(-1)^i\Big(\text{ran }B_i+\text{ran }H_i+\text{ran }B_{i-1}\Big)\\
=&\sum_{i=0}^\infty(-1)^i\text{ran }H_i\qquad\qquad\square
\end{align*}
$$
Y con eso se demuestra fácilmente el teorema.

### El homomorfismo de Hurewicz

Sea $G$ un grupo y sean $g,h\in G$. El conmutador de estos elementos es $[g,h]=ghg^{-1}h^{-1}$. Dos elementos conmutan si y sólo si el conmutador es trivial. El subgrupo derivado o subgrupo conmutador es:
$$
G'=\langle[g,h]|g,h\in G\rangle\leq G
$$
Ahora notemos que un homomorfismo de $G$ se restringe a un homomorfismo de $G'$. Es decir la restricción es un automorfismo de $G'$. Decimos que $G'$ es un **subgrupo característico**. Luego, esto implica que es un subgrupo normal así que hago el cociente, y resultará ser un grupo abeliano porque todo lo que no conmuta se identificó. Este grupo es $G^{\text{ab}}:=G/G'$ y se llama la **abelianización** de $G$.

**Observación** Al hacer esto con un grupo simple, cuyos subgrupos normales son él y el trivial, el cociente $G/G'$ es el grupo trivial. Pero bueno, en general la idea es producir un grupo abeliano con cualquier grupo.

**Proposición** Sean $G$ un grupo y $A$ un grupo abeliano. Si $\varphi:G\to A$ es un homomorfismo, entonces $\exists! \bar\varphi:G^\text{ab}\to A$ tal que 
$$
\xymatrix{G\ar[r]^{\varphi}\ar[dr]&A\\&G^\text{ab}\ar[u]_\varphi}
$$
conmuta.

**Definición** El homomorfismo de Hurewicz es
$$
\begin{align*}h:π_1(X,x_0)&\to H_1(X)\\
[f]&\mapsto[f]\end{align*}
$$
que está bien definido porque en efecto los lazos son ciclos (y no depende del representante).

De hecho,

**Teorema** Si $X$ es arco-conexo, $h$ es suprayectivo y además $\ker h=\big(π_1(X,x_0)\big)'$. Es decir, el abelianizado del grupo fundamental es isomorfo al primer grupo de homología de $X$.

*Demostración* Demostramos que $h$ es un homorfismo bien definido y suprayectivo. Nomás faltó ver una contención de lo del kernel.$\qquad\square$

**Corolarios**

* $\Z\cong\pi_1(S^1,x_0)\cong H_1(S^1)$
* $F_n\cong\pi_1(\bigvee_n S^1)\implies H_n(\bigvee_n S^1)\cong F_n^\text{ab}\cong\Z^n$
* También se puede deducir para el toro que $H_1(T)\cong \Z^2$.

### Grupos de homotopía superiores

Recordemos que el grupo fundamental quedó definido como
$$
\begin{align*}
π_1(X,x_0)=&\{f:I\to X:f(0)=f(1)=x_0\}\Big/\simeq\text{rel }0,1\\
=&\{f:(S^1,s_0)\to(X,x_0)\}\Big/\simeq\text{rel }s_0
\end{align*}
$$
En esta segunda expresión del grupo fundamental, podemos pensar que la operación del grupo está dada por una función definida en la cuña de dos círculos ya que debemos: (1) recorrer $S^1$ al doble de velocidad y luego (2) identificar el punto base con su antípoda.

Así, podemos definir para $n\geq2$
$$
π_n(X,x_0)=\{f:(S^n,s_0)\to (X,x_0)\}\Big/\simeq\text{rel }s_0
$$
donde la operación del grupo está definida en la cuña de dos esferas $n$-dimensionales.

**Proposición** Para todo $n\geq 2$ y $(X,x_0)$ espacio topológico punteado, $π_n(X,x_0)$ es abeliano.

**Observación** Cada elemento de $π_0(X,x_0)$ representa una componente arco-conexa de $X$. ¡Pero $π_0(X,x_0)$ no tiene estructura de grupo!

**Proposición** $π_n:\text{Top}^*\to\text{Grp}$ es un funtor para $n\geq1$. Es decir, está bien definido en objetos y flechas, y manda la identidad en la identidad y es asociativo.

**Proposición** Aquí también hay invarianza homotópica: si $\varphi,\psi:(X,x_0)\to(Y,y_0)$ son homotópicas, las inducidas en grupos de homotopía son la misma. En particular, si dos espacios son homotópicas vía una homotopía que preserva el punto base, entonces sus grupos de homotopía son el mismo.

El recíproco no es cierto, hay espacios con el mismo grupo de homotopía pero que no son equivalentemente homotópicos: $\R^2$ y $S^2$ tienen el mismo grupo fundamental pero su segundo grupo de homología es diferente.

También hay contraejemplos para algo parecido: espacios que tienen la misma homología pero distinto grupo fundamental, así que tampoco son equivalentemente homotópicos. $X$ que sea la cuña de círculos con sus discos adjuntos para que su grupo fundamental sea $A_5$. $Y$ que sea la cuña de tantas esferas como $m$ en la expresión $H_2(X)=\Z^m$.

Ahora, si pedimos que tengan el mismo grupo de homotopía y el mismo grupo de homología, ¿serán homotópicamente equivalentes?

**Teorema extra** (Whitehead) Sean $X$, $Y$ complejos $CW$. Supongamos que $f:X\to Y$ es tal que $f_*:π_n(X,x_0)\toπ_n(Y,y_0)$ es un isomorfismo para toda $n\geq0$. Entonces $f$ es una equivalencia homotópica.

De hecho sí hay espacios cuyos grupos de homotoía son isomorfos pero los espacios no son homotópicamente equivalentes, pero en estos casos el isomorfismo no está inducido por una función entre los espacios.

**Teorema** Sea $p:(\tilde X,\tilde x_0)\to(X,x_0)$ un cubriente entre espacios conexos. Entonces, $p_*:π_n(\tilde X,\tilde x_0)\toπ_n(X,x_0)$ es un isomorfismo para $n\geq2$.

*Demostración* Tomamos un lazo $f:S^n\to X$ y sabemos que hay un levantamiento. Eso prueba suprayectividad. Y para ver inyectividad, al tomar un lazo en el cubriente cuya proyección es homotópica a cero, podemos de hecho levantar la homotopía y obtenemos que el lazo arriba también es homotópico al constante.$\qquad\square$

**Ejemplo** Los grupos de homotopía del toro para $n\geq2$ son triviales por su cubriente universal, $\R^2$, que es contraible. En general, cualquier espacio que tenga un cubriente contraible tiene grupos de homotopía de orden superior triviales.



### Otras ideas de homología

Tomado de Debrunner, Helly-type theorems (...)

**Lema $\mathbf{B_n'}$ ** Sea $n\geq1$. Si $Y$ es una $n$-variedad, entonces $\tilde H_q(Y)=0$ para $q>n$; y además, $\tilde H_n(Y)\cong\Z$ o $\tilde H_n(Y)=0$ dependiendo de si $Y$ es compacta y orientable o no.



Veamos cómo Hatcher enuncia la primera parte:

**Teorema 3.26** Si $M$ es una $d$-variedad cerrada (compacta sin frontera) y conexa entonces $H_i(M;R)=0$ para $i>d$.

**Proposición 3.29** Si $M$ es una $d$-variedad no compacta y conexa entonces $H_i(M;R)=0$ para $i>d$.

