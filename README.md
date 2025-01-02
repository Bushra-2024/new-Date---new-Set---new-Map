# new Date- new Set - new Map

![image](https://github.com/user-attachments/assets/1a039eaa-6af5-4303-a7eb-304d38e10182)

# new Date
The `new Date()` is a way to create a date and time object in JavaScript. It gives you the current date and time or a specific one if you provide details.

The "1970" part refers to the **starting point** (called the Unix Epoch). Computers count time from **January 1, 1970**, and when you use `new Date()`, it calculates how much time has passed since then to give the correct date and time. 

Example:  
```javascript
const now = new Date(); // Gives the current date and time
console.log(now);
// Example output: 2025-01-02T06:30:00.000Z (current date and time)
```

If you want to convert between local and universal time (UTC), JavaScript has built-in methods like `toUTCString()` or `toLocaleString()`.
