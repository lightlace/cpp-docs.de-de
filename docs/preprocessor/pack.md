---
title: Pack | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- pack_CPP
- vc-pragma.pack
dev_langs: C++
helpviewer_keywords:
- pragmas, pack
- pack pragma
ms.assetid: e4209cbb-5437-4b53-b3fe-ac264501d404
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f4a6dc351d0184d43a1cf79f1cec9e9bae33aecf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="pack"></a>pack
Gibt die Komprimierungsausrichtung für Struktur, Union und Klassenmember an.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
#pragma pack( [ show ] | [ push | pop ] [, identifier ] , n  )  
```  
  
## <a name="remarks"></a>Hinweise  
 Das Packen einer Klasse entspricht dem Platzieren ihrer Member direkt nacheinander im Arbeitsspeicher, was bedeutet kann, dass einige oder alle Member an einer Grenze, die kleiner als die standardmäßige Ausrichtung der Zielarchitektur ist, ausgerichtet werden können. `pack` ermöglicht die Steuerung auf der Datendeklarationsebene. Dies unterscheidet sich von der Compileroption [/Zp](../build/reference/zp-struct-member-alignment.md), stellt nur auf Modulebene Steuerelement. `pack` wird bei der ersten `struct`-, `union`- oder `class`-Deklaration wirksam, nachdem das Pragma angezeigt wird. `pack` hat keine Auswirkungen auf Definitionen. Aufrufen von `pack` ohne Argumente legt `n` auf den Wert fest, in der Compileroption **/Zp**. Wenn die Compileroption nicht festgelegt ist, ist der Standardwert 8.  
  
 Wenn Sie die Ausrichtung einer Struktur ändern, belegt sie vielleicht nicht so viel Platz im Arbeitsspeicher, aber Sie werden eine Abnahme der Leistung feststellen oder sogar eine von der Hardware generierte Ausnahme für einen nicht ausgerichteten Zugriff erhalten.  Sie können dieses Ausnahmeverhalten mithilfe ändern [SetErrorMode](http://msdn.microsoft.com/library/windows/desktop/ms680621).  
  
 **anzeigen** (optional)  
 Zeigt den aktuellen Bytewert für die Verpackungsausrichtung an. Der Wert wird von einer Warnmeldung angezeigt.  
  
 **Push** (optional)  
 Überträgt den aktuellen Verpackungsausrichtungswert mittels Push auf den internen Compilerstapel und legt den aktuellen Verpackungsausrichtungswert auf `n` fest. Wenn `n` nicht angegeben ist, wird der aktuelle Verpackungsausrichtungswert mittels Push auf den Stapel übertragen.  
  
 **POP** (optional)  
 Entfernt den Datensatz von der obersten Position des internen Compilerstapels. Wenn `n` nicht mit angegeben **pop**, dann ist der Paketwert, der mit dem resultierenden Datensatz oben im Stapel verknüpft ist der neue verpackungsausrichtungswert. Wenn z. B. `n` `#pragma pack(pop, 16)` angegeben ist, wird `n` der neue Verpackungsausrichtungswert. Wenn Sie ein Element mit `identifier` per pop auslesen möchten, z. B. mit `#pragma pack(pop, r1)`, werden alle Datensätze bis zu dem Datensatz aus dem Stapel per pop ausgelesen, bei dem der `identifier` gefunden wird. Dieser Datensatz wird per pop ausgelesen, und der Paketwert, der mit dem resultierenden Datensatz oben auf dem Stapel verknüpft ist, ist der neue Verpackungsausrichtungswert. Wenn Sie per POP auslesen möchten eine `identifier` , die in keinem Datensatz auf dem Stapel nicht gefunden wurde die **pop** wird ignoriert.  
  
 `identifier` (optional)  
 Bei Verwendung mit **Push**, den Datensatz im internen compilerstapel ein Name zugewiesen. Bei Verwendung mit **pop**, Datensätze vom internen Stapel bis `identifier` entfernt wird; Wenn `identifier` befindet sich nicht im internen Stapel nichts per pop ausgelesen wird.  
  
 `n` (optional)  
 Gibt den Wert in Bytes an, der für die Komprimierung verwendet werden soll. Wenn die Compileroption " [/Zp](../build/reference/zp-struct-member-alignment.md) nicht festgelegt ist, für das Modul, der Standardwert für `n` ist 8. Gültige Werte sind 1, 2, 4, 8 und 16. Die Ausrichtung eines Members erfolgt an einer Begrenzung, die entweder ein Vielfaches von `n` oder ein Vielfaches der Größe des Members ist, je nachdem, was kleiner ist.  
  
 `#pragma pack(pop, identifier, n)`ist nicht definiert.  
  
 Weitere Informationen zur Änderung der Ausrichtung finden Sie unter folgenden Themen:  
  
-   [__alignof](../cpp/alignof-operator.md)  
  
-   [align](../cpp/align-cpp.md)  
  
-   [__unaligned](../cpp/unaligned.md)  
  
-   [Beispiele für die Strukturausrichtung](../build/examples-of-structure-alignment.md) (X64 bestimmte)  
  
    > [!WARNING]
    >  Beachten Sie, dass Sie in Visual Studio 2015 und höher die standardmäßigen „alignas“- und „alignof“-Operatoren verwenden können, die im Gegensatz zu `__alignof` und `declspec( align )` über Compiler portiert werden. Der C++-Standard behandelt nicht das Packen, daher müssen Sie immer noch `pack` verwenden (oder die entsprechende Erweiterung auf anderen Compilern) um Ausrichtungen anzugeben, die kleiner als die Wortgröße der Zielarchitektur sind.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie das Pragma `pack` verwendet wird, um die Ausrichtung einer Struktur zu ändern.  
  
```  
// pragma_directives_pack.cpp  
#include <stddef.h>  
#include <stdio.h>  
  
struct S {  
   int i;   // size 4  
   short j;   // size 2  
   double k;   // size 8  
};  
  
#pragma pack(2)  
struct T {  
   int i;  
   short j;  
   double k;  
};  
  
int main() {  
   printf("%zu ", offsetof(S, i));  
   printf("%zu ", offsetof(S, j));  
   printf("%zu\n", offsetof(S, k));  
  
   printf("%zu ", offsetof(T, i));  
   printf("%zu ", offsetof(T, j));  
   printf("%zu\n", offsetof(T, k));  
}  
```  
  
```  
0 4 8  
0 4 6  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie die **Push**, **pop**, und **anzeigen** Syntax.  
  
```  
// pragma_directives_pack_2.cpp  
// compile with: /W1 /c  
#pragma pack()   // n defaults to 8; equivalent to /Zp8  
#pragma pack(show)   // C4810  
#pragma pack(4)   // n = 4  
#pragma pack(show)   // C4810  
#pragma pack(push, r1, 16)   // n = 16, pushed to stack  
#pragma pack(show)   // C4810  
#pragma pack(pop, r1, 2)   // n = 2 , stack popped  
#pragma pack(show)   // C4810  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)