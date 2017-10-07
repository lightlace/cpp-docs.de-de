---
title: __cdecl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __cdecl_cpp
dev_langs:
- C++
helpviewer_keywords:
- __cdecl keyword [C++]
ms.assetid: 1ff1d03e-fb4e-4562-8be1-74f1ad6427f1
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 5216462ad00d332aec2d00eba78f5d84cdfd7c82
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="cdecl"></a>__cdecl
**Microsoft-spezifisch**  
  
 `__cdecl` ist die Standardaufrufkonvention für C- und C++-Programme. Da der Stapel vom Aufrufer bereinigt wird, können Sie tun **Vararg** Funktionen. Die `__cdecl` -Aufrufkonvention erstellt größere ausführbare Dateien als [__stdcall](../cpp/stdcall.md), da hier jeder Funktionsaufruf stapelbereinigungscode enthalten muss. Die folgende Liste zeigt die Implementierung dieser Aufrufkonvention.  
  
|Element|Implementierung|  
|-------------|--------------------|  
|Reihenfolge der Argumentübergabe|Von rechts nach links.|  
|Stapelwartungszuständigkeit|Aufgerufene Funktion ruft die Argumente vom Stapel auf.|  
|Namensergänzungskonvention|Namen, außer wenn Unterstrich (_) vorangestellt wird \__cdecl-Funktionen, die C-Bindung verwenden, werden exportiert.|  
|Konvention zur Umwandlung von Groß- in Kleinbuchstaben und umgekehrt|Groß-/Kleinbuchstaben werden nicht umgewandelt.|  
  
> [!NOTE]
>  Weitere Informationen finden Sie unter [ergänzte Namen](../build/reference/decorated-names.md).  
  
 Platzieren Sie den `__cdecl`-Modifizierer vor einer Variablen oder einem Funktionsnamen. Da der C-benennungs- und Aufrufkonventionen die Standardeinstellung sind nur dann Sie müssen verwenden `__cdecl` in X86 Code ist, wenn Sie angegeben haben die **/GV** (Vectorcall), **/GZ** (Stdcall) oder ** / Gr** (Fastcall)-Compileroption. Die [/GD](../build/reference/gd-gr-gv-gz-calling-convention.md) Compiler Option erzwingt die `__cdecl` Aufrufkonvention.  
  
 Auf ARM- und x64-Prozessoren wird `__cdecl` zwar vom Compiler akzeptiert, aber normalerweise ignoriert. Gemäß der Konvention zu ARM und x64 werden Argumente in Register übergeben, wenn dies möglich ist, und darauf folgende Argumente werden auf den Stapel übergeben. In X64 codieren, verwenden Sie `__cdecl` überschreiben die **/GV** -Compileroption und verwenden die standardmäßige X64-Aufrufkonvention.  
  
 Wenn die Funktion bei nicht statischen Klassenfunktionen abweichend definiert ist, muss der Aufrufkonventionsmodifizierer nicht in der abweichenden Definition angegeben werden. Das bedeutet, dass für nicht statische Membermethoden der Klasse zum Zeitpunkt der Definition die während der Deklaration angegebene Aufrufkonvention angenommen wird. Bei dieser Klassendefinition:  
  
```cpp  
struct CMyClass {  
   void __cdecl mymethod();  
};  
```  
  
 entspricht:  
  
```cpp  
void CMyClass::mymethod() { return; }  
```  
  
 entspricht:  
  
```cpp  
void __cdecl CMyClass::mymethod() { return; }  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der Compiler angewiesen, C-Namenskonventionen und C-Aufrufkonventionen für die `system`-Funktion zu verwenden.  
  
```cpp  
// Example of the __cdecl keyword on function  
int __cdecl system(const char *);  
// Example of the __cdecl keyword on function pointer  
typedef BOOL (__cdecl *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Argumentübergabe und Benennungskonventionen](../cpp/argument-passing-and-naming-conventions.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)
