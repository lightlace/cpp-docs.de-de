---
title: Code_seg (__declspec) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- code_seg_cpp
dev_langs:
- C++
helpviewer_keywords:
- code_seg __declspec keyword
ms.assetid: ad3c1105-15d3-4e08-b7b9-e4bd9d7b6aa0
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 242dfa36d3cd0c28d1feeb2bd4a2c41d29220b40
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="codeseg-declspec"></a>code_seg (__declspec)
**Microsoft-spezifisch**  
  
 Das `code_seg`-Deklarationsattribut benennt ein ausführbares Textsegment in der OBJ-Datei, in der der Objektcode für die Funktion oder Klassenmemberfunktionen gespeichert wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
__declspec(code_seg("segname")) declarator  
```  
  
## <a name="remarks"></a>Hinweise  
 Das `__declspec(code_seg(...))`-Attribut aktiviert die Platzierung von Code in getrennt benannte Segmente, die einzeln ausgelagert oder im Speicher gesperrt werden können. Sie können dieses Attribut verwenden, um die Platzierung instanziierter Vorlagen und von durch den Compiler generiertem Code zu steuern.  
  
 Ein *Segment* ist ein benannter Codeblock, der Daten in einer OBJ-Datei, die als eine Einheit in den Arbeitsspeicher geladen wird. Ein *Textsegment* ist ein Segment, das ausführbaren Code enthält. Der Begriff *Abschnitt* Segment häufig synonym verwendet.  
  
 Objektcode, der generiert wird, wenn `declarator` definiert wird, wird in das durch `segname` angegebene Textsegment platziert, das ein Literal mit schmaler Zeichenfolge ist. Der Name `segname` nicht angegeben werden, in denen ein [Abschnitt](../preprocessor/section.md) Pragma, bevor es in einer Deklaration verwendet werden kann. Standardmäßig, wenn kein `code_seg` angegeben wird, wird Objektcode in ein Segment mit dem Namen .text platziert. Ein `code_seg` -Attribut überschreibt jede vorhandene [#pragma Code_seg](../preprocessor/code-seg.md) Richtlinie. Ein `code_seg`-Attribut, das auf eine Memberfunktion angewendet wird, überschreibt jedes `code_seg`-Attribut, dass auf die umschließende Klasse angewendet wird.  
  
 Wenn eine Entität ein `code_seg`-Attribut hat, müssen alle Deklarationen und Definitionen derselben Entität identische `code_seg`-Attribute haben. Wenn eine Basisklasse ein `code_seg`-Attribut hat, müssen abgeleitete Klassen dasselbe Attribut haben.  
  
 Wenn ein `code_seg`-Attribut auf eine Namespace-Gültigkeitsbereichsfunktion oder eine Memberfunktion angewendet wird, wird der Objektcode für diese Funktion in das angegebene Textsegment platziert. Wenn dieses Attribut auf eine Klasse angewendet wird, werden alle Memberfunktionen dieser Klasse und geschachtelter Klassen, was vom Compiler generierte spezielle Memberfunktionen umfasst, in das angegebene Segment platziert. Lokal definierte Klassen – z. B. Klassen, die in einem Memberfunktionstext definiert sind – erben das `code_seg`-Attribut des umschließenden Bereichs nicht.  
  
 Wenn ein `code_seg`-Attribut auf eine Vorlagenklasse oder eine Vorlagenfunktion angewendet wird, werden alle impliziten Spezialisierungen der Vorlage in das angegebene Segment platziert. Explizite oder partielle Spezialisierungen erben das `code_seg`-Attribut nicht aus der primären Vorlage. Sie können dasselbe oder ein unterschiedliches `code_seg`-Attribut für die Spezialisierung angeben. Ein `code_seg`-Attribut kann nicht auf eine explizite Vorlageninstanziierung angewendet werden.  
  
 Standardmäßig wird vom Compiler generierter Code, wie beispielsweise eine spezielle Memberfunktion, in das Segment .text platziert. Die Direktive `#pragma code_seg` überschreibt diesen Standard nicht. Verwenden Sie das `code_seg`-Attribut für die Klasse, die Klassenvorlage oder die Funktionsvorlage, um zu steuern, wo der vom Compiler generierte Code platziert wird.  
  
 Lambdas erben `code_seg`-Attribute von ihrem umschließenden Bereich. Um ein Segment für ein Lambda festzulegen, wenden Sie ein `code_seg`-Attribut nach der Parameterdeklarationsklausel und vor allen änderbaren Spezifikationen oder Ausnahmespezifikationen, allen nachstehenden Rückgabetypspezifikationen und dem Lambda-Text an. Weitere Informationen finden Sie unter [Lambda-Ausdruckssyntax](../cpp/lambda-expression-syntax.md). In diesem Beispiel wird ein Lambda in einem Segment mit dem Namen PagedMem definiert:  
  
```cpp  
auto Sqr = [](int t) __declspec(code_seg("PagedMem")) -> int { return t*t; };  
```  
  
 Passen Sie auf, wenn Sie spezifische Memberfunktionen – insbesondere virtuelle Memberfunktionen – in unterschiedliche Segmente platzieren. Wenn Sie eine virtuelle Funktion in einer abgeleiteten Klasse definieren, die sich in einem ausgelagerten Segment befindet, während die Basisklassenmethode sich in einem nicht ausgelagerten Segment befindet, nehmen möglicherweise andere Basisklassenmethoden oder Benutzercode an, dass der Aufruf der virtuellen Methode keinen Seitenfehler auslösen wird.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt, wie ein `code_seg`-Attribut die Segmentplatzierung steuert, wenn implizite und explizite Vorlagenspezialisierung verwendet wird:  
  
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
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [__declspec](../cpp/declspec.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)
