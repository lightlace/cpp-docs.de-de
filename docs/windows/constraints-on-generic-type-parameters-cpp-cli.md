---
title: "Einschränkungen für generische Typparameter (C + c++ / CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: where
dev_langs: C++
helpviewer_keywords:
- where keyword [C++]
- constraints, C++
ms.assetid: eb828cc9-684f-48a3-a898-b327700c0a63
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e59c5ecb6101667c7d8546afcc6cbbfb9e024488
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="constraints-on-generic-type-parameters-ccli"></a>Einschränkungen für generische Typparameter (C++/CLI)
Im generischen Typ oder die Methodendeklarationen können Sie einen Typparameter mit Einschränkungen qualifizieren. Eine Einschränkung ist erforderlich, die Typen als Typargumente verwendet erfüllen müssen. Z. B. möglicherweise eine Einschränkung, dass das Typargument eine bestimmte Schnittstelle implementieren oder von einer bestimmten Klasse erben muss.  
  
 Einschränkungen sind optional. eine Einschränkung für einen Parameter nicht angegeben ist gleichbedeutend mit diesen Parameter auf einschränken <xref:System.Object>.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
where type-parameter: constraint list  
```  
  
#### <a name="parameters"></a>Parameter  
 *Type-parameter*  
 Einer der Typparameter eingeschränkt wird.  
  
 *Einschränkungsliste*  
 *Einschränkungsliste* ist eine durch Trennzeichen getrennte Liste der Einschränkung-Spezifikationen. Die Liste zählen Schnittstellen, die durch den Typparameter implementiert werden.  
  
 Die Liste kann auch eine Klasse enthalten. Für das Typargument eine Basisklasse Einschränkung nicht erfüllen muss es derselben Klasse wie die Einschränkung oder die Einschränkung abgeleitet.  
  
 Sie können auch angeben, `gcnew()` an, dass das Typargument muss einen öffentlichen parameterlosen Konstruktor; haben oder `ref class` an, dass das Typargument muss ein Verweistyp, einschließlich einer Klasse, Schnittstelle, Delegat oder Arraytyp; oder `value class` an Geben Sie das Typargument ein Werttyp sein muss. Jeder Werttyp außer Nullable\<T > angegeben werden können.  
  
 Sie können auch einen generischen Parameter als Einschränkung angeben. Das Typargument für den Typ angegeben, dass Sie typisiert sind muss sein oder vom Typ der Einschränkung abgeleitet werden. Dies ist eine Einschränkung für einen naked bezeichnet.  
  
## <a name="remarks"></a>Hinweise  
 Besteht aus die Constraint-Klausel **, in denen** gefolgt von einem Type-Parameter, einen Doppelpunkt (**:**), und die Einschränkung, der angibt, die Art der Einschränkung für den Typparameter angeben. **wobei** ist ein kontextbezogenes Schlüsselwort; Siehe [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md) für Weitere Informationen. Trennen Sie mehrere **, in denen** Klauseln mit einem Leerzeichen.  
  
 Einschränkungen werden angewendet, um die Typparameter Platzierung von Einschränkungen auf die Typen, die als Argumente für einen generischen Typ oder Methode verwendet werden kann.  
  
 Klassen- und schnittstelleneinschränkungen angeben, dass die Argumenttypen müssen sein oder von einer angegebenen Klasse erben und eine angegebene Schnittstelle implementieren.  
  
 Das Anwenden von Einschränkungen auf einen generischen Typ oder Methode kann es sich um Code in den Typ oder Methode, die bekannten Funktionen von eingeschränkten Typen nutzen. Sie können beispielsweise eine generische Klasse deklarieren, so, dass der Typparameter implementiert die **"IComparable"\<T >** Schnittstelle:  
  
```  
// generics_constraints_1.cpp  
// compile with: /c /clr  
using namespace System;  
generic <typename T>  
where T : IComparable<T>  
ref class List {};  
```  
  
 Diese Einschränkung ist erforderlich, dass ein Typargument für verwendet `T` implementiert `IComparable<T>` zum Zeitpunkt der Kompilierung. Sie können auch Methoden der Schnittstelle, wie z. B. **CompareTo**, aufgerufen werden. In einer Instanz des Typparameters ist keine Typumwandlung erforderlich, Schnittstellenmethoden aufrufen.  
  
 Statische Methoden in das Typargument Klasse können nicht durch den Typparameter aufgerufen werden. Sie können nur durch den tatsächlichen benannten Typ aufgerufen werden.  
  
 Eine Einschränkung handelt es sich nicht um einen Werttyp ist, einschließlich integrierte Typen wie z. B. `int` oder **doppelte**. Da Werttypen Klassen abgeleitet haben können, würde nur eine Klasse jemals die Einschränkung erfüllen können. In diesem Fall kann die generische mit den Typparameter ersetzt wird, durch den bestimmte Werttyp umgeschrieben werden.  
  
 Einschränkungen sind in einigen Fällen erforderlich, da der Compiler die Verwendung von Methoden oder andere Features eines unbekannten Typs dürfen, es sei denn, die Einschränkungen impliziert, dass der unbekannte Typ auf die Methoden oder Schnittstellen unterstützt.  
  
 In einer durch Trennzeichen getrennte Liste können mehrere Einschränkungen für den gleichen Typparameter angegeben werden  
  
```  
// generics_constraints_2.cpp  
// compile with: /c /clr  
using namespace System;  
using namespace System::Collections::Generic;  
generic <typename T>  
where T : List<T>, IComparable<T>  
ref class List {};  
```  
  
 Mit mehreren Typparametern, verwenden Sie eine **, in dem** -Klausel für jeden Typparameter. Zum Beispiel:  
  
```  
// generics_constraints_3.cpp  
// compile with: /c /clr  
using namespace System;  
using namespace System::Collections::Generic;  
  
generic <typename K, typename V>  
   where K: IComparable<K>  
   where V: IComparable<K>  
ref class Dictionary {};  
```  
  
 Zusammenfassend gilt: Verwenden Sie Einschränkungen in Ihrem Code anhand der folgenden Regeln:  
  
-   Wenn mehrere Einschränkungen aufgelistet sind, können die Einschränkungen in beliebiger Reihenfolge aufgelistet werden.  
  
-   Einschränkungen können auch Klassentypen, z. B. abstrakte Basisklassen sein. Allerdings können keine Einschränkungen Werttypen oder versiegelte Klassen sein.  
  
-   Einschränkungen können selbst nicht Typparameter, jedoch können sie die Typparameter in einen offenen konstruierten Typ beinhalten. Zum Beispiel:  
  
    ```  
    // generics_constraints_4.cpp  
    // compile with: /c /clr  
    generic <typename T>  
    ref class G1 {};  
  
    generic <typename Type1, typename Type2>  
    where Type1 : G1<Type2>   // OK, G1 takes one type parameter  
    ref class G2{};  
    ```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie mit Einschränkungen für Typparameter Instanzmethoden aufrufen.  
  
```  
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
 Wenn ein generischer Typparameter als Einschränkung verwendet wird, ist es eine Einschränkung für einen naked aufgerufen. Naked typeinschränkungen sind nützlich, wenn eine Memberfunktion mit einem eigenen Typparameter, die diesen Parameter an den Typparameter der enthaltenden Typs zu beschränken muss.  
  
 Im folgenden Beispiel wird T naked eine Einschränkung für einen im Kontext der Add-Methode.  
  
 Typeinschränkungen für naked-können auch im Allgemeinen Klassendefinitionen verwendet werden. Die Nützlichkeit der naked typeinschränkungen mit generischen Klassen ist beschränkt, da der Compiler keinerlei wissen über eine Einschränkung für einen naked übernehmen kann, mit dem Unterschied, dass es abgeleitet <xref:System.Object>. Verwenden Sie naked typeinschränkungen in generischen Klassen in Szenarien, in denen Sie eine vererbungsbeziehung zwischen zwei Typparameter erzwingen möchten.  
  
```  
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