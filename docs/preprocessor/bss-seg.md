---
title: Bss_seg | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.bss_seg
- bss_seg_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, bss_seg
- bss_seg pragma
ms.assetid: 755f0154-de51-4778-97d3-c9b24e445079
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08304a42b961f93b7d9e4e6e644e1514e34eb335
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2018
ms.locfileid: "42539991"
---
# <a name="bssseg"></a>bss_seg
Gibt das Segment an, in dem nicht initialisierte Variablen in der OBJ-Datei gespeichert werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma bss_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>Hinweise  
 
OBJ-Dateien können angezeigt werden, mit der [Dumpbin](../build/reference/dumpbin-command-line.md) Anwendung. Das Standardsegment für nicht initialisierte Variablen in der OBJ-Datei ist ".bss". In einigen Fällen zu verwenden, der **Bss_seg** können Ladezeiten, indem nicht initialisierte Daten in einen Abschnitt gruppiert.  
  
**Bss_seg** ohne Parameter setzt das Segment auf ".BSS".  
  
*Push* (optional)  
Legt einen Datensatz auf den internen Compilerstapel. Ein *Push* kann ein *Bezeichner* und *Segment-Name*.  
  
*POP* (optional)  
Entfernt einen Datensatz von der obersten Position des internen Compilerstapels.  
  
*Bezeichner* (optional)  
Bei Verwendung mit *Push*, den Datensatz im internen compilerstapel ein Name zugewiesen. Bei Verwendung mit *pop*, Datensätze vom internen Stapel bis *Bezeichner* wird entfernt; Wenn *Bezeichner* wurde nicht gefunden im internen Stapel, nichts per pop ausgelesen wird.  
  
*Bezeichner* ermöglicht, mehrere Datensätze mit einem einzelnen entfernen *pop* Befehl.  
  
*"Segment-Name"*(optional)  
Der Name eines Segments. Bei Verwendung mit *pop*, wird das Element im Stapel geholt und *Segment-Name* wird zum aktiven Segmentnamen.  
  
*"Segment-Class"* (optional)  
Zum Gewährleisten der Kompatibilität mit C++ vor Version 2.0 eingeführt. Wird ignoriert.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// pragma_directive_bss_seg.cpp  
int i;                     // stored in .bss  
#pragma bss_seg(".my_data1")  
int j;                     // stored in "my_data1"  
  
#pragma bss_seg(push, stack1, ".my_data2")     
int l;                     // stored in "my_data2"  
  
#pragma bss_seg(pop, stack1)   // pop stack1 from stack  
int m;                     // stored in "stack_data1"  
  
int main() {  
}  
```  
  
Sie können auch Abschnitte für initialisierte Daten angeben ([Data_seg](../preprocessor/data-seg.md)), Funktionen ([Code_seg](../preprocessor/code-seg.md)), und const-Variablen ([Const_seg](../preprocessor/const-seg.md)).  
  
Daten, die mit der **Bss_seg** Pragma behält keine Informationen über den Speicherort.  
  
Finden Sie unter [/SECTION](../build/reference/section-specify-section-attributes.md) eine Liste der Namen sollten Sie beim Erstellen eines Abschnitts nicht verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 
[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)