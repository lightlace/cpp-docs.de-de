---
title: Data_seg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- data_seg_CPP
- vc-pragma.data_seg
dev_langs:
- C++
helpviewer_keywords:
- data_seg pragma
- pragmas, data_seg
ms.assetid: 65c66466-4c98-494f-93af-106beb4caf78
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c23598ba98d35e2a32832437111ebf9f852e1259
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="dataseg"></a>data_seg
Gibt das Datensegment an, in dem initialisierte Variablen in der OBJ-Datei gespeichert werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
#pragma data_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Bedeutung der Begriffe *Segment* und *Abschnitt* sind in diesem Thema gleichbedeutend.  
  
 OBJ-Dateien können angezeigt werden, mit der [Dumpbin](../build/reference/dumpbin-command-line.md) Anwendung. Das Standardsegment für initialisierte Variablen in der OBJ-Datei ist ".data". Nicht initialisierte Variablen werden als mit Null initialisiert behandelt und in ".bss" gespeichert.  
  
 **Data_seg** ohne Parameter setzt das Segment auf .data.  
  
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
// pragma_directive_data_seg.cpp  
int h = 1;                     // stored in .data  
int i = 0;                     // stored in .bss  
#pragma data_seg(".my_data1")  
int j = 1;                     // stored in "my_data1"  
  
#pragma data_seg(push, stack1, ".my_data2")     
int l = 2;                     // stored in "my_data2"  
  
#pragma data_seg(pop, stack1)   // pop stack1 off the stack  
int m = 3;                     // stored in "stack_data1"  
  
int main() {  
}  
```  
  
 Daten mithilfe von zugeordnet **Data_seg** alle Informationen über den Speicherort wird nicht beibehalten.  
  
 Finden Sie unter [/SECTION](../build/reference/section-specify-section-attributes.md) eine Liste der Namen sollten Sie beim Erstellen eines Abschnitts nicht verwenden.  
  
 Sie können auch Abschnitte für const-Variablen angeben ([Const_seg](../preprocessor/const-seg.md)), nicht initialisierte Daten ([Bss_seg](../preprocessor/bss-seg.md)), und Funktionen ([Code_seg](../preprocessor/code-seg.md)).  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)