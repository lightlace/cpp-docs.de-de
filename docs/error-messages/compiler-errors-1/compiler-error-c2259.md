---
title: "Compilerfehler C2259"
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
  - "C2259"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2259"
ms.assetid: e458236f-bdea-4786-9aa6-a98d8bffa5f4
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2259
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': abstrakte Klasse kann nicht instanziiert werden  
  
 Durch den Code wird eine Instanz einer abstrakten Klasse oder Struktur deklariert.  
  
 Eine Klasse oder Struktur mit einer oder mehreren rein virtuellen Funktionen kann nicht instanziiert werden.  Damit Objekte einer abgeleiteten Klasse instanziiert werden können, muss jede rein virtuelle Funktion durch die abgeleitete Klasse überschrieben werden.  
  
 Weitere Informationen finden Sie unter [Implizit abstrakte Klassen](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Implicitly_abstract_classes).  
  
 Im folgenden Beispiel wird C2259 generiert:  
  
```  
// C2259.cpp  
// compile with: /c  
class V {  
public:  
   void virtual func() = 0;  
};  
class A : public V {};  
class B : public V {  
public:  
   void func();  
};  
V v;  // C2259, V is an abstract class  
A a;  // C2259, A inherits func() as pure virtual  
B b;  // OK, B defines func()  
```  
  
 Immer wenn Sie von einer Schnittstelle ableiten und die Schnittstellenmethoden in der abgeleiteten Klasse mit anderen als öffentlichen Zugriffsberechtigungen implementieren, wird möglicherweise der Fehler C2259 ausgegeben.  Dieser Fehler tritt auf, weil der Compiler erwartet, dass die in der abgeleiteten Klasse definierten Schnittstellenmethoden öffentlichen Zugriff haben.  Wenn Sie die Memberfunktionen für eine Schnittstelle mit beschränkteren Zugriffsberechtigungen implementieren, werden diese vom Compiler nicht als Implementierungen der in der Schnittstelle definierten Schnittstellenmethoden interpretiert, sodass die abgeleitete Klasse zu einer abstrakten Klasse wird.  
  
 Das Problem kann mit zwei Methoden umgangen werden:  
  
-   Definieren Sie die Zugriffsberechtigungen für die implementierten Methoden als öffentlich.  
  
-   Verwenden Sie den Bereichsauflösungsoperator für die in der abgeleiteten Klasse definierten Schnittstellenmethoden, um den Namen der implementierten Methode mit dem Namen der Schnittstelle zu kennzeichnen.  
  
 C2259 kann außerdem infolge einer Konformitätsverbesserung in Visual C\+\+ 2005 ausgegeben werden, durch die **\/Zc:wchar\_t** jetzt standardmäßig aktiviert ist.  In dieser Situation kann der Fehler C2599 behoben werden, indem Sie mit **\/Zc:wchar\_t\-** kompilieren, um das Verhalten der vorherigen Versionen zu erhalten. Die bessere Methode besteht jedoch in der Aktualisierung Ihrer Typen, sodass diese kompatibel sind.  Weitere Informationen finden Sie unter [\/Zc:wchar\_t \(wchar\_t ist der systemeigene Typ\)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md).  
  
 Im folgenden Beispiel wird C2259 generiert:  
  
```  
// C2259b.cpp  
// compile with: /c  
#include <windows.h>   
  
class MyClass {  
public:  
   // WCHAR now typedef'ed to wchar_t  
   virtual void func(WCHAR*) = 0;  
};  
  
class MyClass2 : MyClass {  
public:  
   void func(unsigned short*);  
};  
  
MyClass2 x;   // C2259  
  
// OK  
class MyClass3 {  
public:  
   virtual void func(WCHAR*) = 0;  
   virtual void func2(wchar_t*) = 0;  
   virtual void func3(unsigned short*) = 0;  
};  
  
class MyClass4 : MyClass3 {  
public:  
   void func(WCHAR*) {}  
   void func2(wchar_t*) {}  
   void func3(unsigned short*) {}  
};  
  
MyClass4 y;  
```  
  
 Im folgenden Beispiel wird C2259 generiert:  
  
```  
// C2259c.cpp  
// compile with: /clr  
interface class MyInterface {  
   void MyMethod();  
};  
  
ref class MyDerivedClass: public MyInterface {  
private:  
   // Uncomment the following line to resolve.  
   // public:  
   void MyMethod(){}  
   // or the following line  
   // void MyInterface::MyMethod() {};  
};  
  
int main() {  
   MyDerivedClass^ instance = gcnew MyDerivedClass; // C2259  
}  
```  
  
 Im folgenden Beispiel wird C2259 generiert:  
  
```  
// C2259d.cpp  
// compile with: /clr:oldSyntax  
public __gc __interface MyInterface {  
   void MyMethod();  
};  
  
__gc class MyDerivedClass : public MyInterface {  
// Uncomment the following line to resolve.  
// public:  
   void MyMethod() {};  
   // or the following line  
   // void MyInterface::MyMethod() {};  
};  
  
int main() {  
   MyDerivedClass *instance = new MyDerivedClass();   // C2259  
}  
```