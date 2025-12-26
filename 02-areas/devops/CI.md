Es una práctica de desarrollo donde los miembros de un equipo integran su código frecuentemente, al menos una vez al día.

Cada integración se verifica mediante una construcción automatizada que incluye pruebas para detectar errores lo más rápido posible.
![[Pasted image 20250604113234.png]]
- Detección temprana de errores
- Mayor velocidad en el desarrollo
- Mejor calidad del software
- Reducción de riesgos en integraciones
- Feedback inmediato para los desarrolladores
- Escalabilidad en proyectos grandes

**Job:** Un **Job** es una unidad de trabajo que ejecuta una serie de Steps (pasos) en un mismo entorno (Runner).
```
jobs:
	build:
		runs-on: ubuntu-latest
		steps:
			- run: echo "Compiling proyect..."
	test:
		needs: build # Depends job 'build'
		runs-on: ubuntu-latest
		steps:
		- run: echo "Executing test..."
```
**Steps**: Son acciones individuales dentro de un Job (ejecutar un comando, instalar dependencias, etc).
```
steps:
	- name: Install Node.js
	uses: actions/setup-node@v3
	- name: Install dependencies
	run: npm install
```
**Runners**: Los Runners Máquinas (físicas o virtuales) que ejecutan los Jobs. Pueden ser:
- Auto Hospeados
- Proveídos por el servicio de ubuntu
```
jobs:
	deploy:
		runs-on: ubuntu-latest
```
**Triggers**: son eventos que inician la ejecución del workflow (ej: push, pull request, horario programado).
```
on:
	push:
		branches: [ main ]
	pull_request:
		branches: [ main ]
	schedule:
		- cron: '0 2 * *' #execute trigger at 2 AM
```

