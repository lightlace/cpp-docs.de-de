---
title: "How to: Improve Performance with Generics (Visual C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "performance, C++"
  - "Visual C++, performance"
  - "Visual C++, generics"
  - "generics [C++], performance"
ms.assetid: f14a175b-301f-46cc-86e4-c82d35f9aa3e
caps.latest.revision: 7
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Improve Performance with Generics (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit Generika können Sie wiederverwendbaren Code auf einem Typparameter erstellen.  Der tatsächliche Typ des Typparameters wird verzögert, bis vom Clientcode aufgerufen.  Weitere Informationen zu Generika finden Sie unter [Generics](../windows/generics-cpp-component-extensions.md).  
  
 Dieser Artikel wird erläutert, wie Generika unterstützen, kann die Leistung einer Anwendung zu erhöhen, die Auflistungen verwendet.  
  
## Beispiel  
 . .NET Framework beinhaltet vielen Auflistungsklassen im <xref:System.Collections?displayProperty=fullName>\-Namespace.  Die meisten dieser Auflistungen können auf Objekte des Typs <xref:System.Object?displayProperty=fullName> angewendet.  Dadurch können Auflistungen, um alle Typen zu speichern, da alle Typen in .NET Framework, sogar Werttypen, werden von <xref:System.Object?displayProperty=fullName> abgeleitet.  Es gibt jedoch zwei Nachteile zu dieser Vorgehensweise.  
  
 Erstens wird die Auflistung Werttypen wie ganze Zahlen gespeichert werden, muss der Wert geschachtelt werden, bevor sie der Auflistung hinzugefügt wird und konvertiert wird, wenn der Wert aus der Auflistung abgerufen wird.  Diese sind speicherintensive Vorgänge.  
  
 Zweitens gibt es keine Möglichkeit zu steuern, die, kann einer Auflistung hinzugefügt werden.  Sie ist perfekt gültig, eine ganze Zahl und eine Zeichenfolge der gleichen Auflistung hinzuzufügen, obwohl dies wahrscheinlich nicht, was vorgesehen war.  Daher damit der Code typsicher sein, muss überprüft, ob der Typ, der aus der Auflistung abgerufen wird, ist das, was tatsächlich erwartet wurde.  
  
 Im folgenden Codebeispiel werden die beiden Hauptnachteile .NET Framework\-Auflistungen vor Generika an.  
  
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
  
  **Holte eine Zeichenfolge: Sieben**  
**Holte int: 7**   
## Beispiel  
 Der neue <xref:System.Collections.Generic?displayProperty=fullName>\-Namespace enthält viele derselben Auflistungen, die im Namespace <xref:System.Collections?displayProperty=fullName> gefunden werden, aber diese wurden geändert, um generische Typparameter zu akzeptieren.  Dadurch entfällt die zwei Nachteile von nicht generischen Auflistungen: das Boxing und Unboxing das von Werttypen und das Unvermögen, den in den Auflistungen gespeichert werden Typen anzugeben.  Vorgänge in den beiden Auflistungen sind identisch; unterscheiden sich nur in, wie sie instanziiert werden.  
  
 Vergleichen Sie das Beispiel, das oben mit diesem Beispiel geschrieben wird, die eine generische <xref:System.Collections.Generic.Stack`1>\-Auflistung verwendet.  Auf große Auflistungen, die oft frequentiert sind, ist die Leistung des Beispiels deutlich größer als das vorangehende Beispiel.  
  
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
  
  **14**   
## Siehe auch  
 [Generics](../windows/generics-cpp-component-extensions.md)