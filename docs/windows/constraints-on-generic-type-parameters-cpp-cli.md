---
title: Einschränkungen für generische Typparameter (C++ / CLI) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- where
dev_langs:
- C++
helpviewer_keywords:
- where keyword [C++]
- constraints, C++
ms.assetid: eb828cc9-684f-48a3-a898-b327700c0a63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 33829d868eb90cde7259a482b8fc80f9cd6fd677
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465297"
---
# <a name="constraints-on-generic-type-parameters-ccli"></a>Einschränkungen für generische Typparameter (C++/CLI)
Im generischen Typ oder Methodendeklarationen können Sie einen Typparameter mit Einschränkungen qualifizieren. Eine Einschränkung ist erforderlich, die Typen als Typargumente verwendet erfüllen müssen. Z. B. möglicherweise eine Einschränkung, dass das Typargument eine bestimmte Schnittstelle implementieren oder von einer bestimmten Klasse erben muss.  
  
 Einschränkungen sind optional. eine Einschränkung für einen Parameter nicht angegeben ist gleichbedeutend mit diesen Parameter auf einschränken <xref:System.Object>.  
  
## <a name="syntax"></a>Syntax  
  
```  
where type-parameter: constraint list  
```  
  
#### <a name="parameters"></a>Parameter  
 *Type-parameter*  
 Einer der Typparameter eingeschränkt werden.  
  
 *Einschränkungsliste*  
 *Einschränkungsliste* ist eine durch Trennzeichen getrennte Liste der Einschränkung-Spezifikationen. Die Liste zählen Schnittstellen, die durch den Typparameter implementiert werden.  
  
 Die Liste kann auch eine Klasse enthalten. Für das Typargument eine basisklasseneinschränkung erfüllen muss es derselben Klasse wie die Einschränkung oder von der Einschränkung abgeleitet werden.  
  
 Sie können auch angeben, `gcnew()` an, dass das Typargument muss einen öffentlichen parameterlosen Konstruktor; haben oder **Verweisklasse** an, dass der Typ Argument muss ein Verweistyp, einschließlich jeder Klasse, Schnittstelle, Delegat oder Array sein -Typ oder **Wertklasse** an, dass der Typ das Argument muss ein Werttyp sein. Jeder Werttyp außer Nullable\<T > kann angegeben werden.  
  
 Sie können auch einen generischen Parameter als Einschränkung angeben. Das Typargument für den Typ angegeben, dass Sie typisiert werden kann oder Ableitung vom Typ der Einschränkung. Dies ist eine Einschränkung für einen reinen bezeichnet.  
  
## <a name="remarks"></a>Hinweise  
 Die Einschränkungsklausel besteht aus **, in denen** gefolgt von einem Typparameter, der einen Doppelpunkt (**:**), und die Einschränkung, die die Art der Einschränkung des Typparameters angibt. **wo** ist ein kontextbezogenes Schlüsselwort; Siehe [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md) für Weitere Informationen. Trennen Sie mehrere **, in denen** Klauseln mit einem Leerzeichen.  
  
 Einschränkungen werden angewendet, um die Typparameter um Einschränkungen für die Typen zu platzieren, die als Argumente für einen generischen Typ oder Methode verwendet werden kann.  
  
 Klassen- und schnittstelleneinschränkungen angeben, dass die Argumenttypen müssen oder von einer angegebenen Klasse erben oder implementieren eine angegebene Schnittstelle.  
  
 Das Anwenden von Einschränkungen auf einer generischen Typ- oder kann es sich um Code in diesen Typ oder Methode, die bekannte Features der eingeschränkten Typen nutzen. Sie können z. B. eine generische Klasse deklarieren, dass der Typparameter implementiert die `IComparable<T>` Schnittstelle:  
  
```cpp  
// generics_constraints_1.cpp  
// compile with: /c /clr  
using namespace System;  
generic <typename T>  
where T : IComparable<T>  
ref class List {};  
```  
  
 Diese Einschränkung ist erforderlich, dass ein Typargument für verwendet `T` implementiert `IComparable<T>` zum Zeitpunkt der Kompilierung. Sie können außerdem Schnittstellenmethoden, z. B. `CompareTo`, aufgerufen werden. In einer Instanz des Typparameters ist keine Umwandlung erforderlich, Schnittstellenmethoden aufrufen.  
  
 Statische Methoden in den Typ des Arguments-Klasse können nicht durch den Typparameter nicht aufgerufen werden; Sie können nur über den tatsächlichen benannten Typ aufgerufen werden.  
  
 Eine Einschränkung handelt es sich nicht um einen Werttyp, einschließlich integrierte Typen wie z. B. **Int** oder **doppelte**. Da Werttypen können keine Klassen abgeleitet haben, würde nur eine Klasse jemals die Einschränkung zu erfüllen können. In diesem Fall kann die generische zusammen mit dem Typparameter ersetzt werden, durch den bestimmten Werttyp umgeschrieben werden.  
  
 Einschränkungen sind in einigen Fällen erforderlich, da der Compiler nicht die Verwendung von Methoden oder andere Features eines unbekannten Typs werden kann, wenn die Einschränkungen impliziert, dass es sich bei der unbekannte Typ die Methoden oder Schnittstellen unterstützt.  
  
 Mehrere Einschränkungen für den gleichen Typparameter können in eine durch Trennzeichen getrennte Liste angegeben werden  
  
```cpp  
// generics_constraints_2.cpp  
// compile with: /c /clr  
using namespace System;  
using namespace System::Collections::Generic;  
generic <typename T>  
where T : List<T>, IComparable<T>  
ref class List {};  
```  
  
 Bei mehreren Typparametern, verwenden Sie eine **, in denen** -Klausel für jeden Typparameter. Zum Beispiel:  
  
```cpp  
// generics_constraints_3.cpp  
// compile with: /c /clr  
using namespace System;  
using namespace System::Collections::Generic;  
  
generic <typename K, typename V>  
   where K: IComparable<K>  
   where V: IComparable<K>  
ref class Dictionary {};  
```  
  
 Zusammenfassend lässt sich sagen, verwenden Sie Einschränkungen in Ihrem Code gemäß den folgenden Regeln:  
  
-   Wenn mehrere Einschränkungen aufgeführt sind, können die Einschränkungen in beliebiger Reihenfolge aufgeführt.  
  
-   Einschränkungen können auch Klassentypen, z. B. abstrakte Basisklassen sein. Allerdings können keine Einschränkungen Werttypen oder versiegelte Klassen sein.  
  
-   Einschränkungen können sich selbst nicht Typparameter, aber sie können die Typparameter in offenen konstruierten Typen umfassen. Zum Beispiel:  
  
    ```cpp  
    // generics_constraints_4.cpp  
    // compile with: /c /clr  
    generic <typename T>  
    ref class G1 {};  
  
    generic <typename Type1, typename Type2>  
    where Type1 : G1<Type2>   // OK, G1 takes one type parameter  
    ref class G2{};  
    ```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt das Aufrufen von Instanzmethoden für Typparameter mit Einschränkungen.  
  
```cpp  
// generics_constraints_5.cpp  
// compile with: /clr  
using namespace System;  
  
interface class IAge {  
   int Age();  
};  
  
ref class MyClass {  
public:  
   generic <class ItemType> where ItemType : IAge   
   bool isSenior(ItemType item) {  
      // Because of the constraint,  
      // the Age method can be called on ItemType.  
      if (item->Age() >= 65)   
         return true;  
      else  
         return false;  
   }  
};  
  
ref class Senior : IAge {  
public:  
   virtual int Age() {  
      return 70;  
   }  
};  
  
ref class Adult: IAge {  
public:  
   virtual int Age() {  
      return 30;  
   }  
};  
  
int main() {  
   MyClass^ ageGuess = gcnew MyClass();  
   Adult^ parent = gcnew Adult();  
   Senior^ grandfather = gcnew Senior();  
  
   if (ageGuess->isSenior<Adult^>(parent))  
      Console::WriteLine("\"parent\" is a senior");  
   else  
      Console::WriteLine("\"parent\" is not a senior");  
  
   if (ageGuess->isSenior<Senior^>(grandfather))  
      Console::WriteLine("\"grandfather\" is a senior");  
   else  
      Console::WriteLine("\"grandfather\" is not a senior");  
}  
```  
  
```Output  
"parent" is not a senior  
"grandfather" is a senior  
```  
  
## <a name="example"></a>Beispiel  
 Wenn ein generischer Typparameter als Einschränkung verwendet wird, spricht man von einer reinen typeinschränkung. Naked-typeinschränkungen sind nützlich, wenn eine Memberfunktion mit ihren eigenen Typparameter dieser Parameter auf den Typparameter des enthaltenden Typs einschränken muss.  
  
 Im folgenden Beispiel `T` ein naked typconstraint im Kontext der `Add` Methode.  
  
 Naked-typeinschränkungen können auch in generischen Klassendefinitionen verwendet werden. Das Verwenden von naked-typeinschränkungen für generische Klassen ist beschränkt, da der Compiler keine Informationen über eine Einschränkung für einen reinen annehmen kann, außer dass es abgeleitet <xref:System.Object>. Verwenden Sie naked-typeinschränkungen in generischen Klassen in Szenarien, in denen Sie eine vererbungsbeziehung zwischen zwei Typparametern erzwingen möchten.  
  
```cpp  
// generics_constraints_6.cpp  
// compile with: /clr /c  
generic <class T>  
ref struct List {  
   generic <class U>  
   where U : T  
   void Add(List<U> items)  {}  
};  
  
generic <class A, class B, class C>  
where A : C  
ref struct SampleClass {};  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Generika](../windows/generics-cpp-component-extensions.md)