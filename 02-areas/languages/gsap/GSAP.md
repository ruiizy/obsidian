Solo se debe animar **x** e **y**

ease son las animaciones de suavizado, el in, out o el inout es la acelaración de la animación.

Para determinar dependiendo de otras se utiliza timeline
```javascript
const tl = gsap.timeline({
	defaults: {
		duration: 2
	}
})

tl.to('.box.purple' {
 x: 100
})

tl.to('.box.yellow' {
 x: 100
}, "<") // Significa que se ejecute cuando acabe justo la anterior animación
```

Cada vez que se usa un plugin de gsap hay que registrarlo
```javascript
	gsap.registerPlugin(SplitText)
```
