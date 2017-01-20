---
title: "Generic Interfaces (Visual C++)"
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
  - "generic interfaces"
  - "interfaces, generic [C++}"
ms.assetid: f3da788a-ba83-4db7-9dcf-9b95a8fb9d1a
caps.latest.revision: 21
caps.handback.revision: "19"
ms.author: "mblome"
manager: "ghogen"
---
# Generic Interfaces (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Einschränkungen, die für Typparameter auf Klassen anwenden, sind identisch, die, die die Typparameter, die auf Schnittstellen anwenden \( [Generic Classes \(C\+\+\/CLI\)](../windows/generic-classes-cpp-cli.md)\).  
  
 Die Regeln, dass Kontrollfunktionsüberladen das entspricht für Funktionen innerhalb der generischen Klassen bzw. der generischen Schnittstellen sind.  
  
 Explizite Schnittstellenmemberimplementierungen arbeiten mit erstellten Schnittstellentypen ebenso wie einfache Schnittstellentypen \(siehe folgende Beispiele\).  
  
 Weitere Informationen zu Schnittstellen, finden Sie unter [interface class](../windows/interface-class-cpp-component-extensions.md).  
  
## Syntax  
  
```  
[attributes] generic <class-key type-parameter-identifier[, ...]>  
[type-parameter-constraints-clauses][accesibility-modifiers] interface class identifier [: base-list] {   interface-body} [declarators] ;  
```  
  
## Hinweise  
 *Attribute* \(optional\)  
 Zusätzliche deklarative Informationen.  Weitere Informationen zu Attributen und Attributklassen, finden Sie Attribute.  
  
 *class\-key*  
 **Klasse** oder **typename**  
  
 `type-parameter-identifier(s)`  
 Durch Trennzeichen getrennte Bezeichnerliste.  
  
 `type-parameter-constraints-clauses`  
 Nimmt die Form auf, die in [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../windows/constraints-on-generic-type-parameters-cpp-cli.md) angegeben  
  
 *BarrierefreiheitModifizierer* \(optional\)  
 Zugriffsmodifizierer \(z.  **public, private**\).  
  
 *Bezeichner \(identifier\)*  
 Beim Schnittstellennamen.  
  
 *BasisListe* \(optional\)  
 Eine Liste, die eine oder mehrere Basisschnittstellen expliziten durch Trennzeichen getrennten enthält.  
  
 *SchnittstelleText*  
 Deklarationen der Schnittstellenmember.  
  
 *Deklaratoren* \(optional\)  
 Deklarationen von Variablen auf diesem Typ.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie eine generische Schnittstelle deklariert und instanziiert.  Im Beispiel wird die generische `IList<ItemType>`\-Schnittstelle deklariert.  Sie wird durch zwei generische Klassen, `List1<ItemType>` und `List2<ItemType>`, mit verschiedenen Implementierungen implementiert.  
  
```  
// generic_interface.cpp  
// compile with: /clr  
using namespace System;  
  
// An exception to be thrown by the List when  
// attempting to access elements beyond the  
// end of the list.  
ref class ElementNotFoundException : Exception {};  
  
// A generic List interface  
generic <typename ItemType>  
public interface class IList {  
   ItemType MoveFirst();  
   bool Add(ItemType item);  
   bool AtEnd();  
   ItemType Current();  
   void MoveNext();  
};  
  
// A linked list implementation of IList  
generic <typename ItemType>  
public ref class List1 : public IList<ItemType> {  
   ref class Node {  
      ItemType m_item;  
  
   public:  
      ItemType get_Item() { return m_item; };  
      void set_Item(ItemType value) { m_item = value; };  
  
      Node^ next;  
  
      Node(ItemType item) {  
         m_item = item;  
         next = nullptr;  
      }  
   };  
  
   Node^ first;  
   Node^ last;  
   Node^ current;  
  
   public:  
   List1() {  
      first = nullptr;  
      last = first;  
      current = first;  
   }  
  
   virtual ItemType MoveFirst() {  
      current = first;  
      if (first != nullptr)  
        return first->get_Item();  
      else  
         return ItemType();  
   }  
  
   virtual bool Add(ItemType item) {  
      if (last != nullptr) {   
         last->next = gcnew Node(item);  
         last = last->next;  
      }  
      else {  
         first = gcnew Node(item);  
         last = first;  
         current = first;  
      }  
      return true;  
   }  
  
   virtual bool AtEnd() {  
      if (current == nullptr )  
        return true;  
      else   
        return false;  
   }  
  
   virtual ItemType Current() {  
       if (current != nullptr)  
         return current->get_Item();  
       else  
         throw gcnew ElementNotFoundException();  
   }  
  
   virtual void MoveNext() {  
      if (current != nullptr)  
       current = current->next;  
      else  
        throw gcnew ElementNotFoundException();  
   }  
};  
  
// An array implementation of IList  
generic <typename ItemType>  
ref class List2 : public IList<ItemType> {  
   array<ItemType>^ item_array;  
   int count;  
   int current;  
  
   public:  
  
   List2() {  
      // not yet possible to declare an  
      // array of a generic type parameter  
      item_array = gcnew array<ItemType>(256);  
      count = current = 0;  
   }  
  
   virtual ItemType MoveFirst() {  
      current = 0;  
      return item_array[0];  
   }  
  
   virtual bool Add(ItemType item) {  
      if (count < 256)  
         item_array[count++] = item;  
      else  
        return false;  
      return true;  
   }  
  
   virtual bool AtEnd() {  
      if (current >= count)  
        return true;  
      else  
        return false;  
   }  
  
   virtual ItemType Current() {  
      if (current < count)  
        return item_array[current];  
      else  
        throw gcnew ElementNotFoundException();  
   }  
  
   virtual void MoveNext() {  
      if (current < count)   
         ++current;  
      else  
         throw gcnew ElementNotFoundException();  
   }  
};  
  
// Add elements to the list and display them.  
generic <typename ItemType>  
void AddStringsAndDisplay(IList<ItemType>^ list, ItemType item1, ItemType item2) {  
   list->Add(item1);  
   list->Add(item2);  
   for (list->MoveFirst(); ! list->AtEnd(); list->MoveNext())  
     Console::WriteLine(list->Current());  
}  
  
int main() {  
   // Instantiate both types of list.  
  
   List1<String^>^ list1 = gcnew List1<String^>();  
   List2<String^>^ list2 = gcnew List2<String^>();  
  
   // Use the linked list implementation of IList.  
   AddStringsAndDisplay<String^>(list1, "Linked List", "List1");  
  
   // Use the array implementation of the IList.  
   AddStringsAndDisplay<String^>(list2, "Array List", "List2");  
}  
```  
  
  **Verknüpfte Liste**  
**List1**  
**Matrixliste**  
**List2**   
## Beispiel  
 Dieses Beispiel deklariert eine generische Schnittstelle, `IMyGenIface` und zwei nicht generische Schnittstellen, `IMySpecializedInt` und `ImySpecializedString`, die `IMyGenIface` spezialisieren.  Die zwei speziellen Schnittstellen werden dann von zwei Klassen, `MyIntClass` und `MyStringClass` implementiert.  Im Beispiel wird gezeigt, wie generische Schnittstellen ausgelegt, die generischen und nicht generischen Schnittstellen instanziiert und die explizit implementierten Member auf den Schnittstellen aufruft.  
  
```  
// generic_interface2.cpp  
// compile with: /clr  
// Specializing and implementing generic interfaces.  
using namespace System;  
  
generic <class ItemType>  
public interface class IMyGenIface {  
   void Initialize(ItemType f);  
};  
  
public interface class IMySpecializedInt: public IMyGenIface<int> {  
   void Display();  
};  
  
public interface class IMySpecializedString: public IMyGenIface<String^> {  
   void Display();  
};  
  
public ref class MyIntClass: public IMySpecializedInt {  
   int myField;  
  
public:   
   virtual void Initialize(int f) {  
      myField = f;  
   }  
  
   virtual void Display() {  
      Console::WriteLine("The integer field contains: {0}", myField);  
   }      
};  
  
public ref struct MyStringClass: IMySpecializedString {      
   String^ myField;  
  
public:  
   virtual void Initialize(String^ f) {  
      myField = f;  
    }  
  
   virtual void Display() {  
      Console::WriteLine("The String field contains: {0}", myField);  
   }  
};  
  
int main() {  
   // Instantiate the generic interface.  
   IMyGenIface<int>^ myIntObj = gcnew MyIntClass();  
  
   // Instantiate the specialized interface "IMySpecializedInt."  
   IMySpecializedInt^ mySpIntObj = (IMySpecializedInt^) myIntObj;  
  
   // Instantiate the generic interface.  
   IMyGenIface<String^>^ myStringObj = gcnew MyStringClass();  
  
   // Instantiate the specialized interface "IMySpecializedString."  
   IMySpecializedString^ mySpStringObj =   
            (IMySpecializedString^) myStringObj;  
  
   // Call the explicitly implemented interface members.  
   myIntObj->Initialize(1234);  
   mySpIntObj->Display();  
  
   myStringObj->Initialize("My string");  
   mySpStringObj->Display();  
}  
```  
  
  **Das ganzzahlige Feld enthält: 1234**  
**Das Zeichenfolgenfeld enthält: Meine Zeichenfolge**   
## Siehe auch  
 [Generics](../windows/generics-cpp-component-extensions.md)