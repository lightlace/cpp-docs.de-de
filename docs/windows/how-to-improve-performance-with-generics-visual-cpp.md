---
title: 'Vorgehensweise: Verbessern der Leistung mit Generika (Visual C++) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- performance, C++
- Visual C++, performance
- Visual C++, generics
- generics [C++], performance
ms.assetid: f14a175b-301f-46cc-86e4-c82d35f9aa3e
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8d8aad77236e5c1b2cdc8fe5958d87d8c53b8f05
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-improve-performance-with-generics-visual-c"></a>Gewusst wie: Verbessern der Leistung mit Generika (Visual C++)
Mit Generika können Sie wiederverwendbaren Code, die auf einem Typparameter basierenden erstellen. Der tatsächliche Typ des Typparameters wird verzögert, bis von Clientcode aufgerufen. Weitere Informationen zu Generika finden Sie unter [Generika](../windows/generics-cpp-component-extensions.md).  
  
 In diesem Artikel wird erläutert, wie Generika zur Verbesserung der Leistung einer Anwendung, die Auflistungen verwendet.  
  
## <a name="example"></a>Beispiel  
 Viele Auflistungsklassen in .NET Framework enthält die <xref:System.Collections?displayProperty=fullName> Namespace. Die meisten dieser Auflistungen arbeiten mit Objekten des Typs <xref:System.Object?displayProperty=fullName>. Auf diese Weise können Auflistungen zum Speichern von beliebigen Typs, da alle Typen in .NET Framework auch Werttypen abgeleitet sein <xref:System.Object?displayProperty=fullName>. Es gibt jedoch zwei Nachteile dieser Vorgehensweise.  
  
 Zuerst, wenn die Auflistung Werttypen wie ganzen Zahlen gespeichert ist, der Wert muss mittels Boxing konvertiert, bevor Sie der Auflistung hinzugefügt werden und mittels Unboxing zurückkonvertiert, wenn der Wert aus der Auflistung abgerufen wird. Hierbei handelt es sich um kostenintensive Vorgänge.  
  
 Zweitens besteht keine Möglichkeit, die steuern, welche Typen für eine Sammlung hinzugefügt werden können. Es ist durchaus zulässig, eine ganze Zahl und eine Zeichenfolge in die gleiche Sammlung hinzufügen, obwohl dies ist wahrscheinlich nicht beabsichtigt war. Damit für Ihren Code typsicher sein können, müssen Sie daher überprüfen Sie, ob der Typ, der aus der Auflistung abgerufen wirklich Inhalte als erwartet wurde.  
  
 Im folgenden Codebeispiel wird veranschaulicht, die zwei wichtigsten vor-und Nachteile von .NET Framework-Auflistungen vor Generika.  
  
```  
// perf_pre_generics.cpp  
// compile with: /clr  
  
using namespace System;  
using namespace System::Collections;  
  
int main()  
{  
    // This Stack can contain any type.  
    Stack ^s = gcnew Stack();  
  
    // Push an integer to the Stack.  
    // A boxing operation is performed here.  
    s->Push(7);  
  
    // Push a String to the same Stack.  
    // The Stack now contains two different data types.  
    s->Push("Seven");  
  
    // Pop the items off the Stack.  
    // The item is returned as an Object, so a cast is  
    // necessary to convert it to its proper type.  
    while (s->Count > 0)  
    {  
        Object ^o = s->Pop();  
        if (o->GetType() == Type::GetType("System.String"))  
        {  
            Console::WriteLine("Popped a String: {0}", (String ^)o);  
        }  
        else if (o->GetType() == Type::GetType("System.Int32"))  
        {  
            Console::WriteLine("Popped an int: {0}", (int)o);  
        }  
        else  
        {  
            Console::WriteLine("Popped an unknown type!");  
        }  
    }  
}  
```  
  
```Output  
Popped a String: Seven  
Popped an int: 7  
```  
  
## <a name="example"></a>Beispiel  
 Die neue <xref:System.Collections.Generic?displayProperty=fullName> -Namespace enthält viele der gleichen Sammlungen finden der <xref:System.Collections?displayProperty=fullName> -Namespace, jedoch auf generische Parameter akzeptieren geändert wurden. Diese Auswertung eliminiert die zwei Nachteile von nicht-generische Auflistungen: das Boxing und unboxing eines Werttypen und der Unfähigkeit, die Typen anzugeben, in den Auflistungen gespeichert werden. Vorgänge für die beiden Auflistungen sind identisch. Sie unterscheiden sich nur in der Weise, wie sie instanziiert werden.  
  
 Vergleichen Sie das Beispiel oben mit diesem Beispiel für die Verwendung einen generischen geschrieben <xref:System.Collections.Generic.Stack%601> Auflistung. Auf große Sammlungen, die häufig zugegriffen werden, werden in diesem Beispiel wird die Leistung erheblich größer als das vorhergehende Beispiel.  
  
```  
// perf_post_generics.cpp  
// compile with: /clr  
  
#using <System.dll>  
  
using namespace System;  
using namespace System::Collections::Generic;  
  
int main()  
{  
    // This Stack can only contain integers.  
    Stack<int> ^s = gcnew Stack<int>();  
  
    // Push an integer to the Stack.  
    // A boxing operation is performed here.  
    s->Push(7);  
    s->Push(14);  
  
    // You can no longer push a String to the same Stack.  
    // This will result in compile time error C2664.  
    //s->Push("Seven");  
  
    // Pop an item off the Stack.  
    // The item is returned as the type of the collection, so no  
    // casting is necessary and no unboxing is performed for  
    // value types.  
    int i = s->Pop();  
    Console::WriteLine(i);  
  
    // You can no longer retrieve a String from the Stack.  
    // This will result in compile time error C2440.  
    //String ^str = s->Pop();  
}  
```  
  
```Output  
14  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Generika](../windows/generics-cpp-component-extensions.md)