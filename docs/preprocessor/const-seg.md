---
title: Const_seg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.const_seg
- const_seg_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, const_seg
- const_seg pragma
ms.assetid: 1eb58ee2-fb0e-4a39-9621-699c8f5ef957
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 984dc392b6ffa51d662d3ab56b1c0dc0dbc92233
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33839154"
---
# <a name="constseg"></a>const_seg
Gibt das Segment an, in dem [const](../cpp/const-cpp.md) Variablen werden in der OBJ-Datei gespeichert.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma const_seg ( [ [ { push | pop}, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Bedeutung der Begriffe *Segment* und *Abschnitt* sind in diesem Thema gleichbedeutend.  
  
 OBJ-Dateien können angezeigt werden, mit der [Dumpbin](../build/reference/dumpbin-command-line.md) Anwendung. Das Standardsegment in der OBJ-Datei für `const`-Variablen ist .rdata. Einige `const`-Variablen, z. B. Skalare, sind automatisch im Codestream enthalten. Inlinecode erscheint nicht in .rdata.  
  
 Das Definieren eines Objekts, das eine dynamische Initialisierung in einem `const_seg` benötigt, führt zu einem nicht definierten Verhalten.  
  
 `#pragma const_seg` ohne Parameter setzt das Segment auf .rdata zurück.  
  
 `push` (optional)  
 Legt einen Datensatz auf den internen Compilerstapel. Ein `push` kann über einen `identifier` und einen `segment-name` verfügen.  
  
 `pop` (optional)  
 Entfernt einen Datensatz von der obersten Position des internen Compilerstapels.  
  
 `identifier` (optional)  
 Bei Verwendung mit `push` wird dem Datensatz im internen Compilerstapel ein Name zugewiesen. Bei Verwendung mit `pop` werden Datensätze vom internen Stapel geholt, bis `identifier` entfernt wird. Wenn `identifier` im internen Stapel nicht gefunden wird, wird kein Element vom Stapel geholt.  
  
 `identifier` ermöglicht, mehrere Datensätze mit einem `pop`-Befehl zu entfernen.  
  
 "`segment-name`" (optional)  
 Der Name eines Segments. Bei Verwendung mit `pop` wird das Element vom Stapel geholt und `segment-name` wird zum aktiven Segmentnamen.  
  
 "`segment-class`" (optional)  
 Zum Gewährleisten der Kompatibilität mit C++ vor Version 2.0 eingeführt. Wird ignoriert.  
  
## <a name="example"></a>Beispiel  
  
```  
// pragma_directive_const_seg.cpp  
// compile with: /EHsc  
#include <iostream>  
  
const int i = 7;               // inlined, not stored in .rdata  
const char sz1[]= "test1";     // stored in .rdata  
  
#pragma const_seg(".my_data1")  
const char sz2[]= "test2";     // stored in .my_data1  
  
#pragma const_seg(push, stack1, ".my_data2")  
const char sz3[]= "test3";     // stored in .my_data2  
  
#pragma const_seg(pop, stack1) // pop stack1 from stack  
const char sz4[]= "test4";     // stored in .my_data1  
  
int main() {  
    using namespace std;  
   // const data must be referenced to be put in .obj  
   cout << sz1 << endl;  
   cout << sz2 << endl;  
   cout << sz3 << endl;  
   cout << sz4 << endl;  
}  
```  
  
```Output  
test1  
test2  
test3  
test4  
```  
  
## <a name="comments"></a>Kommentare  
 Finden Sie unter [/SECTION](../build/reference/section-specify-section-attributes.md) eine Liste der Namen sollten Sie beim Erstellen eines Abschnitts nicht verwenden.  
  
 Sie können auch Abschnitte für initialisierte Daten angeben ([Data_seg](../preprocessor/data-seg.md)), nicht initialisierte Daten ([Bss_seg](../preprocessor/bss-seg.md)), und Funktionen ([Code_seg](../preprocessor/code-seg.md)).  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)