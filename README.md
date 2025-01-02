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



### **Four Ways to Create a `Date` Object**

### **1. Creating a Date Object Without Parameters**
When you create a `Date` object without parameters, it will represent the current date and time.  

```javascript
const currentDate = new Date();
console.log(currentDate); // Example output: 2025-01-02T08:30:15.123Z
```

This is useful when you want to get the current system date and time for logging or timestamping.


### **2. Creating a Date Object Using Milliseconds**
You can create a `Date` object by passing the number of milliseconds elapsed since **January 1, 1970, 00:00:00 UTC**.  

#### Example 1: With a specific number
```javascript
const dateFromMilliseconds = new Date(0);
console.log(dateFromMilliseconds); // Output: 1970-01-01T00:00:00.000Z
```

#### Example 2: Using a calculation
You can calculate the milliseconds by multiplying values:
- `1000 ms` = `1 second`
- `60 seconds` = `1 minute`
- `60 minutes` = `1 hour`
- `24 hours` = `1 day`

```javascript
const oneDayInMilliseconds = 1000 * 60 * 60 * 24;
const dateAfterOneDay = new Date(oneDayInMilliseconds);
console.log(dateAfterOneDay); // Output: 1970-01-02T00:00:00.000Z
```

This is useful when you're working with time calculations or need to measure time differences programmatically.


### **3. Creating a Date Object Using a String**
You can pass a date string in various formats to the `Date` constructor. Common formats include:

#### Example 1: ISO String (YYYY-MM-DD)
```javascript
const dateFromISO = new Date("2025-01-02");
console.log(dateFromISO); // Output: 2025-01-02T00:00:00.000Z
```

#### Example 2: Full Date and Time
```javascript
const dateFromFullString = new Date("January 2, 2025 15:30:00");
console.log(dateFromFullString); // Output: 2025-01-02T15:30:00.000Z
```

#### Example 3: Partial Strings (Browser-dependent behavior)
```javascript
const dateFromPartial = new Date("01/02/2025");
console.log(dateFromPartial); // Output: 2025-01-02T00:00:00.000Z
```

Use this method when you're parsing date strings from user input, APIs, or databases.



### **4. Creating a Date Object Using 7 Parameters**
You can specify the year, month, day, hours, minutes, seconds, and milliseconds explicitly:  

```javascript
const specificDate = new Date(2025, 0, 2, 15, 30, 0, 0);
console.log(specificDate); // Output: 2025-01-02T15:30:00.000Z
```

#### Explanation of Parameters
1. **Year** - A 4-digit year (e.g., `2025`).
2. **Month** - `0` for January, `1` for February, and so on. **Note:** Month is zero-based.
3. **Day** - Day of the month (1–31).
4. **Hours** - Hours (0–23).
5. **Minutes** - Minutes (0–59).
6. **Seconds** - Seconds (0–59).
7. **Milliseconds** - Milliseconds (0–999).

#### Example with Default Values
If you omit certain parameters, they default to zero.
```javascript
const dateWithDefaults = new Date(2025, 0, 2); 
console.log(dateWithDefaults); // Output: 2025-01-02T00:00:00.000Z
```

This is helpful when you need to create a specific date and time programmatically for precise scheduling or calculations.

---




### **What Do `get` and `set` Methods Do?**

The `get` and `set` methods are used to **read or modify specific parts of a date**. Think of them as tools to extract or change information about the date.

#### **`get` Methods** (Retrieve Information)
These methods return parts of the `Date` object.

1. **`getFullYear()`**
   - Retrieves the year.
   ```javascript
   const date = new Date();
   console.log(date.getFullYear()); 
   // Example output: 2025
   ```

2. **`getMonth()`**
   - Retrieves the month (0 for January, 11 for December).
   ```javascript
   console.log(date.getMonth()); 
   // Example output: 0 (January)
   ```

3. **`getDate()`**
   - Retrieves the day of the month (1–31).
   ```javascript
   console.log(date.getDate()); 
   // Example output: 2
   ```

4. **`getDay()`**
   - Retrieves the day of the week (0 for Sunday, 6 for Saturday).
   ```javascript
   console.log(date.getDay()); 
   // Example output: 4 (Thursday)
   ```

5. **`getHours()`, `getMinutes()`, `getSeconds()`**
   - Retrieves specific time components.
   ```javascript
   console.log(date.getHours());   // Example output: 6
   console.log(date.getMinutes()); // Example output: 30
   console.log(date.getSeconds()); // Example output: 15
   ```

---

#### **`set` Methods** (Modify Information)
These methods change specific parts of the `Date` object.

1. **`setFullYear(year)`**
   - Updates the year.
   ```javascript
   const date = new Date();
   date.setFullYear(2030);
   console.log(date); 
   // Example output: 2030-01-02T06:30:00.000Z
   ```

2. **`setMonth(month)`**
   - Updates the month (0-indexed).
   ```javascript
   date.setMonth(5); // June
   console.log(date); 
   // Example output: 2030-06-02T06:30:00.000Z
   ```

3. **`setDate(day)`**
   - Updates the day of the month.
   ```javascript
   date.setDate(15);
   console.log(date); 
   // Example output: 2030-06-15T06:30:00.000Z
   ```

4. **`setHours(hours)`, `setMinutes(minutes)`, `setSeconds(seconds)`**
   - Updates specific time components.
   ```javascript
   date.setHours(12);
   date.setMinutes(0);
   console.log(date); 
   // Example output: 2030-06-15T12:00:00.000Z
   ```

---

