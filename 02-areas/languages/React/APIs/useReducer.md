Es un hook que permite manejar el estado de una forma centralizada, 

```typescript
function nameReducer(previousName: string, newName: string) {
	return newName
}

const initialNameValue = 'Joe'

function NameInput() {
	const [name, setName] = useReducer(nameReducer, initialNameValue)
	const handleChange = (event) => setName(event.currentTarget.value)
	return (
		<div>
			<label>
				Name: <input defaultValue={name} onChange={handleChange} />
			</label>
			<div>You typed: {name}</div>
		</div>
	)
}

```

```typescript

setChannel(newChannel)
setElmi(cagona)
setVicente(noooooo😩)

setTimeout(() => {

}, 1000)
```
