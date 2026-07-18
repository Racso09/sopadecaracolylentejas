# Cindy's Dating Simulator (16–17/7/2026)

## herramientas
- **la idea original** era usar raylib + C para garantizar control total y fluidez, pero como apenas sé programar, opté por algo más práctico. **godot 4.7** (última versión al momento) hay que ser honestos, cualquier compu correría lo que estoy por hacer y aparte estoy muy familiarizado con godot, así que es ideal para mi nivel. algo para añadir es que **nunca empecé ni terminé un juego (ni siquiera uno pequeño)** , y sé que esa es la recomendación para indies, pero bueno acá estoy.

## config
- el proyecto tiene una resolución de **320×240** que después se podrá escalar en los ajustes, **60 FPS**, y filtro **nearest** (prioricé el pixel art aunque después usaré otros estilos).
- de paso personalicé la interfaz de godot para sentirme más cómodo y que se vea más cool ya saben jeje.

---

## el main menu
- en vez de empezar con algo jugable, hice un **menú básico**. fue fácil y quedó intencionalmente simple, un label y un par de botones. de momento esa fue la escena principal del proyecto y más adelante en el desarrollo haré algo muchísimo más estético y ***fancy***.

![menu](https://github.com/user-attachments/assets/8d4cca6c-dd87-4dda-a8dc-f5c08b865404)

---

## splash
- después de hacer el menú quise hacer una intro con un logo animado para hacerla la escena principal. el editor de animaciones de godot es super intuitivo y fácil de aprender, es una herramienta muy potente y ya tuve un par de experiencia usandolo, el temita empezó cuando el jittering entró a molestar.

### *jittering*
- los assets **pixel art**, al rotarlos o moverlos, sufrían **jittering** (pérdida de pixel‑perfect). quería **fluidez**, no necesariamente píxeles perfectos. cambiar el filtro a **linear** suaviza feo, pero da fluidez. me quedé toda la madrugada buscando soluciones dentro de godot. a la mañana siguiente seguí probando varias cosas, ninguna funcionaba. algunas usaban shaders, pero por algún motivo no funcionaban (sigo sin saber por qué).

### solución
- afortunadamente buscando en youtube encontré este shader que esta vez si funcionaba [Smooth-Pixels de Slammaa](https://github.com/Slammaa/Smooth-Pixels). entonces configuré el proyecto en **linear** y apliqué el shader a cada sprite.
  - **NOTA**: el shader puede dejar bordes raros y se recomienda dejar un píxel extra alrededor de cada sprite en la hoja. de momento no hice eso ya que no tuve problemas.

### splash *de nuevo*
- está compuesta por un fondo de cuadrados de 8×8 y lo configuré como un tile que se repita y animarlo en diagonal. el logo tiene 2 frames que cambian por segundo (a reloj) y tiene unas rotaciónes. la cámara tiene zooms y rotaciones para que quede más piola. añadí un **modulate** para simular ese efecto azúl de las intros de sonic en genesis pero con mi propio toque.

### carpetas del proyecto
- estructura actual (puede que los sprites vayan en carpetas separadas, pero esta es la excepción porque hay pocos)

![carpetas](https://github.com/user-attachments/assets/d3cd5879-bfe5-4487-a1dd-2a328baf4b3e)

- **NOTA**: los shaders sí tienen su propia carpeta.

---

## conclusión
- todo funciona como quería. la escena splash se carga automáticamente al iniciar, con su animación completa (zoom, rotación, fade, etc.) y cambia al menú temporal. me siento **orgulloso** del resultado.

![captura final](https://github.com/user-attachments/assets/f3306d87-5f17-47c9-9354-2b73e0a4a089)


https://github.com/user-attachments/assets/ec1104a1-fac3-42ac-9625-37aecd357ee2


---

## lo que sigue
- hacer algo jugable (personajes, diálogos, etc.).
- si aparece el problema de bordes en los sprites, añadir el píxel extra.
