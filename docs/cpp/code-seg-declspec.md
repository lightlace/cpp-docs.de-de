---
title: "code_seg (__declspec) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "code_seg_cpp"
  - "code_seg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "code_seg __declspec-Schlüsselwort"
ms.assetid: ad3c1105-15d3-4e08-b7b9-e4bd9d7b6aa0
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# code_seg (__declspec)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Das `code_seg`\-Deklarationsattribut benennt ein ausführbares Textsegment in der OBJ\-Datei, in der der Objektcode für die Funktion oder Klassenmemberfunktionen gespeichert wird.  
  
## Syntax  
  
```  
__declspec(code_seg("segname")) declarator  
```  
  
## Hinweise  
 Das `__declspec(code_seg(...))`\-Attribut aktiviert die Platzierung von Code in getrennt benannte Segmente, die einzeln ausgelagert oder im Speicher gesperrt werden können.  Sie können dieses Attribut verwenden, um die Platzierung instanziierter Vorlagen und von durch den Compiler generiertem Code zu steuern.  
  
 Ein *Segment* wird als Datenblock in einer OBJ\-Datei bezeichnet, der als eine Einheit in den Speicher geladen wird.  Ein *Textsegment* ist ein Segment, das ausführbaren Code enthält.  Der Term *Abschnitt* wird oft wahlweise anstelle von Segment verwendet.  
  
 Objektcode, der generiert wird, wenn `declarator` definiert wird, wird in das durch `segname` angegebene Textsegment platziert, das ein Literal mit schmaler Zeichenfolge ist.  Der Name `segname` muss nicht in einem [Abschnitts](../preprocessor/section.md)\-Pragma angegeben werden, bevor er in einer Deklaration verwendet werden kann.  Standardmäßig, wenn kein `code_seg` angegeben wird, wird Objektcode in ein Segment mit dem Namen .text platziert.  Ein `code_seg`\-Attribut überschreibt jede vorhandene [\#pragma code\_seg](../preprocessor/code-seg.md)\-Direktive.  Ein `code_seg`\-Attribut, das auf eine Memberfunktion angewendet wird, überschreibt jedes `code_seg`\-Attribut, dass auf die umschließende Klasse angewendet wird.  
  
 Wenn eine Entität ein `code_seg`\-Attribut hat, müssen alle Deklarationen und Definitionen derselben Entität identische `code_seg`\-Attribute haben.  Wenn eine Basisklasse ein `code_seg`\-Attribut hat, müssen abgeleitete Klassen dasselbe Attribut haben.  
  
 Wenn ein `code_seg`\-Attribut auf eine Namespace\-Gültigkeitsbereichsfunktion oder eine Memberfunktion angewendet wird, wird der Objektcode für diese Funktion in das angegebene Textsegment platziert.  Wenn dieses Attribut auf eine Klasse angewendet wird, werden alle Memberfunktionen dieser Klasse und geschachtelter Klassen, was vom Compiler generierte spezielle Memberfunktionen umfasst, in das angegebene Segment platziert.  Lokal definierte Klassen – z. B. Klassen, die in einem Memberfunktionstext definiert sind – erben das `code_seg`\-Attribut des umschließenden Bereichs nicht.  
  
 Wenn ein `code_seg`\-Attribut auf eine Vorlagenklasse oder eine Vorlagenfunktion angewendet wird, werden alle impliziten Spezialisierungen der Vorlage in das angegebene Segment platziert.  Explizite oder partielle Spezialisierungen erben das `code_seg`\-Attribut nicht aus der primären Vorlage.  Sie können dasselbe oder ein unterschiedliches `code_seg`\-Attribut für die Spezialisierung angeben.  Ein `code_seg`\-Attribut kann nicht auf eine explizite Vorlageninstanziierung angewendet werden.  
  
 Standardmäßig wird vom Compiler generierter Code, wie beispielsweise eine spezielle Memberfunktion, in das Segment .text platziert.  Die Direktive `#pragma code_seg` überschreibt diesen Standard nicht.  Verwenden Sie das `code_seg`\-Attribut für die Klasse, die Klassenvorlage oder die Funktionsvorlage, um zu steuern, wo der vom Compiler generierte Code platziert wird.  
  
 Lambdas erben `code_seg`\-Attribute von ihrem umschließenden Bereich.  Um ein Segment für ein Lambda festzulegen, wenden Sie ein `code_seg`\-Attribut nach der Parameterdeklarationsklausel und vor allen änderbaren Spezifikationen oder Ausnahmespezifikationen, allen nachstehenden Rückgabetypspezifikationen und dem Lambda\-Text an.  Weitere Informationen finden Sie unter [Lambda\-Ausdruckssyntax](../cpp/lambda-expression-syntax.md).  In diesem Beispiel wird ein Lambda in einem Segment mit dem Namen PagedMem definiert:  
  
```cpp  
auto Sqr = [](int t) __declspec(code_seg("PagedMem")) -> int { return t*t; };  
```  
  
 Passen Sie auf, wenn Sie spezifische Memberfunktionen – insbesondere virtuelle Memberfunktionen – in unterschiedliche Segmente platzieren.  Wenn Sie eine virtuelle Funktion in einer abgeleiteten Klasse definieren, die sich in einem ausgelagerten Segment befindet, während die Basisklassenmethode sich in einem nicht ausgelagerten Segment befindet, nehmen möglicherweise andere Basisklassenmethoden oder Benutzercode an, dass der Aufruf der virtuellen Methode keinen Seitenfehler auslösen wird.  
  
## Beispiel  
 Dieses Beispiel zeigt, wie ein `code_seg`\-Attribut die Segmentplatzierung steuert, wenn implizite und explizite Vorlagenspezialisierung verwendet wird:  
  
```  
// code_seg.cpp  
// Compile: cl /EHsc /W4 code_seg.cpp  
  
// Base template places object code in Segment_1 segment  
template<class T>  
class __declspec(code_seg("Segment_1")) Example  
{  
public:  
   virtual void VirtualMemberFunction(T /*arg*/) {}  
};  
  
// bool specialization places code in default .text segment  
template<>  
class Example<bool>   
{  
public:  
   virtual void VirtualMemberFunction(bool /*arg*/) {}  
};  
  
// int specialization places code in Segment_2 segment  
template<>  
class __declspec(code_seg("Segment_2")) Example<int>   
{  
public:  
   virtual void VirtualMemberFunction(int /*arg*/) {}  
};  
  
// Compiler warns and ignores __declspec(code_seg("Segment_3"))  
// in this explicit specialization  
__declspec(code_seg("Segment_3")) Example<short>; // C4071  
  
int main()  
{  
   // implicit double specialization uses base template's  
   // __declspec(code_seg("Segment_1")) to place object code  
   Example<double> doubleExample{};  
   doubleExample.VirtualMemberFunction(3.14L);  
  
   // bool specialization places object code in default .text segment  
   Example<bool> boolExample{};  
   boolExample.VirtualMemberFunction(true);  
  
   // int specialization uses __declspec(code_seg("Segment_2"))  
   // to place object code  
   Example<int> intExample{};  
   intExample.VirtualMemberFunction(42);  
}  
```  
  
 **Ende Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)