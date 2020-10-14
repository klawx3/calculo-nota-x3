# Calculo nota 🧮

Para calcular la nota del alumno con niveles de exigencia, notas maximas, notas minimos y puntajes totales usar

## Notación matematica
**f(x)** representa la recta para puntajes bajo o igual a el nivel minimo

<img src="https://latex.codecogs.com/gif.latex?f(x)=\frac{x}{p*e-p}*(nap-nmin)+nmin" /> 

**g(x)** representa la recta para puntajes sobre el nivel minimo

<img src="https://latex.codecogs.com/gif.latex?g(x)=\frac{x-p*e}{p-p*e}*(nmax-nap)+nap" /> 
uso de cada una:

<img src="https://latex.codecogs.com/gif.latex?\text{si}x\eqslantless{p*e}\implies{f(x)}" /> 
<img src="https://latex.codecogs.com/gif.latex?\text{si}x>p*e\implies{g(x)}" /> 

### donde:

**x** = puntaje del alumno

**p** = puntaje total

**e** = exigencia => (e | 0 < e <= 1)

**nmax** = nota maxima}

**nmin** = nota minima

**nap** = nota aprovación

*nota para mejorar: factorizar expreciones*

# Algoritmo en Python 🐍
```python

class EscalaNota:
    #Variables a modificar
    nota_aprobacion = 4.0
    nota_minima = 1.0
    nota_max = 7.0
    puntaje = 100
    exigencia = 0.6

    def __init__(self,puntaje):
        self.puntaje = puntaje

    def f(self, x):
        return (x * (self.nota_aprobacion - self.nota_minima)) / \
            (self.puntaje * self.exigencia) + (self.nota_minima)

    def g(self,x):
        return (x - (self.puntaje * self.exigencia) ) / \
         (self.puntaje - (self.puntaje * self.exigencia)) * \
         (self.nota_max - self.nota_aprobacion) + self.nota_aprobacion

    def get_nota(self, x):
        if x > self.puntaje * self.exigencia:
            return self.g(x)
        return self.f(x)
    
puntaje_prueba = 10
puntaje_alumno = 6
alumno = EscalaNota(puntaje_prueba)
nota = alumno.get_nota(puntaje_alumno)
print("nota alumno:",nota)
```
*nota para mejorar: implementar constructor con variales opcionales*
	
>  Autor: [klawx3](https://github.com/klawx3)
