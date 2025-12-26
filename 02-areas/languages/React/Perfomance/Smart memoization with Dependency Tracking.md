``` Javascript
import { memo, useMemo, useCallback, useState } from 'react';  
  
// ❌ Over-memoization can hurt performance  
const BadExample = memo(() => {  
	const [count, setCount] = useState(0);  
  
	// This creates a new function on every render anyway  
	const handleClick = () => setCount(c => c + 1);  
  
	return <button onClick={handleClick}>{count}</button>;  
});  
  
// ✅ Strategic memoization with proper dependencies  
const ExpensiveUserList = memo(({ users, searchTerm, sortBy }) => {  
	const filteredAndSortedUsers = useMemo(() => {  
		console.log('Expensive computation running...');  
  
		return users  
				.filter(user => user.name.toLowerCase().includes(searchTerm.toLowerCase()) ||  user.email.toLowerCase().includes(searchTerm.toLowerCase()))  
		.sort((a, b) => {  
		switch (sortBy) {  
			case 'name': return a.name.localeCompare(b.name);  
			case 'email': return a.email.localeCompare(b.email);  
			case 'date': return new Date(b.createdAt) - new Date(a.createdAt);  
			default: return 0;  
			}  
		});  
	}, [users, searchTerm, sortBy]); // Only recompute when these change  
  
	return (  
		<div>  
			{filteredAndSortedUsers.map(user => (  
				<UserCard key={user.id} user={user} />  
			))}  
		</div>  
	);  
});  
  
// Memoize child components that receive objects as props  
const UserCard = memo(({ user }) => {  
	return (  
		<div className="user-card">  
			<h3>{user.name}</h3>  
			<p>{user.email}</p>  
			<small>{new Date(user.createdAt).toLocaleDateString()}</small>  
		</div>  
		);  
	});
```