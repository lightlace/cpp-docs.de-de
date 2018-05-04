---
title: __stdcall | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __stdcall_cpp
dev_langs:
- C++
helpviewer_keywords:
- __stdcall keyword [C++]
ms.assetid: e212594b-1827-4d07-9527-7d412b300df8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f018a87f7a73de6500294b0817263e6f847af8ad
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="stdcall"></a>__stdcall
**Microsoft-spezifisch**  
  
 Die `__stdcall`-Aufrufkonvention wird zum Aufrufen von Win32-API-Funktionen verwendet. Entleert der aufgerufene den Stapel, damit der Compiler stellt **Vararg** Funktionen `__cdecl`. Für Funktionen, die diese Aufrufkonvention verwenden, ist ein Funktionsprototyp erforderlich.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
return-type __stdcall function-name[(argument-list)]  
```  
  
## <a name="remarks"></a>Hinweise  
 Die folgende Liste zeigt die Implementierung dieser Aufrufkonvention.  
  
|Element|Implementierung|  
|-------------|--------------------|  
|Reihenfolge der Argumentübergabe|Von rechts nach links.|  
|Argumentübergabekonvention|Nach Wert, es sei denn, ein Zeiger oder ein Referenztyp wird übergeben.|  
|Stapelwartungszuständigkeit|Die aufgerufene Funktion nimmt die eigenen Argumente vom Stapel auf.|  
|Namensergänzungskonvention|Ein Unterstrich (_) wird dem Namen vorangestellt. Dem Namen folgt das @-Zeichen, gefolgt von der Anzahl von Bytes (als Dezimalzahl) in der Argumentliste. Daher wird die Funktion, die als `int func( int a, double b )` deklariert ist, wie folgt ergänzt: `_func@12`|  
|Konvention zur Umwandlung von Groß- in Kleinbuchstaben und umgekehrt|Keiner|  
  
 Die [/GZ](../build/reference/gd-gr-gv-gz-calling-convention.md) -Compileroption gibt `__stdcall` für alle Funktionen, die nicht explizit mit einer anderen Aufrufkonvention deklariert wurden.  
  
 Mit deklarierten Funktionen der `__stdcall` Modifizierer return Werte die gleiche Weise wie mit deklarierten Funktionen [__cdecl](../cpp/cdecl.md).  
  
 Auf ARM und x64-Prozessoren wird `__stdcall` vom Compiler akzeptiert und ignoriert. Auf ARM und x64-Architekturen werden Argumente konventionsgerecht möglichst in Registern und folgende Argumente auf dem Stapel übergeben.  
  
 Wenn die Funktion bei nicht statischen Klassenfunktionen abweichend definiert ist, muss der Aufrufkonventionsmodifizierer nicht in der abweichenden Definition angegeben werden. Das bedeutet, dass für nicht statische Membermethoden der Klasse zum Zeitpunkt der Definition die während der Deklaration angegebene Aufrufkonvention angenommen wird. Bei der Klassendefinition  
  
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
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel Verwendung von __**"stdcall"** führt alle `WINAPI` -Funktionstypen als Standardaufruf behandelt:  
  
```cpp  
// Example of the __stdcall keyword  
#define WINAPI __stdcall  
// Example of the __stdcall keyword on function pointer  
typedef BOOL (__stdcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Argumentübergabe und Benennungskonventionen](../cpp/argument-passing-and-naming-conventions.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)