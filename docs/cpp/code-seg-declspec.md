---
title: Code_seg (__declspec) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- code_seg_cpp
dev_langs:
- C++
helpviewer_keywords:
- code_seg __declspec keyword
ms.assetid: ad3c1105-15d3-4e08-b7b9-e4bd9d7b6aa0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dc96b3bdd7aa2eed69290b879e054df5ac6f35c3
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408835"
---
# <a name="codeseg-declspec"></a>code_seg (__declspec)
**Microsoft-spezifisch**  
  
 Die **Code_seg** -Deklarationsattribut benennt ein ausführbares Textsegment in der OBJ-Datei, die in der der Objektcode für die Funktion oder Klassenmemberfunktionen gespeichert wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
__declspec(code_seg("segname")) declarator  
```  
  
## <a name="remarks"></a>Hinweise  
 Das `__declspec(code_seg(...))`-Attribut aktiviert die Platzierung von Code in getrennt benannte Segmente, die einzeln ausgelagert oder im Speicher gesperrt werden können. Sie können dieses Attribut verwenden, um die Platzierung instanziierter Vorlagen und von durch den Compiler generiertem Code zu steuern.  
  
 Ein *Segment* ist ein benannter Block von Daten in einer OBJ-Datei, die als eine Einheit in den Speicher geladen wird. Ein *Textsegment* ist ein Segment, das ausführbaren Code enthält. Der Begriff *Abschnitt* Segment wird häufig synonym verwendet.  
  
 Objektcode, der generiert wird, wenn `declarator` definiert wird, wird in das durch `segname` angegebene Textsegment platziert, das ein Literal mit schmaler Zeichenfolge ist. Der Name `segname` muss nicht angegeben werden eine [Abschnitt](../preprocessor/section.md) Pragma, bevor es in einer Deklaration verwendet werden kann. Standardmäßig, wenn kein `code_seg` angegeben wird, wird Objektcode in ein Segment mit dem Namen .text platziert. Ein **Code_seg** -Attribut überschreibt jede vorhandene [#pragma Code_seg](../preprocessor/code-seg.md) Richtlinie. Ein **Code_seg** -Attribut auf eine Memberfunktion überschreibt alle **Code_seg** auf der einschließenden Klasse angewendete Attribut.  
  
 Wenn eine Entität verfügt über eine **Code_seg** -Attribut, das alle Deklarationen und Definitionen derselben Entität identische benötigen **Code_seg** Attribute. Wenn eine Basisklasse verfügt über eine **Code_seg** abgeleitetes Attribut Klassen müssen dasselbe Attribut verfügen.  
  
 Wenn eine **Code_seg** Attribut eine Namespace-gültigkeitsbereichsfunktion oder eine Memberfunktion angewendet wird, der Objektcode für diese Funktion in das angegebene Textsegment platziert. Wenn dieses Attribut auf eine Klasse angewendet wird, werden alle Memberfunktionen dieser Klasse und geschachtelter Klassen, was vom Compiler generierte spezielle Memberfunktionen umfasst, in das angegebene Segment platziert. Lokal definierte Klassen – z. B. Klassen, die in einem Funktionsrumpf Member definiert, erben nicht die **Code_seg** Attribut des einschließenden Bereich.  
  
 Wenn eine **Code_seg** -Attribut auf eine Vorlagenklasse oder eine Vorlagenfunktion angewendet wird, werden alle implizite spezialisierungen der Vorlage in das angegebene Segment platziert. Explizite oder partielle spezialisierungen erben nicht die **Code_seg** Attribut aus der primären Vorlage. Sie können angeben, die denselben oder einen anderen **Code_seg** -Attribut für die Spezialisierung. Ein **Code_seg** Attribut nicht auf eine explizite Vorlageninstanziierung angewendet werden.  
  
 Standardmäßig wird vom Compiler generierter Code, wie beispielsweise eine spezielle Memberfunktion, in das Segment .text platziert. Die Direktive `#pragma code_seg` überschreibt diesen Standard nicht. Verwenden der **Code_seg** Attribut für die Klasse, Klassenvorlage oder Funktionsvorlage, um steuern, in dem vom Compiler generierte Code platziert wird.  
  
 Lambdas erben **Code_seg** Attribute von ihrem umschließenden Bereich. Um ein Segment für einen Lambda-Ausdruck angeben, gelten eine **Code_seg** Attribut nach der parameterdeklarationsklausel und vor allen änderbaren oder Ausnahmespezifikation, alle nachstehenden rückgabetypspezifikationen und der Lambda-Text. Weitere Informationen finden Sie unter [Lambda-Ausdruckssyntax](../cpp/lambda-expression-syntax.md). In diesem Beispiel wird ein Lambda in einem Segment mit dem Namen PagedMem definiert:  
  
```cpp  
auto Sqr = [](int t) __declspec(code_seg("PagedMem")) -> int { return t*t; };  
```  
  
 Passen Sie auf, wenn Sie spezifische Memberfunktionen – insbesondere virtuelle Memberfunktionen – in unterschiedliche Segmente platzieren. Wenn Sie eine virtuelle Funktion in einer abgeleiteten Klasse definieren, die sich in einem ausgelagerten Segment befindet, während die Basisklassenmethode sich in einem nicht ausgelagerten Segment befindet, nehmen möglicherweise andere Basisklassenmethoden oder Benutzercode an, dass der Aufruf der virtuellen Methode keinen Seitenfehler auslösen wird.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt, wie eine **Code_seg** -Attribut die segmentplatzierung steuert wenn implizite und explizite vorlagenspezialisierung verwendet wird:  
  
```cpp 
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
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [__declspec](../cpp/declspec.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)