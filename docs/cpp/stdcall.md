---
title: "__stdcall | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__stdcall_cpp"
  - "__stdcall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__stdcall-Schlüsselwort [C++]"
ms.assetid: e212594b-1827-4d07-9527-7d412b300df8
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# __stdcall
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Die `__stdcall`\-Aufrufkonvention wird zum Aufrufen von Win32\-API\-Funktionen verwendet.  Der Aufgerufene löscht den Stapel. Daher kann der Compiler **vararg**\-Funktionen `__cdecl` machen.  Für Funktionen, die diese Aufrufkonvention verwenden, ist ein Funktionsprototyp erforderlich.  
  
## Syntax  
  
```  
  
return-type __stdcall function-name[(argument-list)]  
```  
  
## Hinweise  
 Die folgende Liste zeigt die Implementierung dieser Aufrufkonvention.  
  
|Element|Implementierung|  
|-------------|---------------------|  
|Reihenfolge der Argumentübergabe|Von rechts nach links.|  
|Argumentübergabekonvention|Nach Wert, es sei denn, ein Zeiger oder ein Referenztyp wird übergeben.|  
|Stapelwartungszuständigkeit|Die aufgerufene Funktion nimmt die eigenen Argumente vom Stapel auf.|  
|Namensergänzungskonvention|Ein Unterstrich \(\_\) wird dem Namen vorangestellt.  Dem Namen folgt das @\-Zeichen, gefolgt von der Anzahl von Bytes \(als Dezimalzahl\) in der Argumentliste.  Daher wird die Funktion, die als `int func( int a, double b )` deklariert ist, wie folgt ergänzt: `_func@12`|  
|Konvention zur Umwandlung von Groß\- in Kleinbuchstaben und umgekehrt|Keine|  
  
 Die [\/Gz](../build/reference/gd-gr-gv-gz-calling-convention.md)\-Compileroption gibt `__stdcall` für alle Funktionen an, die nicht explizit mit einer anderen Aufrufkonvention deklariert wurden.  
  
 Funktionen, die mithilfe des `__stdcall`\-Modifizierers deklariert werden, geben Werte auf die gleiche Art und Weise zurück wie die Funktionen, die mit [\_\_cdecl](../cpp/cdecl.md) deklariert werden.  
  
 Auf ARM und x64\-Prozessoren wird `__stdcall` vom Compiler akzeptiert und ignoriert. Auf ARM und x64\-Architekturen werden Argumente konventionsgerecht möglichst in Registern und folgende Argumente auf dem Stapel übergeben.  
  
 Wenn die Funktion bei nicht statischen Klassenfunktionen abweichend definiert ist, muss der Aufrufkonventionsmodifizierer nicht in der abweichenden Definition angegeben werden.  Das bedeutet, dass für nicht statische Membermethoden der Klasse zum Zeitpunkt der Definition die während der Deklaration angegebene Aufrufkonvention angenommen wird.  Bei der Klassendefinition  
  
```cpp  
struct CMyClass {  
   void __stdcall mymethod();  
};  
```  
  
 this  
  
```cpp  
void CMyClass::mymethod() { return; }  
```  
  
 entspricht  
  
```cpp  
void __stdcall CMyClass::mymethod() { return; }  
```  
  
## Beispiel  
 Im folgenden Beispiel führt die Verwendung von \_\_**stdcall** in allen `WINAPI`\-Funktionstypen dazu, dass sie als Standardaufruf behandelt werden:  
  
```c  
// Example of the __stdcall keyword  
#define WINAPI __stdcall  
// Example of the __stdcall keyword on function pointer  
typedef BOOL (__stdcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);  
```  
  
## Siehe auch  
 [Argumentübergabe und Benennungskonventionen](../cpp/argument-passing-and-naming-conventions.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)