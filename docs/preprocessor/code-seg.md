---
title: "code_seg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "code_seg_CPP"
  - "vc-pragma.code_seg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "code_seg-Pragma"
  - "Pragmas, code_seg"
ms.assetid: bf4faac1-a511-46a6-8d9e-456851d97d56
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# code_seg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt das Textsegment an, in dem Funktionen in der OBJ\-Datei gespeichert werden.  
  
## Syntax  
  
```  
#pragma code_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## Hinweise  
 Die `code_seg`\-Pragmadirektive steuert nicht die Platzierung von Objektcode, der für instanziierte Vorlagen generiert wird, oder von Code, der implizit vom Compiler generiert wird – beispielsweise spezielle Memberfunktionen.  Es wird empfohlen, dass Sie statt dessen das Attribut [\_\_declspec\(code\_seg\(...\)\)](../cpp/code-seg-declspec.md) verwenden, denn es ermöglicht Ihnen die Kontrolle über die Platzierung des gesamten Objektcodes.  Dies umfasst vom Compiler generierten Code.  
  
 Ein *Segment* in einer OBJ\-Datei wird als Datenblock bezeichnet, der als eine Einheit in den Speicher geladen wird.  Ein *Textsegment* ist ein Segment, das ausführbaren Code enthält.  In diesem Artikel werden die Ausdrücke *Segment* und *Abschnitt* gleichbedeutend verwendet.  
  
 Die `code_seg`\-Pragmadirektive teilt dem Compiler mit, allen nachfolgenden Objektcode von der Übersetzungseinheit in ein Textsegment mit dem Namen `segment-name` zu platzieren.  Standardmäßig wird das Textsegment, dass für Funktionen in einer OBJ\-Datei verwendet wird, .text genannt.  
  
 Eine `code_seg`\-Pragmadirektive ohne Parameter setzt den Textsegmentname für den nachfolgenden Objektcode auf .text zurück.  
  
 **Push** \(optional\)  
 Legt einen Datensatz auf den internen Compilerstapel.  Ein **push** kann über einen `identifier` und einen `segment-name` verfügen.  
  
 **pop** \(optional\)  
 Entfernt einen Datensatz von der obersten Position des internen Compilerstapels.  
  
 `identifier` \(optional\)  
 Bei Verwendung mit **push** wird dem Datensatz im internen Compilerstapel ein Name zugewiesen.  Bei Verwendung mit **pop** werden Datensätze vom internen Stapel geholt, bis `identifier` entfernt wird. Wenn `identifier` im internen Stapel nicht gefunden wird, wird kein Element vom Stapel geholt.  
  
 `identifier` ermöglicht, mehrere Datensätze mit nur einem  **pop**\-Befehl zu entfernen.  
  
 "`segment-name`" \(optional\)  
 Der Name eines Segments.  Bei Verwendung mit **pop** wird das Element vom Stapel geholt und `segment-name` wird zum aktiven Textsegmentnamen.  
  
 "`segment-class`" \(optional\)  
 Ignoriert, aber eingeschlossen, um die Kompatibilität mit Versionen von C\+\+ vor der Version 2.0 zu gewährleisten.  
  
 Sie können die Anwendung [DUMPBIN.EXE](../build/reference/dumpbin-command-line.md) verwenden, um OBJ\-Dateien anzuzeigen.  Versionen von DUMPBIN für jede unterstützte Zielarchitektur werden in [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] eingeschlossen.  
  
## Beispiel  
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
  
 Eine Liste der Namen, die beim Erstellen eines Abschnitts nicht verwendet werden sollten, finden Sie unter [\/SECTION](../build/reference/section-specify-section-attributes.md).  
  
 Sie können auch Abschnitte für initialisierte Daten \([data\_seg](../preprocessor/data-seg.md)\), nicht initialisierte Daten \([bss\_seg](../preprocessor/bss-seg.md)\) und const\-Variablen \([const\_seg](../preprocessor/const-seg.md)\) angeben.  
  
## Siehe auch  
 [code\_seg \(\_\_declspec\)](../cpp/code-seg-declspec.md)   
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)