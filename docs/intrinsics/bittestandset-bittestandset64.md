---
title: "_bittestandset, _bittestandset64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_bittestandset_cpp"
  - "_bittestandset64_cpp"
  - "_bittestandset64"
  - "_bittestandset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_bittestandset intrinsic"
  - "_bittestandset64 intrinsic"
  - "bts instruction"
ms.assetid: 6d6c8670-fea0-4c1c-9aad-2bb842715203
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _bittestandset, _bittestandset64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Erzeugen Sie eine Anweisung, die Bit `b` der Adresse `a` untersucht, den aktuellen Wert zurückgibt und das Bit auf 1 setzt.  
  
## Syntax  
  
```  
unsigned char _bittestandset(    long *a,    long b ); unsigned char _bittestandset64(    __int64 *a,    __int64 b );  
```  
  
#### Parameter  
 \[in, out\] `a`  
 Ein Zeiger auf den zu untersuchenden Speicher.  
  
 \[in\] `b`  
 Die zu testende Bitposition.  
  
## Rückgabewert  
 Das Bit an der angegebenen Position.  
  
## Anforderungen  
  
|Systemintern|Architektur|  
|------------------|-----------------|  
|`_bittestandset`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`_bittestandset64`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Diese Routine ist nur als systeminterne Funktion verfügbar.  
  
## Beispiel  
  
```  
// bittestandset.cpp  
// processor: x86, ARM, x64  
// This example uses several of the _bittest family of intrinsics  
// to implement a Flags class that allows bit level access to an  
// integer field.  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_bittestandset, _bittestandreset,\  
                  _bittestandcomplement, _bittest)  
  
class Flags  
{  
private:  
    long flags;  
    long* oldValues;  
  
public:  
    Flags() : flags(0)  
    {  
        oldValues = new long[32];  
    }  
  
    ~Flags()  
    {  
        delete oldValues;  
    }  
  
    void SetFlagBit(long nBit)  
    {  
        // We omit range checks on the argument  
        oldValues[nBit] = _bittestandset(&flags, nBit);  
        printf_s("Flags: 0x%x\n", flags);  
    }  
    void ClearFlagBit(long nBit)  
    {  
        oldValues[nBit] = _bittestandreset(&flags, nBit);  
        printf_s("Flags: 0x%x\n", flags);  
    }  
    unsigned char GetFlagBit(long nBit)  
    {  
        unsigned char result = _bittest(&flags, nBit);  
        printf_s("Flags: 0x%x\n", flags);  
        return result;  
    }  
    void RestoreFlagBit(long nBit)  
    {  
        if (oldValues[nBit])  
            oldValues[nBit] = _bittestandset(&flags, nBit);  
        else  
            oldValues[nBit] = _bittestandreset(&flags, nBit);  
        printf_s("Flags: 0x%x\n", flags);       
    }  
    unsigned char ToggleBit(long nBit)  
    {  
        unsigned char result = _bittestandcomplement(&flags, nBit);  
        printf_s("Flags: 0x%x\n", flags);  
        return result;  
    }  
};  
  
int main()  
{  
    Flags f;  
    f.SetFlagBit(1);  
    f.SetFlagBit(2);  
    f.SetFlagBit(3);  
    f.ClearFlagBit(3);  
    f.ToggleBit(1);  
    f.RestoreFlagBit(2);  
}  
```  
  
  **Flags: 0x2**  
**Flags: 0x6**  
**Flags: 0xe**  
**Flags: 0x6**  
**Flags: 0x4**  
**Flags: 0x0**   
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)