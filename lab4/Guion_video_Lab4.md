# Guion del video - Laboratorio 4 (DermAlpes)

Duración objetivo: menos de 3 minutos (unas 388 palabras narradas, entre 2:35 y 2:50 a ritmo normal). El video está dirigido a DermAlpes y a un público no especializado, entonces se evitan términos técnicos o se explican con ejemplos. Cada bloque indica quién habla y qué mostrar en pantalla. Si se pasan del tiempo, lo primero que se puede recortar es el bloque 3.

**1. El problema (0:00 - 0:25)** · Juan Felipe
*En pantalla: una foto de dermatoscopio y la misma foto con el contorno de la lesión dibujado.*

"Hola, somos Juan Felipe Sáenz y Tomás Aguilera. DermAlpes recibe fotos de lesiones de piel tomadas en centros de salud pequeños, y un dermatólogo las revisa a distancia. Para ahorrarle tiempo, queremos que una herramienta marque automáticamente dónde está la lesión, para que el especialista pueda medirla. Ojo: la herramienta no diagnostica, solo delimita la lesión."

**2. Cómo funciona (0:25 - 1:05)** · Tomás
*En pantalla: la foto original, la foto con los grupos coloreados y la máscara en blanco y negro.*

"La herramienta no necesita fotos etiquetadas por médicos. Mira cada punto de la imagen, su color y su ubicación, y junta los puntos que se parecen en grupos. En casi todas las fotos salen dos grupos: la piel y algo más oscuro. Después aplica una regla sencilla para decidir cuál es la lesión: es la zona más oscura que la piel, ignorando lo que está pegado a los bordes de la foto, como las esquinas negras que deja el lente. Al final se queda con la mancha más grande y le rellena los huecos. El resultado es una máscara: blanco donde hay lesión, negro donde hay piel."

**3. Cómo lo probamos (1:05 - 1:25)** · Juan Felipe
*En pantalla: las 15 imágenes de ajuste y las 5 de prueba separadas.*

"Usamos 20 fotos públicas que ya tenían la lesión marcada por dermatólogos. Con 15 ajustamos el método y las otras 5 las guardamos para el final, sin mirarlas, para saber cómo le iría con fotos nuevas."

**4. Resultados (1:25 - 2:00)** · Tomás
*En pantalla: la figura de las 5 imágenes de prueba (original, máscara estimada y referencia).*

"En esas 5 fotos nuevas, el contorno de la herramienta coincidió con el del dermatólogo con un puntaje promedio de 0.88 sobre 1, casi igual que en las fotos de ajuste. Lo que marca como lesión casi siempre es lesión: acierta el 97%. Pero se le escapa una parte, en promedio cerca del 18% de la lesión, sobre todo en el borde. Por eso tiende a dibujarla un poco más pequeña de lo que es."

**5. Cuándo falla (2:00 - 2:30)** · Juan Felipe
*En pantalla: los casos ISIC_0000110 (lesión pálida), ISIC_0000123 (piel enrojecida) e ISIC_0000157 (vellos).*

"Falla más con lesiones pálidas o de borde difuso. En una de prueba marcó solo un 6% de la foto cuando la lesión ocupaba un 10%. También se confunde con cosas oscuras que no son lesión, como vellos, piel enrojecida o lesiones partidas en varias manchas."

**6. Precauciones (2:30 - 3:00)** · Tomás
*En pantalla: lista de recomendaciones.*

"Recomendamos tres cosas. Primero, el dermatólogo siempre debe ver la foto con el contorno encima y poder corregirlo, sobre todo antes de medir el tamaño. Segundo, todas las fotos que usamos eran de piel clara: en piel más oscura el contraste es menor y podría fallar mucho más, así que hay que probarla con pacientes y equipos de DermAlpes antes de usarla. Tercero, nunca usarla para diagnosticar. Gracias."
