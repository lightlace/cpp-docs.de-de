---
title: "pack"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "pack_CPP"
  - "vc-pragma.pack"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "pack-Pragma"
  - "Pragmas, pack"
ms.assetid: e4209cbb-5437-4b53-b3fe-ac264501d404
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "corob"
manager: "ghogen"
---
# pack
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt die Komprimierungsausrichtung für Struktur, Union und Klassenmember an.  
  
## Syntax  
  
```  
  
#pragma pack( [ show ] | [ push | pop ] [, identifier ] , n  )  
```  
  
## Hinweise  
 Das Packen einer Klasse entspricht dem Platzieren ihrer Member direkt nacheinander im Arbeitsspeicher, was bedeutet kann, dass einige oder alle Member an einer Grenze, die kleiner als die standardmäßige Ausrichtung der Zielarchitektur ist, ausgerichtet werden können.  `pack` ermöglicht die Steuerung auf der Datendeklarationsebene.  Dies unterscheidet sich von der Compileroption [\/Zp](../build/reference/zp-struct-member-alignment.md), die nur die Modulebenensteuerung bereitstellt.  `pack` wird bei der ersten `struct`\-, `union`\- oder `class`\-Deklaration wirksam, nachdem das Pragma angezeigt wird.  `pack` hat keine Auswirkungen auf Definitionen.  Das Aufrufen von `pack` ohne Argumente legt `n` auf den Wert fest, der in der Compileroption **\/Zp** festgelegt ist.  Wenn die Compileroption nicht festgelegt ist, ist der Standardwert 8.  
  
 Wenn Sie die Ausrichtung einer Struktur ändern, belegt sie vielleicht nicht so viel Platz im Arbeitsspeicher, aber Sie werden eine Abnahme der Leistung feststellen oder sogar eine von der Hardware generierte Ausnahme für einen nicht ausgerichteten Zugriff erhalten.  Sie können dieses Ausnahmeverhalten mithilfe von [SetErrorMode](http://msdn.microsoft.com/library/windows/desktop/ms680621) ändern.  
  
 **show** \(optional\)  
 Zeigt den aktuellen Bytewert für die Verpackungsausrichtung an.  Der Wert wird von einer Warnmeldung angezeigt.  
  
 **push** \(optional\)  
 Überträgt den aktuellen Verpackungsausrichtungswert mittels Push auf den internen Compilerstapel und legt den aktuellen Verpackungsausrichtungswert auf `n` fest.  Wenn `n` nicht angegeben ist, wird der aktuelle Verpackungsausrichtungswert mittels Push auf den Stapel übertragen.  
  
 **pop** \(optional\)  
 Entfernt den Datensatz von der obersten Position des internen Compilerstapels.  Wenn `n` nicht mit **pop** angegeben ist, ist der Paketwert, der dem resultierenden Datensatz oben auf dem Stapel zugeordnet ist, der neue Verpackungsausrichtungswert.  Wenn z. B. `n` `#pragma pack(pop, 16)` angegeben ist, wird `n` der neue Verpackungsausrichtungswert.  Wenn Sie ein Element mit `identifier` per pop auslesen möchten, z. B. mit `#pragma pack(pop, r1)`, werden alle Datensätze bis zu dem Datensatz aus dem Stapel per pop ausgelesen, bei dem der `identifier` gefunden wird.  Dieser Datensatz wird per pop ausgelesen, und der Paketwert, der mit dem resultierenden Datensatz oben auf dem Stapel verknüpft ist, ist der neue Verpackungsausrichtungswert.  Wenn Sie einen `identifier` per pop auslesen möchten, der in keinem Datensatz auf dem Stapel gefunden wird, wird **pop** ignoriert.  
  
 `identifier` \(optional\)  
 Bei Verwendung mit **push** wird dem Datensatz im internen Compilerstapel ein Name zugewiesen.  Bei Verwendung mit **pop** werden Datensätze vom internen Stapel geholt, bis `identifier` entfernt wird. Wenn `identifier` im internen Stapel nicht gefunden wird, wird kein Element vom Stapel geholt.  
  
 `n` \(optional\)  
 Gibt den Wert in Bytes an, der für die Komprimierung verwendet werden soll.  Wenn die Compileroption [\/Zp](../build/reference/zp-struct-member-alignment.md) nicht für das Modul festgelegt wird, ist 8 der Standardwert für `n`.  Gültige Werte sind 1, 2, 4, 8 und 16.  Die Ausrichtung eines Members erfolgt an einer Begrenzung, die entweder ein Vielfaches von `n` oder ein Vielfaches der Größe des Members ist, je nachdem, was kleiner ist.  
  
 `#pragma pack(pop,` `identifier``,` `n``)` ist nicht definiert.  
  
 Weitere Informationen zur Änderung der Ausrichtung finden Sie unter folgenden Themen:  
  
-   [\_\_alignof](../cpp/alignof-operator.md)  
  
-   [align](../cpp/align-cpp.md)  
  
-   [\_\_unaligned](../cpp/unaligned.md)  
  
-   [Beispiele für die Strukturausrichtung](../build/examples-of-structure-alignment.md) \(x64\-spezifisch\)  
  
    > [!WARNING]
    >  Beachten Sie, dass Sie in Visual Studio 2015 und höher die standardmäßigen „alignas“\- und „alignof“\-Operatoren verwenden können, die im Gegensatz zu `__alignof` und `declspec( align )` über Compiler portiert werden.  Der C\+\+\-Standard behandelt nicht das Packen, daher müssen Sie immer noch `pack` verwenden \(oder die entsprechende Erweiterung auf anderen Compilern\) um Ausrichtungen anzugeben, die kleiner als die Wortgröße der Zielarchitektur sind.  
  
## Beispiel  
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
  
## Beispiel  
 Das folgende Beispiel veranschaulicht, wie die **push**\-, die **pop**\- und die **show**\-Syntax verwendet werden.  
  
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
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)