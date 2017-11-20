---
title: __sptr __uptr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __uptr_cpp
- __sptr_cpp
dev_langs: C++
helpviewer_keywords:
- __sptr modifier
- __uptr modifier
ms.assetid: c7f5f3b2-9106-4a0b-a6de-d1588ab153ed
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0dd691c706fa9b80307971b7004ee1fbbccd7153
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="sptr-uptr"></a>__sptr, __uptr
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Verwenden Sie den `__sptr`- oder `__uptr`-Modifizierer in einer 32-Bit-Zeigerdeklaration, um anzugeben, wie der Compiler einen 32-Bit-Zeiger in einen 64-Bit-Zeiger konvertiert. Ein 32-Bit-Zeiger wird beispielsweise konvertiert, wenn er einer 64-Bit-Zeigervariablen zugewiesen oder auf einer 64-Bit-Plattform dereferenziert wird.  
  
 In der Microsoft-Dokumentation zur Unterstützung von 64-Bit-Plattformen wird das wichtigste Bit eines 32-Bit-Zeigers gelegentlich als signiertes Bit bezeichnet. Standardmäßig verwendet der Compiler eine Vorzeichenerweiterung, um einen 32-Bit-Zeiger in einen 64-Bit-Zeiger zu konvertieren. Das heißt, die unwichtigsten 32 Bits des 64-Bit-Zeigers werden auf den Wert des 32-Bit-Zeigers festgelegt, und die wichtigsten 32 Bits werden auf den Wert des signierten Bits des 32-Bit-Zeigers festgelegt. Diese Konvertierung ergibt korrekte Ergebnisse, wenn das signierte Bit 0 ist. Wenn das signierte Bit 1 ist, sind die Ergebnisse nicht korrekt. Beispielsweise ergibt die 32-Bit-Adresse "0x7FFFFFFF" die entsprechende 64-Bit-Adresse "0x000000007FFFFFFF", die 32-Bit-Adresse "0x80000000" wurde jedoch inkorrekt auf "0xFFFFFFFF80000000" geändert.  
  
 Der `__sptr`-Modifizierer bzw. der signierte Zeiger gibt an, dass durch eine Zeigerkonvertierung die wichtigsten Bits eines 64-Bit-Zeigers auf das signierte Bit des 32-Bit-Zeigers festgelegt werden. Der `__uptr`-Modifizierer bzw. der nicht signierte Zeiger gibt an, dass durch eine Konvertierung die wichtigsten Bits auf Null festgelegt werden. Die folgenden Deklarationen sind die `__sptr` und `__uptr` Modifizierern mit zwei nicht qualifizierten Zeigern verwendet zwei Zeiger qualifiziert, mit der [__ptr32](../cpp/ptr32-ptr64.md) Typ und einen Funktionsparameter.  
  
```  
int * __sptr psp;  
int * __uptr pup;  
int * __ptr32 __sptr psp32;  
int * __ptr32 __uptr pup32;  
void MyFunction(char * __uptr __ptr32 myValue);  
```  
  
 Verwenden Sie die `__sptr`- und `__uptr`-Modifizierer mit Zeigerdeklarationen. Verwenden Sie die Modifizierer an der Position einer [zeigertypqualifizierers](../c-language/pointer-declarations.md), dass der Modifizierer das Sternchen folgen muss. Sie können keine die Modifizierer mit [Zeiger auf Member](../cpp/pointers-to-members.md). Die Modifizierer beeinflussen nicht die Nichtzeigerdeklarationen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden 32-Bit-Zeiger deklariert, die die `__sptr`- und `__uptr`-Modifizierer verwenden, alle 32-Bit-Zeiger einer 64-Bit-Zeigervariablen zugewiesen und dann der Hexadezimalwert des jeweiligen 64-Bit-Zeigers angezeigt. Das Beispiel wird mit dem systemeigenen 64-Bit-Compiler kompiliert und auf einer 64-Bit-Plattform ausgeführt.  
  
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