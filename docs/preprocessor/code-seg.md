---
title: Code_seg | Microsoft-Dokumentation
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
ms.openlocfilehash: 052e9a55d443fa263ecf8443c9e3933baeb1f3b8
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "42538654"
---
# <a name="codeseg"></a>code_seg
Gibt das Textsegment an, in dem Funktionen in der OBJ-Datei gespeichert werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma code_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>Hinweise  
 
Die **Code_seg** Pragmaanweisung steuert nicht die Platzierung von Objektcode, der für instanziierte Vorlagen generiert, oder von Code, die implizit vom Compiler generiert werden – beispielsweise spezielle Memberfunktionen. Wir empfehlen die Verwendung der [__declspec(code_seg(...)) ](../cpp/code-seg-declspec.md) Attribut stattdessen, denn es Ihnen ermöglicht die Kontrolle über die Platzierung des gesamten Objektcodes. Dies umfasst vom Compiler generierten Code.  
  
Ein *Segment* in einer OBJ-Datei ist einem benannten Block von Daten, die als eine Einheit in den Speicher geladen wird. Ein *Textsegment* ist ein Segment, das ausführbaren Code enthält. In diesem Artikel die Begriffe *Segment* und *Abschnitt* werden synonym verwendet.  
  
Die **Code_seg** Pragmaanweisung teilt dem Compiler mit allen nachfolgenden Objektcode von der Übersetzungseinheit in ein Textsegment mit dem Namen einfügen *Segment-Name*. Standardmäßig wird das Textsegment, dass für Funktionen in einer OBJ-Datei verwendet wird, .text genannt.  
  
Ein **Code_seg** Pragmaanweisung ohne Parameter setzt den textsegmentnamen für den nachfolgenden Objektcode auf .text zurück.  
  
*Push* (optional)  
Legt einen Datensatz auf den internen Compilerstapel. Ein *Push* kann ein *Bezeichner* und *Segment-Name*.  
  
*POP* (optional)  
Entfernt einen Datensatz von der obersten Position des internen Compilerstapels.  
  
*Bezeichner* (optional)  
Bei Verwendung mit *Push*, den Datensatz im internen compilerstapel ein Name zugewiesen. Bei Verwendung mit *pop*, Datensätze vom internen Stapel bis *Bezeichner* wird entfernt; Wenn *Bezeichner* wurde nicht gefunden im internen Stapel, nichts per pop ausgelesen wird.  
  
*Bezeichner* ermöglicht, mehrere Datensätze mit nur einem entfernen *pop* Befehl.  
  
"*Segment-Name*" (optional)  
Der Name eines Segments. Bei Verwendung mit *pop*, wird das Element im Stapel geholt und *Segment-Name* wird von der aktiven textsegmentnamen.  
  
"*Segmentklasse*" (optional)  
Ignoriert, aber eingeschlossen, um die Kompatibilität mit Versionen von C++ vor der Version 2.0 zu gewährleisten.  
  
Sie können die [DUMPBIN. EXE-Datei](../build/reference/dumpbin-command-line.md) Anwendung zum Anzeigen der OBJ-Dateien. Versionen von DUMPBIN für jede unterstützte Zielarchitektur werden in Visual Studio enthalten.  
  
## <a name="example"></a>Beispiel  

Dieses Beispiel zeigt, wie Sie mit der **Code_seg** Pragma-Direktive, um zu steuern, wo der Objektcode platziert:  
  
```cpp  
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
  
Eine Liste von Namen, die beim Erstellen eines Abschnitts nicht verwendet werden soll, finden Sie unter [/SECTION](../build/reference/section-specify-section-attributes.md).  
  
Sie können auch Abschnitte für initialisierte Daten angeben ([Data_seg](../preprocessor/data-seg.md)), nicht initialisierte Daten ([Bss_seg](../preprocessor/bss-seg.md)), und const-Variablen ([Const_seg](../preprocessor/const-seg.md)).  
  
## <a name="see-also"></a>Siehe auch  
 
[code_seg (__declspec)](../cpp/code-seg-declspec.md)   
[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)