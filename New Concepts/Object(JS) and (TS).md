# JavaScript Object 

JavaScript-ൽ **Object** എന്നത് ഏറ്റവും അടിസ്ഥാനപരമായ ഒരു **Data Structure** ആണ്. ലളിതമായി പറഞ്ഞാൽ, ഇത് **Key-Value pairs**-ന്റെ ഒരു ശേഖരമാണ്.
# Core Concept & Analogy

നിങ്ങളുടെ മൊബൈൽ ഫോൺ ഒരു ഉദാഹരണമായി എടുക്കാം. അതിനൊരു brand ഉണ്ട്, color ഉണ്ട്, അതുപോലെ ഫോൺ വിളിക്കാൻ ഒരു സംവിധാനവുമുണ്ട്.

- ഇവിടെ brand, color എന്നിവയാണ് **Properties** (അതായത്, ഫോണിനെക്കുറിച്ചുള്ള ഡാറ്റ).
    
      
    
- ഫോൺ വിളിക്കുക എന്ന ആക്ഷൻ ആണ് **Method** (അതായത്, ഫംഗ്ഷൻ).
    
      
    

ഒരു **Object**-ൽ ഡാറ്റ സൂക്ഷിക്കുന്നത് **Key-Value pairs** ആയിട്ടാണ്. ഇതിൽ **Key** എപ്പോഴും ഒരു **String** അല്ലെങ്കിൽ **Symbol** ആയിരിക്കും. എന്നാൽ **Value** എന്തും ആകാം—ഒരു **Number**, **String**, **Array**, മറ്റൊരു **Object**, അല്ലെങ്കിൽ ഒരു **Function**. ഒരു **Function**-നെ **Object**-ന്റെ ഉള്ളിൽ കൊടുത്താൽ അതിനെ നമ്മൾ **Method** എന്ന് വിളിക്കുന്നു.

### Under the Hood: Memory & Architecture

ഇനി ഇത് കമ്പ്യൂട്ടറിനുള്ളിൽ എങ്ങനെ പ്രവർത്തിക്കുന്നു എന്ന് നോക്കാം:

  
1. **Reference Types:** JavaScript-ൽ **Objects** എന്ന് പറയുന്നത് **Primitive types** (ഉദാഹരണത്തിന് സാധാരണ അക്കങ്ങളും അക്ഷരങ്ങളും) പോലെയല്ല. ഇവ **Reference types** ആണ്.
    
      
    
2. **Memory Heap:** നിങ്ങൾ ഒരു **Object** ക്രിയേറ്റ് ചെയ്യുമ്പോൾ, അതിലെ ഡാറ്റ കമ്പ്യൂട്ടറിന്റെ **Memory Heap**-ൽ ആണ് allocate ചെയ്യുന്നത്.
    
      
    
3. **Pointers:** ആ **Object**-നെ ഒരു **Variable**-ലേക്ക് അസൈൻ ചെയ്യുമ്പോൾ, ഡാറ്റ മുഴുവനായി ആ **Variable**-ൽ സൂക്ഷിക്കുന്നില്ല. പകരം, **Memory Heap**-ലുള്ള ആ ഡാറ്റയുടെ **Memory Address** (അല്ലെങ്കിൽ **Pointer**) മാത്രമാണ് **Variable**-ൽ സേവ് ചെയ്യപ്പെടുന്നത്.
    
      
    

ഇതുകൊണ്ട് ഒരു പ്രധാന പ്രത്യേകതയുണ്ട്. താഴെ പറയുന്നതുപോലെ നിങ്ങൾ ഒരു **Object** മറ്റൊരു **Variable**-ലേക്ക് അസൈൻ ചെയ്താൽ:

  
JavaScript

```
let dev1 = { name: "Midhun" };
let dev2 = dev1;
```

ഇവിടെ പുതിയൊരു ഡാറ്റ കോപ്പി ചെയ്യപ്പെടുന്നില്ല. പകരം ഒരേ **Memory Address**-ലേക്ക് രണ്ട് **Variables**-ഉം പോയിന്റ് ചെയ്യുന്നു. അതുകൊണ്ട് `dev2`-ൽ എന്തെങ്കിലും മാറ്റം വരുത്തിയാൽ `dev1`-ലും ആ മാറ്റം പ്രതിഫലിക്കും.


കൂടാതെ, **V8** പോലുള്ള **JavaScript Engines** ഈ **Objects**-നെ **Hash Tables** പോലെയോ അല്ലെങ്കിൽ **Hidden Classes** ഉപയോഗിച്ചോ ആണ് മെമ്മറിയിൽ മാനേജ് ചെയ്യുന്നത്. ഇത് **Properties** വളരെ വേഗത്തിൽ ആക്സസ് ചെയ്യാൻ (Lookups) സഹായിക്കുന്നു.

### Practical Example

JavaScript

```
const developer = {
    name: "Midhun",          // Property (String)
    stack: "MERN",           // Property (String)
    experienceMonths: 3,     // Property (Number)
    buildAPI: function() {   // Method
        console.log("Writing backend APIs...");
    }
};

// Accessing properties
console.log(developer.name); 
developer.buildAPI();
```

ചുരുക്കത്തിൽ, പരസ്പരം ബന്ധപ്പെട്ട ഡാറ്റയും ആ ഡാറ്റയിൽ പ്രവർത്തിക്കുന്ന ഫംഗ്ഷനുകളും ഒരുമിച്ച് ചേർത്ത് വെക്കാൻ ഉപയോഗിക്കുന്ന ഒരു കണ്ടെയ്നർ ആണ് **Object**. കമ്പ്യൂട്ടർ മെമ്മറിയിൽ ഇതൊരു **Reference type** ആയിട്ടാണ് പ്രവർത്തിക്കുന്നത്.


# TypeScript Object

TypeScript-ൽ ഒരു Object എന്നത് data-യും അതിനോട് ബന്ധപ്പെട്ട behaviors-ഉം (methods) ഒന്നിച്ചു സൂക്ഷിക്കാനുള്ള ഒരു ഡാറ്റാ സ്ട്രക്ചർ (Data Structure) ആണ്. അടിസ്ഥാനപരമായി ഇത് JavaScript-ലെ അതേ object തന്നെയാണ്, എന്നാൽ TypeScript ഇതിലേക്ക് ശക്തമായ Type Checking കൊണ്ടുവരുന്നു.


ഇത് എങ്ങനെയാണ് പ്രവർത്തിക്കുന്നത് എന്ന് താഴെ പറയുന്ന പ്രധാന കൺസെപ്റ്റുകളിലൂടെ മനസ്സിലാക്കാം:

### 1. Under the Hood: Memory & Reference

കമ്പ്യൂട്ടർ മെമ്മറിയിൽ (Memory) objects എങ്ങനെയാണ് പ്രവർത്തിക്കുന്നത് എന്ന് നോക്കാം. നിങ്ങൾ ഒരു object create ചെയ്യുമ്പോൾ, അതിന്റെ യഥാർത്ഥ ഡാറ്റ Memory-യിലെ **Heap** എന്ന ഭാഗത്താണ് സൂക്ഷിക്കപ്പെടുന്നത്. ഈ ഡാറ്റ ഇരിക്കുന്ന സ്ഥലത്തേക്കുള്ള ഒരു അഡ്രസ്സ് അല്ലെങ്കിൽ **Reference** (ഒരു pointer പോലെ) ആണ് **Stack memory**-യിലെ variable-ൽ സൂക്ഷിക്കുന്നത്.

അതുകൊണ്ടാണ് ഒരു object-നെ വേറൊരു variable-ലേക്ക് assign ചെയ്യുമ്പോൾ (Pass by Reference), ഡാറ്റ കോപ്പി ചെയ്യപ്പെടാതെ ഒരേ മെമ്മറി ലൊക്കേഷനിലേക്ക് (Memory Location) രണ്ടും പോയിന്റ് ചെയ്യുന്നത്.

### 2. Structural Typing (Duck Typing)

TypeScript objects-ന്റെ ഏറ്റവും പ്രധാനപ്പെട്ട കൺസെപ്റ്റ് ആണ് **Structural Typing**. അതായത്, TypeScript ഒരു object എങ്ങനെ ഉണ്ടായി എന്നല്ല നോക്കുന്നത്, മറിച്ച് അതിന്റെ രൂപം അഥവാ **Shape** എന്താണ് എന്നാണ് നോക്കുന്നത്. ഒരു object-ൽ ആവശ്യമായ എല്ലാ properties-ഉം ശരിയായ Types-ൽ ഉണ്ടെങ്കിൽ, TypeScript അതിനെ അംഗീകരിക്കും.

ഉദാഹരണത്തിന്, നിങ്ങളുടെ സിസ്റ്റത്തിൽ ഒരു കസ്റ്റമർ ലീഡിന്റെ (Lead) ഡാറ്റ കൈകാര്യം ചെയ്യുകയാണെന്ന് കരുതുക:

TypeScript

```
// ഇതൊരു Type Contract ആണ്
interface Lead {
    id: number;
    name: string;
    isConverted: boolean;
}

// ഇവിടെ TypeScript Shape പരിശോധിക്കുന്നു
let newLead: Lead = {
    id: 101,
    name: "John Doe",
    isConverted: false
};
```

ഇവിടെ `Lead` എന്ന **Interface** ആ object-ന്റെ കൃത്യമായ Shape എന്തായിരിക്കണം എന്ന് നിർവചിക്കുന്നു. നിങ്ങൾ ഒരു പുതിയ property (ഉദാഹരണത്തിന് `age`) ആഡ് ചെയ്യാനോ, ഉള്ള ഒരെണ്ണം ഒഴിവാക്കാനോ ശ്രമിച്ചാൽ **Compile-time**-ൽ തന്നെ TypeScript നിങ്ങൾക്ക് Error തരും.

### 3. Compile-time vs Runtime

TypeScript-ന്റെ ഒരു പ്രധാന സ്വഭാവം **Type Erasure** ആണ്. അതായത്, നിങ്ങൾ എഴുതിയ TypeScript കോഡ് Compile ചെയ്ത് JavaScript ആയി മാറുമ്പോൾ, മുകളിൽ കൊടുത്ത `interface` പോലുള്ള Type annotations എല്ലാം പൂർണ്ണമായും മാഞ്ഞുപോകും. 

**Runtime**-ൽ (ബ്രൗസറിലോ Node.js-ലോ കോഡ് റൺ ചെയ്യുമ്പോൾ) ഇത് സാധാരണ ഒരു JavaScript object മാത്രമായിരിക്കും. TypeScript-ന്റെ ഒരേയൊരു ലക്ഷ്യം ഡെവലപ്പർ കോഡ് എഴുതുന്ന സമയത്ത് (Compile-time) തന്നെ തെറ്റുകൾ കണ്ടുപിടിക്കുക എന്നത് മാത്രമാണ്.



**ചുരുക്കത്തിൽ:**

Memory-യുടെ അടിസ്ഥാനത്തിൽ നോക്കുമ്പോൾ ഒരു Object എന്നത് Reference വഴി ആക്സസ് ചെയ്യാവുന്ന ഒരു Heap allocation ആണ്. എന്നാൽ TypeScript അതിന് മുകളിൽ ഒരു Compile-time Contract വെക്കുന്നു. ഇത് വഴി ആ object-ന്റെ Shape എപ്പോഴും കൃത്യമായിരിക്കുമെന്ന് ഉറപ്പുവരുത്താൻ ഡെവലപ്പർക്ക് സാധിക്കുന്നു.

# How to solve large problems

------------------------

# How to handle when large data set of object In Js and TS

JS/TS-ൽ വലിയ ഒരു dataset (ഉദാഹരണത്തിന് ലക്ഷക്കണക്കിന് objects ഉള്ള ഒരു Array) handle ചെയ്യുമ്പോൾ പ്രധാനമായും രണ്ട് പ്രശ്നങ്ങളാണ് ഉണ്ടാകുക: ഒന്ന്, മെമ്മറി പരിധി കവിയുക (Memory Heap Overflow). രണ്ട്, ബ്രൗസറോ സെർവറോ നിശ്ചലമാകുക (Event Loop Block ആകുക).

  

ഈ പ്രശ്നങ്ങൾ ഒഴിവാക്കാനും അണ്ടർ-ദി-ഹുഡ് (under-the-hood) കാര്യക്ഷമത വർദ്ധിപ്പിക്കാനും താഴെ പറയുന്ന core CS strategies ഉപയോഗിക്കാം:

  

**1. Time Complexity കുറയ്ക്കാൻ Data Structures മാറ്റുക (Hash Maps)**

ഒരു വലിയ Array-ൽ നിന്നും ഒരു പ്രത്യേക object കണ്ടുപിടിക്കാൻ `find()` അല്ലെങ്കിൽ `filter()` ഉപയോഗിച്ചാൽ, അതിൻ്റെ Time Complexity `O(n)` ആണ്. അതായത്, 1 ലക്ഷം objects ഉണ്ടെങ്കിൽ എഞ്ചിൻ 1 ലക്ഷം തവണ loop ചെയ്യേണ്ടി വരാം.

  

- **പരിഹാരം:** ഡാറ്റ എളുപ്പത്തിൽ തിരയാൻ (Search & Lookup) `Map` അല്ലെങ്കിൽ Object dictionary ഉപയോഗിക്കുക. ഇതിൻ്റെ Time Complexity `O(1)` ആണ്. ഒരു Unique ID (ഉദാഹരണത്തിന് user ID) Key ആക്കി വച്ചാൽ, വലിയ loop ഇല്ലാതെ തന്നെ നേരിട്ട് ഡാറ്റ എടുക്കാൻ സാധിക്കും.
    
      
    

**2. Event Loop Block ആകാതിരിക്കാൻ Chunking ഉപയോഗിക്കുക**

JS ഒരു Single-threaded ഭാഷയാണ്. വലിയൊരു Array ഒറ്റയടിക്ക് process ചെയ്താൽ (ഉദാഹരണത്തിന് വലിയൊരു `forEach` അല്ലെങ്കിൽ `reduce`), Main Thread block ആകും. അപ്പോൾ user-ന് UI-ൽ ക്ലിക്ക് ചെയ്യാനോ scroll ചെയ്യാനോ കഴിയില്ല (UI Freeze).

  

- **പരിഹാരം:** വലിയ dataset-നെ ചെറിയ chunks ആയി തിരിക്കുക. `setTimeout`, `setInterval` അല്ലെങ്കിൽ `requestAnimationFrame` ഉപയോഗിച്ച് ഓരോ chunk-ഉം Asynchronous ആയി process ചെയ്യുക. ഇങ്ങനെ ചെയ്യുമ്പോൾ ഓരോ chunk കഴിയുമ്പോഴും Event Loop-ന് ഇടവേള ലഭിക്കുകയും, മറ്റ് tasks (click events, rendering) ചെയ്യാൻ സാധിക്കുകയും ചെയ്യും.
    
      
    

**3. Memory Management ഉം Garbage Collection ഉം (Streaming & Virtualization)**

Node.js-ൽ V8 engine-ന് ഒരു നിർദിഷ്ട Memory Heap limit ഉണ്ട്. ഒരു വലിയ JSON file ഒറ്റയടിക്ക് RAM-ലേക്ക് load ചെയ്താൽ Out of Memory error വന്ന് application crash ആകും.

  

- **Backend:** മുഴുവൻ ഡാറ്റയും ഒരുമിച്ച് load ചെയ്യുന്നതിന് പകരം Streams ഉപയോഗിക്കുക. Data ചെറിയ packets ആയി read ചെയ്ത് process ചെയ്ത ശേഷം Memory-യിൽ നിന്നും റിലീസ് ചെയ്യുക. ഉപയോഗം കഴിഞ്ഞ objects-നെ Garbage Collection വേഗത്തിൽ ക്ലീൻ ചെയ്യും.
    
      
    
- **Frontend:** UI-ൽ വലിയ ലിസ്റ്റ് കാണിക്കാൻ Virtualization (ഉദാഹരണത്തിന് React-ലെ Virtual DOM-ൽ) ഉപയോഗിക്കുക. സ്ക്രീനിൽ കാണുന്ന objects മാത്രം render ചെയ്യുക. ബാക്കിയുള്ളവ scroll ചെയ്യുമ്പോൾ മാത്രം memory-ലേക്ക് കൊണ്ടുവരിക.
    
      
    

**4. CPU-Intensive Tasks-ന് Web Workers ഉപയോഗിക്കുക**

വലിയ dataset-ൽ സങ്കീർണ്ണമായ sorting, filtering അല്ലെങ്കിൽ mathematical calculations ചെയ്യണമെങ്കിൽ, അത് Main Thread-ൽ ചെയ്യുന്നത് ഒഴിവാക്കണം.

  

- **പരിഹാരം:** Web Workers ഉപയോഗിച്ച് ഈ processing ഒരു Background Thread-ലേക്ക് മാറ്റുക. ഇതിലൂടെ Main Thread സ്വതന്ത്രമാകുകയും, processing കഴിഞ്ഞ ശേഷം മാത്രം റിസൾട്ട് Main Thread-ലേക്ക് അയച്ചു കൊടുക്കുകയും ചെയ്യാം.
    
      
    

ചുരുക്കത്തിൽ, വലിയ dataset കൈകാര്യം ചെയ്യുമ്പോൾ അനാവശ്യമായ `O(n)` iterations ഒഴിവാക്കാൻ കൃത്യമായ Data Structures (Array-ക്ക് പകരം Map) തിരഞ്ഞെടുക്കുക. ഒറ്റയടിക്ക് ഡാറ്റ ലോഡ് ചെയ്യാതെ Chunking അല്ലെങ്കിൽ Streaming വഴി Memory Heap-ഉം Event Loop-ഉം സ്വതന്ത്രമാക്കി നിർത്തുകയുമാണ് അണ്ടർ-ദി-ഹുഡ് ചെയ്യേണ്ടത്.