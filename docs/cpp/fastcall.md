---
title: __fastcall | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __fastcall_cpp
dev_langs:
- C++
helpviewer_keywords:
- __fastcall keyword [C++]
ms.assetid: bb5b9c8a-dfad-450c-9119-0ac2bc59544f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4d69c97294795ed2f3f0b2d82ec8caa4734fa1f7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="fastcall"></a>__fastcall
**Microsoft-spezifisch**  
  
 Die `__fastcall`-Aufrufkonvention gibt an, dass Argumente für Funktionen in Registern zu übergeben sind, sofern dies möglich ist. Diese Aufrufkonvention gilt nur für die x86-Architektur. Die folgende Liste zeigt die Implementierung dieser Aufrufkonvention.  
  
|Element|Implementierung|  
|-------------|--------------------|  
|Reihenfolge der Argumentübergabe|Die ersten beiden in der Argumentliste von links nach rechts gefundenen DWORD oder kleineren Argumente werden in ECX- und EDX-Registern übergeben. Alle anderen Argumente werden von rechts nach links an den Stapel übergeben.|  
|Stapelwartungszuständigkeit|Aufgerufene Funktion ruft die Argumente vom Stapel auf.|  
|Namensergänzungskonvention|Das @-Zeichen wird Namen vorangestellt. Ein @-Zeichen in der Parameterliste, gefolgt von der Anzahl von Bytes (in Dezimalangabe) wird an den Namen angefügt.|  
|Konvention zur Umwandlung von Groß- in Kleinbuchstaben und umgekehrt|Groß-/Kleinbuchstaben werden nicht umgewandelt.|  
  
> [!NOTE]
>  In zukünftigen Versionen werden von Compilern möglicherweise andere Register zum Speichern von Parametern verwendet werden.  
  
 Mithilfe der [/Gr](../build/reference/gd-gr-gv-gz-calling-convention.md) -Compileroption bewirkt, dass jede Funktion im Modul als Kompilieren `__fastcall` , wenn die Funktion mit einem in Konflikt stehenden Attribut deklariert ist, oder der Name der Funktion ist `main`.  
  
 Das Schlüsselwort `__fastcall` wird von Compilern angenommen und ignoriert, die auf ARM und x64-Architekturen abzielen. Auf einem x64-Chip werden konventionell die ersten vier Argumente, wenn möglich, in Registern übergeben, und zusätzliche Argumente werden auf den Stapel übergeben. Weitere Informationen finden Sie unter [Überblick X64 Aufrufkonventionen](../build/overview-of-x64-calling-conventions.md). Auf einem ARM-Chip werden bis zu vier Ganzzahl- und acht Gleitkommaargumente in Registern übergeben, und zusätzliche Argumente werden auf den Stapel übergeben.  
  
 Wenn die Funktion bei nicht statischen Klassenfunktionen abweichend definiert ist, muss der Aufrufkonventionsmodifizierer nicht in der abweichenden Definition angegeben werden. Das bedeutet, dass für nicht statische Membermethoden der Klasse zum Zeitpunkt der Definition die während der Deklaration angegebene Aufrufkonvention angenommen wird. Bei dieser Klassendefinition:  
  
```cpp  
struct CMyClass {  
   void __fastcall mymethod();  
};  
```  
  
 entspricht:  
  
```cpp  
void CMyClass::mymethod() { return; }  
```  
  
 entspricht:  
  
```cpp  
void __fastcall CMyClass::mymethod() { return; }  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Funktion `DeleteAggrWrapper` an Argumente in Registern übergeben:  
  
```cpp  
// Example of the __fastcall keyword  
#define FASTCALL    __fastcall  
  
void FASTCALL DeleteAggrWrapper(void* pWrapper);  
// Example of the __ fastcall keyword on function pointer  
typedef BOOL (__fastcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);  
```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Argumentübergabe und Benennungskonventionen](../cpp/argument-passing-and-naming-conventions.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)