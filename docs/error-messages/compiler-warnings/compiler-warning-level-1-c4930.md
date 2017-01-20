---
title: "Compilerwarnung (Stufe 1) C4930"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4930"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4930"
ms.assetid: 89a206c9-c536-4186-8e81-1cde3e7f4f5b
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4930
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Prototyp': Funktion mit Prototyp wurde nicht aufgerufen \(war eine Variablendefinition gemeint?\)  
  
 Der Compiler hat einen nicht verwendeten Funktionsprototyp gefunden.  Falls der Prototyp als Variablendeklaration gedacht war, entfernen Sie die öffnende\/schließende runde Klammer.  
  
 Im folgenden Beispiel wird C4930 generiert:  
  
```  
// C4930.cpp  
// compile with: /W1  
class Lock {  
public:  
   int i;  
};  
  
void f() {  
   Lock theLock();   // C4930  
   // try the following line instead  
   // Lock theLock;  
}  
  
int main() {  
}  
```  
  
 C4930 kann auch auftreten, wenn der Compiler nicht zwischen einer Funktionsprototypdeklaration und einem Funktionsaufruf unterscheiden kann.  
  
 Im folgenden Beispiel wird C4930 generiert:  
  
```  
// C4930b.cpp  
// compile with: /EHsc /W1  
  
class BooleanException  
{  
   bool _result;  
  
public:  
   BooleanException(bool result)  
      : _result(result)  
   {  
   }  
  
   bool GetResult() const  
   {  
      return _result;  
   }  
};  
  
template<class T = BooleanException>  
class IfFailedThrow  
{  
public:  
   IfFailedThrow(bool result)  
   {  
      if (!result)  
      {  
         throw T(result);  
      }  
   }  
};  
  
class MyClass  
{  
public:  
   bool MyFunc()  
   {  
      try  
      {  
         IfFailedThrow<>(MyMethod()); // C4930  
  
         // try one of the following lines instead  
         // IfFailedThrow<> ift(MyMethod());  
         // IfFailedThrow<>(this->MyMethod());  
         // IfFailedThrow<>((*this).MyMethod());  
  
         return true;  
      }  
      catch (BooleanException e)  
      {  
         return e.GetResult();  
      }  
   }  
  
private:  
   bool MyMethod()  
   {  
      return true;  
   }  
};  
  
int main()  
{  
   MyClass myClass;  
   myClass.MyFunc();  
}  
```  
  
 Im oben gezeigten Beispiel wird das Ergebnis einer Methode, die null Argumente akzeptiert, als Argument an den Konstruktor einer unbenannten lokalen Klassenvariablen übergeben.  Sie können die Mehrdeutigkeit dieses Aufrufs aufheben, indem Sie entweder die lokale Variable benennen oder dem Methodenaufruf eine Objektinstanz zusammen mit dem entsprechenden Operator Zeiger\-auf\-Member voranstellen.