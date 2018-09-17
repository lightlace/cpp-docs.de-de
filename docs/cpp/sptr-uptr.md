---
title: __sptr, __uptr | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __uptr_cpp
- __sptr_cpp
dev_langs:
- C++
helpviewer_keywords:
- __sptr modifier
- __uptr modifier
ms.assetid: c7f5f3b2-9106-4a0b-a6de-d1588ab153ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dc6625e9f9137bc6adbe10270ef7192d2f1672f0
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700855"
---
# <a name="sptr-uptr"></a>__sptr, __uptr
**Microsoft-spezifisch**

 Verwenden der **__sptr** oder **__uptr** Modifizierer für eine 32-Bit-Zeigerdeklaration, um anzugeben, wie der Compiler einen 32-Bit-Zeiger in einen 64-Bit-Zeiger konvertiert. Ein 32-Bit-Zeiger wird beispielsweise konvertiert, wenn er einer 64-Bit-Zeigervariablen zugewiesen oder auf einer 64-Bit-Plattform dereferenziert wird.  
  
 In der Microsoft-Dokumentation zur Unterstützung von 64-Bit-Plattformen wird das wichtigste Bit eines 32-Bit-Zeigers gelegentlich als signiertes Bit bezeichnet. Standardmäßig verwendet der Compiler eine Vorzeichenerweiterung, um einen 32-Bit-Zeiger in einen 64-Bit-Zeiger zu konvertieren. Das heißt, die unwichtigsten 32 Bits des 64-Bit-Zeigers werden auf den Wert des 32-Bit-Zeigers festgelegt, und die wichtigsten 32 Bits werden auf den Wert des signierten Bits des 32-Bit-Zeigers festgelegt. Diese Konvertierung ergibt korrekte Ergebnisse, wenn das signierte Bit 0 ist. Wenn das signierte Bit 1 ist, sind die Ergebnisse nicht korrekt. Beispielsweise ergibt die 32-Bit-Adresse "0x7FFFFFFF" die entsprechende 64-Bit-Adresse "0x000000007FFFFFFF", die 32-Bit-Adresse "0x80000000" wurde jedoch inkorrekt auf "0xFFFFFFFF80000000" geändert.  
  
 Die **__sptr**, bzw. der signierte Zeiger %(Dateiname) gibt an, dass eine zeigerkonvertierung die wichtigsten Bits eines 64-Bit-Zeigers auf das signierte Bit des 32-Bit-Zeigers festgelegt. Die **__uptr**, oder nicht signierte Zeiger %(Dateiname) gibt an, dass eine Konvertierung die wichtigsten Bits auf NULL festgelegt. Die folgenden Deklarationen sind die **__sptr** und **__uptr** Modifizierer, die mit zwei nicht qualifizierten Zeigern, die verwendet werden, mit zwei Zeiger qualifiziert die [__ptr32](../cpp/ptr32-ptr64.md) Typ, und die Funktion der Parameter.  
  
```cpp 
int * __sptr psp;  
int * __uptr pup;  
int * __ptr32 __sptr psp32;  
int * __ptr32 __uptr pup32;  
void MyFunction(char * __uptr __ptr32 myValue);  
```  
  
 Verwenden der **__sptr** und **__uptr** Modifizierer mit Zeigerdeklarationen. Verwenden Sie die in die Position des ein [zeigertypqualifizierers](../c-language/pointer-declarations.md), was bedeutet, dass den Modifizierer dem Sternchen nachgestellt muss. Sie können keine die Modifizierer mit [Zeiger auf Member](../cpp/pointers-to-members.md). Die Modifizierer beeinflussen nicht die Nichtzeigerdeklarationen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert die 32-Bit-Zeiger, mit denen die **__sptr** und **__uptr** Modifizierer, jeden 32-Bit-Zeiger einer 64-Bit-Zeigervariablen zugewiesen, und klicken Sie dann zeigt den hexadezimalen Wert der einzelnen 64 - Bit-Zeiger. Das Beispiel wird mit dem systemeigenen 64-Bit-Compiler kompiliert und auf einer 64-Bit-Plattform ausgeführt.  
  
```cpp  
// sptr_uptr.cpp  
// processor: x64  
#include "stdio.h"  
  
int main()  
{  
    void *        __ptr64 p64;  
    void *        __ptr32 p32d; //default signed pointer  
    void * __sptr __ptr32 p32s; //explicit signed pointer  
    void * __uptr __ptr32 p32u; //explicit unsigned pointer  
  
// Set the 32-bit pointers to a value whose sign bit is 1.  
    p32d = reinterpret_cast<void *>(0x87654321);  
    p32s = p32d;  
    p32u = p32d;  
  
// The printf() function automatically displays leading zeroes with each 32-bit pointer. These are unrelated   
// to the __sptr and __uptr modifiers.   
    printf("Display each 32-bit pointer (as an unsigned 64-bit pointer):\n");  
    printf("p32d:       %p\n", p32d);   
    printf("p32s:       %p\n", p32s);  
    printf("p32u:       %p\n", p32u);  
  
    printf("\nDisplay the 64-bit pointer created from each 32-bit pointer:\n");  
    p64 = p32d;   
    printf("p32d: p64 = %p\n", p64);  
    p64 = p32s;  
    printf("p32s: p64 = %p\n", p64);  
    p64 = p32u;  
    printf("p32u: p64 = %p\n", p64);  
    return 0;  
}  
```  
  
```Output  
Display each 32-bit pointer (as an unsigned 64-bit pointer):  
p32d:       0000000087654321  
p32s:       0000000087654321  
p32u:       0000000087654321  
  
Display the 64-bit pointer created from each 32-bit pointer:  
p32d: p64 = FFFFFFFF87654321  
p32s: p64 = FFFFFFFF87654321  
p32u: p64 = 0000000087654321  
```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft-spezifische Modifizierer](../cpp/microsoft-specific-modifiers.md)