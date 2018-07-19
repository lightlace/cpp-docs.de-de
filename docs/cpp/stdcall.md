---
title: __stdcall | Microsoft-Dokumentation
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
ms.openlocfilehash: 09efc905507d93bbb80b003f93b885d9d27fcb1d
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939844"
---
# <a name="stdcall"></a>__stdcall
**Microsoft-spezifisch**  
  
 Die **__stdcall** -Aufrufkonvention wird verwendet, um Win32-API-Funktionen aufrufen. Der aufgerufene entleert den Stapel, damit der Compiler stellt **Vararg** Funktionen **__cdecl**. Für Funktionen, die diese Aufrufkonvention verwenden, ist ein Funktionsprototyp erforderlich.  
  
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
  
 Die [/GZ](../build/reference/gd-gr-gv-gz-calling-convention.md) -Compileroption gibt **__stdcall** für alle Funktionen, die nicht explizit mit einer anderen Aufrufkonvention deklariert.  
  
 Funktionen, die mithilfe von deklariert die **__stdcall** Modifizierer zurückgegeben Werte die gleiche Weise wie Funktionen, die mithilfe von deklariert [__cdecl](../cpp/cdecl.md).  
  
 Auf ARM und X64 Prozessoren **__stdcall** akzeptiert und ignoriert der Compiler; auf ARM und X64 Architekturen, gemäß der Konvention werden Argumente konventionsgerecht möglichst in Registern übergeben, und nachfolgende Argumente werden auf dem Stapel übergeben.  
  
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
 Im folgenden Beispiel ist die Verwendung von __**Stdcall** führt alle `WINAPI` -Funktionstypen als Standardaufruf behandelt werden:  
  
```cpp  
// Example of the __stdcall keyword  
#define WINAPI __stdcall  
// Example of the __stdcall keyword on function pointer  
typedef BOOL (__stdcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Argumentübergabe und Benennungskonventionen](../cpp/argument-passing-and-naming-conventions.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)