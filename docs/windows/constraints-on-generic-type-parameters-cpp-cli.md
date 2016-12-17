---
title: "Constraints on Generic Type Parameters (C++/CLI)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "where"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "where keyword [C++]"
  - "constraints, C++"
ms.assetid: eb828cc9-684f-48a3-a898-b327700c0a63
caps.latest.revision: 25
caps.handback.revision: "23"
ms.author: "mblome"
manager: "ghogen"
---
# Constraints on Generic Type Parameters (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

im generischen Typ oder in den Methodendeklarationen können Sie einen Typparameter mit Einschränkungen qualifizieren.  Eine Einschränkung ist eine Anforderung, die Typen verwenden, z Typargumente erfüllen müssen.  Beispielsweise könnte eine Einschränkung, dass das Typargument eine bestimmte Schnittstelle implementiert oder von einer bestimmten Klasse erben muss.  
  
 Beschränkungen sind optional; einer Einschränkung auf einen Parameter nicht anzugeben ist zum Einschränken dieser Parameter entspricht <xref:System.Object>.  
  
## Syntax  
  
```  
  
where type-parameter: constraint list  
```  
  
#### Parameter  
 *Typparameter*  
 Einer der Typparameter, beschränkt werden.  
  
 *Einschränkungsliste*  
 *Einschränkungsliste* ist eine durch Trennzeichen getrennte Liste der Einschränkungsspezifikation.  Die Liste kann die durch den Typparameter implementiert werden Schnittstellen schließen.  
  
 Die Liste kann auch eine Klasse enthalten.  Damit das Typargument erfüllt eine Basisklasseneinschränkung, muss er die gleiche Klasse der Einschränkung sein oder von der Einschränkung berechnen.  
  
 Sie können auch `gcnew()` angeben, um das Typargument angeben müssen einen öffentlichen parameterlosen Konstruktor besitzen; oder `ref class`, um anzugeben Typargument muss ein Verweistyp, einschließlich jeder Klasse, Schnittstelle, Delegaten oder Arraytyp sein; oder `value class`, um anzugeben Typargument muss ein Werttyp sein.  Ein beliebiger Werttyp außer NullableT \<\> kann angegeben werden.  
  
 Sie können einen generischen Parameter als Einschränkung auch angeben.  Das Typargument, das für den Typ angegeben wird, dass, Sie einschränken, muss den Typ der Einschränkung sein oder leiten.  Dies ist einer nackten Typeinschränkung aufgerufen.  
  
## Hinweise  
 Die Einschränkungsklausel besteht aus **where**, das von einem Typparameter, einem Doppelpunkt \(**:**\) gefolgt und der Einschränkung, die die Art der Einschränkung für die Typparameter angeben.  **where**  ist ein Schlüsselwort kontextbezogenes; Weitere Informationen finden Sie unter [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md).  Trennen Sie mehrere **where**\-Klauseln mit einem Leerzeichen.  
  
 Einschränkungen werden den Typparameter angewendet, um Einschränkungen auf Typen zu platzieren, die als Argumente für einen generischen Typ oder eine Methode verwendet werden können.  
  
 Klassen\- und Schnittstelleneinschränkungen geben an, dass die Argumenttypen einer angegebenen Klasse sein oder erben oder eine angegebene Schnittstelle implementieren müssen.  
  
 Die Anwendung von Beschränkungen einem generischen Typ oder einer Methode können Code in diesem Typ oder in Methode, um die bekannten Funktionen der eingeschränkten Typen nutzen.  Beispielsweise können Sie eine generische Klasse deklarieren, sodass die Typparameterwerkzeuge die Schnittstelle **IComparable \<T\>**:  
  
```  
// generics_constraints_1.cpp  
// compile with: /c /clr  
using namespace System;  
generic <typename T>  
where T : IComparable<T>  
ref class List {};  
```  
  
 Diese Einschränkung erfordert, dass ein Typargument, das für  `T` verwendet wird, `IComparable<T>` zur Kompilierzeit implementiert.  Es können sich Schnittstellenmethoden, wie **CompareTo**, aufgerufen werden.  Keine Umwandlung wird auf eine Instanz des Typparameters erforderlich, um Schnittstellenmethoden aufzurufen.  
  
 Statische Methoden in der Klasse des Typarguments können nicht durch den Typparameter aufgerufen werden; Sie können nur vom tatsächlichen benannten Typ aufgerufen werden.  
  
 Eine Einschränkung kann kein Werttyp, z integrierte Datentypen \(wie `int` oder **double** sein.  Da Werttypen abgeleiteten Klassen besitzen können, nur einer Klasse vorhanden\) in der Lage wäre, die Einschränkung zu erfüllen.  In diesem Fall können das generische mit dem Typparameter umgeschrieben werden, der von bestimmten Werttyp ersetzt wird.  
  
 Einschränkungen werden in einigen Fällen erforderlich, da der Compiler nicht die Verwendung von Methoden oder andere Features eines unbekannten Typ zulässig, es sei denn, die Einschränkungen bedeuten, dass der Typ die unbekannte Methoden oder Schnittstellen unterstützt.  
  
 Mehrere Einschränkungen für den gleichen Typparameter können in einer durch Trennzeichen getrennten Liste angegeben werden  
  
```  
// generics_constraints_2.cpp  
// compile with: /c /clr  
using namespace System;  
using namespace System::Collections::Generic;  
generic <typename T>  
where T : List<T>, IComparable<T>  
ref class List {};  
```  
  
 Wenn mehrere Typparameter verwenden Sie **where** eine Klausel für jeden Typparameter.  Beispiel:  
  
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
  
 So zusammenfassen, Einschränkungen im Code entsprechend den folgenden Regeln verwenden:  
  
-   Wenn mehrere Einschränkungen aufgeführt sind, werden die Einschränkungen in beliebiger Reihenfolge aufgeführt werden.  
  
-   Einschränkungen können Klassentypen, wie abstrakte Basisklassen auch sein.  Sie können Einschränkungen nicht Werttypen oder versiegelte Klasse sein.  
  
-   Einschränkungen können nicht auch Typparameter sein, aber sie können die Typparameter in einen offenen generischen Typ einschließen.  Beispiel:  
  
    ```  
    // generics_constraints_4.cpp  
    // compile with: /c /clr  
    generic <typename T>  
    ref class G1 {};  
  
    generic <typename Type1, typename Type2>  
    where Type1 : G1<Type2>   // OK, G1 takes one type parameter  
    ref class G2{};  
    ```  
  
## Beispiel  
 Im folgenden Beispiel wird mit Einschränkungen, Instanzmethoden für Typparameter aufzurufen.  
  
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
  
  **"übergeordnete" kein Senior**  
**"" ist ein Großvater Senior**   
## Beispiel  
 Wenn ein generischer Typparameter als Einschränkung verwendet wird, wird es einer nackten Typeinschränkung aufgerufen.  Nackte Typeinschränkungen sind nützlich, wenn eine Memberfunktion mit eigenen Typparameter dass Parameter dem Typparameter der enthaltenden Typen einzuschränken.  
  
 Im folgenden Beispiel ist T einer nackten Typeinschränkung im Kontext der Add\-Methode.  
  
 Nackte Typeinschränkungen können in generischen Klassendefinitionen auch verwendet werden.  Die Nützlichkeit von naked\-Funktion Typeinschränkungen mit generischen Klassen ist eingeschränkt, da der Compiler keine zu einer nackten Typeinschränkung davon ausgehen kann, dass sie von <xref:System.Object> abgeleitet.  Verwenden Sie nackte Typeinschränkungen für generische Klassen in Szenarien, in denen eine Vererbungsbeziehung zwischen zwei Typparametern erzwingen möchten.  
  
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
  
## Siehe auch  
 [Generics](../windows/generics-cpp-component-extensions.md)