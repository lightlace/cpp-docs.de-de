---
title: Code_seg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- code_seg_CPP
- vc-pragma.code_seg
dev_langs:
- C++
helpviewer_keywords:
- pragmas, code_seg
- code_seg pragma
ms.assetid: bf4faac1-a511-46a6-8d9e-456851d97d56
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f958d1652f82f297ae530c1e24bdf331976e0dc0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="codeseg"></a>code_seg
Gibt das Textsegment an, in dem Funktionen in der OBJ-Datei gespeichert werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma code_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `code_seg`-Pragmadirektive steuert nicht die Platzierung von Objektcode, der für instanziierte Vorlagen generiert wird, oder von Code, der implizit vom Compiler generiert wird – beispielsweise spezielle Memberfunktionen. Wir empfehlen die Verwendung der [__declspec(code_seg(...)) ](../cpp/code-seg-declspec.md) -Attribut stattdessen, denn es Ihnen ermöglicht die Kontrolle über die Platzierung des gesamten Objektcodes. Dies umfasst vom Compiler generierten Code.  
  
 Ein *Segment* in einer OBJ-Datei ist ein benannter Codeblock, der Daten, die als eine Einheit in den Arbeitsspeicher geladen wird. Ein *Textsegment* ist ein Segment, das ausführbaren Code enthält. In diesem Artikel die Begriffe *Segment* und *Abschnitt* synonym verwendet werden.  
  
 Die `code_seg`-Pragmadirektive teilt dem Compiler mit, allen nachfolgenden Objektcode von der Übersetzungseinheit in ein Textsegment mit dem Namen `segment-name` zu platzieren. Standardmäßig wird das Textsegment, dass für Funktionen in einer OBJ-Datei verwendet wird, .text genannt.  
  
 Eine `code_seg`-Pragmadirektive ohne Parameter setzt den Textsegmentname für den nachfolgenden Objektcode auf .text zurück.  
  
 **Push** (optional)  
 Legt einen Datensatz auf den internen Compilerstapel. Ein **Push** kann ein `identifier` und `segment-name`.  
  
 **POP** (optional)  
 Entfernt einen Datensatz von der obersten Position des internen Compilerstapels.  
  
 `identifier` (optional)  
 Bei Verwendung mit **Push**, den Datensatz im internen compilerstapel ein Name zugewiesen. Bei Verwendung mit **pop**, Datensätze vom internen Stapel bis `identifier` entfernt wird; Wenn `identifier` befindet sich nicht im internen Stapel nichts per pop ausgelesen wird.  
  
 `identifier` ermöglicht, mehrere Datensätze mit nur einem per pop ausgelesen werden **pop** Befehl.  
  
 "`segment-name`" (optional)  
 Der Name eines Segments. Bei Verwendung mit **pop**, wird der Stapel geholt und `segment-name` wird zum aktiven textsegmentnamen.  
  
 "`segment-class`" (optional)  
 Ignoriert, aber eingeschlossen, um die Kompatibilität mit Versionen von C++ vor der Version 2.0 zu gewährleisten.  
  
 Sie können die [DUMPBIN. EXE-Datei](../build/reference/dumpbin-command-line.md) Anwendung OBJ-Dateien anzeigen. Versionen von DUMPBIN für jede unterstützte Zielarchitektur werden in [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] eingeschlossen.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird gezeigt, wie Sie mithilfe der Pragmadirektive `code_seg` steuern können, wo der Objektcode platziert wird:  
  
```  
// pragma_directive_code_seg.cpp  
void func1() {                  // stored in .text  
}  
  
#pragma code_seg(".my_data1")  
void func2() {                  // stored in my_data1  
}  
  
#pragma code_seg(push, r1, ".my_data2")  
void func3() {                  // stored in my_data2  
}  
  
#pragma code_seg(pop, r1)      // stored in my_data1  
void func4() {  
}  
  
int main() {  
}  
```  
  
 Eine Liste der Namen, die zum Erstellen eines Abschnitts nicht verwendet werden soll, finden Sie unter [/SECTION](../build/reference/section-specify-section-attributes.md).  
  
 Sie können auch Abschnitte für initialisierte Daten angeben ([Data_seg](../preprocessor/data-seg.md)), nicht initialisierte Daten ([Bss_seg](../preprocessor/bss-seg.md)), und const-Variablen ([Const_seg](../preprocessor/const-seg.md)).  
  
## <a name="see-also"></a>Siehe auch  
 [code_seg (__declspec)](../cpp/code-seg-declspec.md)   
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)