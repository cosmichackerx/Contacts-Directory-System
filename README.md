# Contacts-Directory-System

```java
import java.util.HashMap;
import java.util.LinkedHashMap;
import java.util.List;
import java.util.Map;
import java.util.Set;
import java.util.TreeMap;

/**
 * This program demonstrates how to manage a Contacts Directory System
 * using a Map, and also compares it to List and Set.
 */
public class ContactsDirectory {

    public static void main(String[] args) {
        
        // --- 1. Create a Map using the Map interface reference ---
        // A Map stores key-value pairs, where keys are unique.
        System.out.println("--- 1. Using HashMap for Contacts Directory ---");
        Map<String, String> contacts = new HashMap<>();

        // --- 2. Add elements to the Map, including a duplicate key ---
        System.out.println("Adding contacts...");
        contacts.put("Alice", "123-456-7890");
        contacts.put("Bob", "987-654-3210");
        contacts.put("Charlie", "555-123-4567");
        // Adding a duplicate key "Alice". This will overwrite her old number.
        contacts.put("Alice", "111-222-3333");

        System.out.println("Current contacts: " + contacts);
        System.out.println();

        // --- 3. Check if a key exists ---
        System.out.println("--- 2. Checking if a Contact Exists ---");
        String nameToCheck = "Bob";
        if (contacts.containsKey(nameToCheck)) {
            System.out.println("Yes, " + nameToCheck + " is in the directory.");
        } else {
            System.out.println("No, " + nameToCheck + " is not in the directory.");
        }
        System.out.println();

        // --- 4. Check if a value exists ---
        System.out.println("--- 3. Checking if a Phone Number Exists ---");
        String numberToCheck = "987-654-3210";
        if (contacts.containsValue(numberToCheck)) {
            System.out.println("Yes, the number " + numberToCheck + " is in the directory.");
        } else {
            System.out.println("No, the number " + numberToCheck + " is not in the directory.");
        }
        System.out.println();

        // --- 5. Retrieve a value by key ---
        System.out.println("--- 4. Retrieving a Contact's Number ---");
        String contactToFind = "Alice";
        System.out.println(contactToFind + "'s phone number is: " + contacts.get(contactToFind));
        System.out.println();

        // --- 6. Remove an element by key ---
        System.out.println("--- 5. Removing a Contact ---");
        String contactToRemove = "Charlie";
        contacts.remove(contactToRemove);
        System.out.println("Removed " + contactToRemove + " from the directory.");
        System.out.println("Updated contacts: " + contacts);
        System.out.println();

        // --- 7. Remove all elements ---
        System.out.println("--- 6. Clearing the Directory ---");
        // Let's create a new map for this demonstration
        Map<String, String> tempContacts = new HashMap<>();
        tempContacts.put("Eve", "444-555-6666");
        tempContacts.put("Frank", "777-888-9999");
        System.out.println("Temporary contacts before clearing: " + tempContacts);
        tempContacts.clear();
        System.out.println("Temporary contacts after clearing: " + tempContacts);
        System.out.println();

        // --- 8. Display the size ---
        System.out.println("--- 7. Displaying the Size ---");
        System.out.println("Final number of unique contacts: " + contacts.size());
        System.out.println();

        // --- 9. Loop through the Map in three ways ---
        System.out.println("--- 8. Iterating Through the Map ---");
        System.out.println("a) Iterating over Keys (keySet()):");
        for (String name : contacts.keySet()) {
            System.out.println("Name: " + name);
        }
        System.out.println();

        System.out.println("b) Iterating over Values (values()):");
        for (String phoneNumber : contacts.values()) {
            System.out.println("Phone Number: " + phoneNumber);
        }
        System.out.println();

        System.out.println("c) Iterating over Key-Value Pairs (entrySet()):");
        for (Map.Entry<String, String> entry : contacts.entrySet()) {
            System.out.println("Name: " + entry.getKey() + ", Phone: " + entry.getValue());
        }
        System.out.println();

        // --- 10. Compare Map with Set and List ---
        System.out.println("--- 9. Map vs List vs Set Comparison ---");
        System.out.println("List: Order is maintained, allows duplicates.");
        List<String> phoneList = List.of("123", "456", "123");
        System.out.println("Example List: " + phoneList);

        System.out.println("Set: No duplicates, no guaranteed order.");
        Set<String> uniqueNumbers = Set.of("123", "456", "123");
        System.out.println("Example Set: " + uniqueNumbers);

        System.out.println("Map: Stores unique keys that map to values. No duplicates in keys.");
        // The contacts map already demonstrates this.
        System.out.println("Example Map: " + contacts);
        System.out.println();

        // --- 11. Use the var keyword for another Map ---
        System.out.println("--- 10. Using 'var' for App Settings Map ---");
        var appSettings = new HashMap<String, String>();
        appSettings.put("theme", "dark");
        appSettings.put("language", "English");
        System.out.println("App settings: " + appSettings);
        System.out.println();

        // --- 12. Demonstrate the Map Interface with different implementations ---
        System.out.println("--- 11. Map Implementations and Ordering ---");
        System.out.println("HashMap: No guaranteed order.");
        Map<String, String> hashMap = new HashMap<>();
        hashMap.put("Zebra", "Zoo");
        hashMap.put("Apple", "Fruit");
        hashMap.put("Dog", "Animal");
        System.out.println("HashMap: " + hashMap);
        System.out.println();

        System.out.println("LinkedHashMap: Maintains insertion order.");
        Map<String, String> linkedHashMap = new LinkedHashMap<>();
        linkedHashMap.put("Zebra", "Zoo");
        linkedHashMap.put("Apple", "Fruit");
        linkedHashMap.put("Dog", "Animal");
        System.out.println("LinkedHashMap: " + linkedHashMap);
        System.out.println();

        System.out.println("TreeMap: Sorts keys in natural order.");
        Map<String, String> treeMap = new TreeMap<>();
        treeMap.put("Zebra", "Zoo");
        treeMap.put("Apple", "Fruit");
        treeMap.put("Dog", "Animal");
        System.out.println("TreeMap: " + treeMap);
    }
}
```

---

# 📞 ContactsDirectory – Java Map & Collections Demo

This program demonstrates how to build and manage a **Contacts Directory System** in Java using the **`Map` interface** and its common implementations (`HashMap`, `LinkedHashMap`, `TreeMap`). It also compares `Map` with `List` and `Set` to highlight their differences.  

The project is designed as a **learning tool** for understanding how Java Collections handle **ordering, uniqueness, and key–value storage**.

---

## 🚀 Features Demonstrated

### 1. **Using a Map for a Contacts Directory**
- Stores contacts as **key–value pairs** (`Name → Phone Number`).  
- Keys must be **unique**; adding a duplicate key overwrites the old value.  

```java
Map<String, String> contacts = new HashMap<>();
contacts.put("Alice", "123-456-7890");
contacts.put("Bob", "987-654-3210");
contacts.put("Alice", "111-222-3333"); // overwrites Alice's old number
```

---

### 2. **Basic Map Operations**
- ✅ Add contacts  
- ✅ Check if a contact (key) exists  
- ✅ Check if a phone number (value) exists  
- ✅ Retrieve a number by name  
- ✅ Remove a contact  
- ✅ Clear all contacts  
- ✅ Display directory size  

---

### 3. **Iterating Through a Map**
- **Keys** (`keySet()`) → list all names  
- **Values** (`values()`) → list all phone numbers  
- **Entries** (`entrySet()`) → list name–number pairs  

---

### 4. **Comparing Map, List, and Set**
- **List** → Ordered, allows duplicates (e.g., `[123, 456, 123]`)  
- **Set** → Unique elements, no duplicates (e.g., `[123, 456]`)  
- **Map** → Unique keys, each maps to a value (e.g., `{Alice=111-222-3333, Bob=987-654-3210}`)  

---

### 5. **Using `var` for Type Inference**
Demonstrates Java’s `var` keyword for cleaner syntax:  

```java
var appSettings = new HashMap<String, String>();
appSettings.put("theme", "dark");
appSettings.put("language", "English");
```

---

### 6. **Different Map Implementations**
- **HashMap** → No guaranteed order  
- **LinkedHashMap** → Maintains insertion order  
- **TreeMap** → Sorts keys in natural (alphabetical) order  

**Example Output:**  
```
HashMap: {Dog=Animal, Zebra=Zoo, Apple=Fruit}
LinkedHashMap: {Zebra=Zoo, Apple=Fruit, Dog=Animal}
TreeMap: {Apple=Fruit, Dog=Animal, Zebra=Zoo}
```

---

## 📊 Summary Table

| Collection Type | Allows Duplicates? | Maintains Order? | Access Method |
|-----------------|--------------------|-----------------|---------------|
| **List**        | ✅ Yes             | ✅ Yes (insertion) | By Index      |
| **Set**         | ❌ No              | ❌ No (HashSet)   | By Value      |
| **Map**         | ❌ No (keys only)  | Depends on implementation | By Key |

---

## 🎯 Learning Outcomes
- Understand how **Maps** store and manage key–value pairs.  
- Learn the difference between **HashMap, LinkedHashMap, and TreeMap**.  
- Compare **Map, List, and Set** to choose the right collection for a problem.  
- Practice **CRUD operations** (Create, Read, Update, Delete) on collections.  
- Explore **iteration techniques** and **type inference (`var`)** in Java.  

---

👉 This program is ideal for beginners exploring the **Java Collections Framework** and for quick revision before coding interviews or academic projects.  

---
