---
title: __fastcall | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __fastcall
- __fastcall_cpp
dev_langs:
- C++
helpviewer_keywords:
- __fastcall keyword [C++]
ms.assetid: bb5b9c8a-dfad-450c-9119-0ac2bc59544f
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: da4644465cf5b4df0ec4477edc1871b0b8291134
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

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
