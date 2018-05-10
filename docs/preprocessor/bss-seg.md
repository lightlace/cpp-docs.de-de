---
title: Bss_seg | Microsoft Docs
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
ms.openlocfilehash: 1b82027066e66cc51be8982a19ab6209ff236ef2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="bssseg"></a>bss_seg
Gibt das Segment an, in dem nicht initialisierte Variablen in der OBJ-Datei gespeichert werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
#pragma bss_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>Hinweise  
 OBJ-Dateien können angezeigt werden, mit der [Dumpbin](../build/reference/dumpbin-command-line.md) Anwendung. Das Standardsegment für nicht initialisierte Variablen in der OBJ-Datei ist ".bss". In einigen Fällen zu verwenden, der **Bss_seg** beschleunigen können Ladezeiten, indem nicht initialisierte Daten in einen Abschnitt gruppiert.  
  
 **Bss_seg** ohne Parameter setzt das Segment auf ".BSS".  
  
 **Push**(optional)  
 Legt einen Datensatz auf den internen Compilerstapel. Ein **Push** kann ein *Bezeichner* und *Segmentnamen*.  
  
 **POP** (optional)  
 Entfernt einen Datensatz von der obersten Position des internen Compilerstapels.  
  
 *Bezeichner* (optional)  
 Bei Verwendung mit **Push**, den Datensatz im internen compilerstapel ein Name zugewiesen. Bei Verwendung mit **pop**, Datensätze vom internen Stapel bis *Bezeichner* entfernt wird; Wenn *Bezeichner* befindet sich nicht im internen Stapel nichts per pop ausgelesen wird.  
  
 *Bezeichner* ermöglicht, mehrere Datensätze mit einem einzelnen entfernen **pop** Befehl.  
  
 *"Segmentnamen"*(optional)  
 Der Name eines Segments. Bei Verwendung mit **pop**, wird der Stapel geholt und *Segmentnamen* wird zum aktiven Segmentnamen.  
  
 *"Segmentklasse"* (optional)  
 Zum Gewährleisten der Kompatibilität mit C++ vor Version 2.0 eingeführt. Wird ignoriert.  
  
## <a name="example"></a>Beispiel  
  
```  
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
  
 Daten, die mithilfe der **Bss_seg** Pragma behält keine Informationen über den Speicherort.  
  
 Finden Sie unter [/SECTION](../build/reference/section-specify-section-attributes.md) eine Liste der Namen sollten Sie beim Erstellen eines Abschnitts nicht verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)