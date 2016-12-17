---
title: "__cdecl"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "__cdecl"
  - "__cdecl_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__cdecl-Schlüsselwort [C++]"
ms.assetid: 1ff1d03e-fb4e-4562-8be1-74f1ad6427f1
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "mblome"
manager: "ghogen"
---
# __cdecl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 `__cdecl` ist die Standardaufrufkonvention für C\- und C\+\+\-Programme.  Da der Stapel vom Aufrufer bereinigt wird, kann er **vararg**\-Funktionen ausführen.  Die `__cdecl`\-Aufrufkonvention erstellt größere ausführbare Dateien als [\_\_stdcall](../cpp/stdcall.md), da hier jeder Funktionsaufruf Stapelbereinigungscode enthalten muss.  Die folgende Liste zeigt die Implementierung dieser Aufrufkonvention.  
  
|Element|Implementierung|  
|-------------|---------------------|  
|Reihenfolge der Argumentübergabe|Von rechts nach links.|  
|Stapelwartungszuständigkeit|Aufgerufene Funktion ruft die Argumente vom Stapel auf.|  
|Namensergänzungskonvention|Der Unterstrich \(\_\) wird Namen vorangestellt, außer beim Exportieren von \_\_cdecl\-Funktionen, die eine C\-Bindung verwenden.|  
|Konvention zur Umwandlung von Groß\- in Kleinbuchstaben und umgekehrt|Groß\-\/Kleinbuchstaben werden nicht umgewandelt.|  
  
> [!NOTE]
>  Verwandte Informationen finden Sie unter [Ergänzte Namen](../build/reference/decorated-names.md).  
  
 Platzieren Sie den `__cdecl`\-Modifizierer vor einer Variablen oder einem Funktionsnamen.  Da C\-Benennungs\- und C\-Aufrufkonventionen die Standardeinstellung sind, müssen Sie in x86\-Code `__cdecl` nur verwenden, wenn Sie die Compileroption **\/Gv** \(vectorcall\), **\/Gz** \(stdcall\) oder **\/Gr** \(fastcall\) angegeben haben.  Mit der [\/Gd](../build/reference/gd-gr-gv-gz-calling-convention.md)\-Compileroption wird die `__cdecl`\-Aufrufkonvention erzwungen.  
  
 Auf ARM\- und x64\-Prozessoren wird `__cdecl` zwar vom Compiler akzeptiert, aber normalerweise ignoriert.  Gemäß der Konvention zu ARM und x64 werden Argumente in Register übergeben, wenn dies möglich ist, und darauf folgende Argumente werden auf den Stapel übergeben.  Verwenden Sie in x64\-Code `__cdecl`, um die Compileroption **\/Gv** zu überschreiben, und verwenden Sie die standardmäßige x64\-Aufrufkonvention.  
  
 Wenn die Funktion bei nicht statischen Klassenfunktionen abweichend definiert ist, muss der Aufrufkonventionsmodifizierer nicht in der abweichenden Definition angegeben werden.  Das bedeutet, dass für nicht statische Membermethoden der Klasse zum Zeitpunkt der Definition die während der Deklaration angegebene Aufrufkonvention angenommen wird.  Bei dieser Klassendefinition:  
  
```cpp  
struct CMyClass {  
   void __cdecl mymethod();  
};  
```  
  
 entspricht:  
  
```cpp  
void CMyClass::mymethod() { return; }  
```  
  
 folgendem:  
  
```cpp  
void __cdecl CMyClass::mymethod() { return; }  
```  
  
## Beispiel  
 Im folgenden Beispiel wird der Compiler angewiesen, C\-Namenskonventionen und C\-Aufrufkonventionen für die `system`\-Funktion zu verwenden.  
  
```cpp  
// Example of the __cdecl keyword on function  
int __cdecl system(const char *);  
// Example of the __cdecl keyword on function pointer  
typedef BOOL (__cdecl *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);  
```  
  
## Siehe auch  
 [Argumentübergabe und Benennungskonventionen](../cpp/argument-passing-and-naming-conventions.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)