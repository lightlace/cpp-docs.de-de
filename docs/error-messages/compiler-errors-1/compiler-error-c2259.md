---
title: Compilerfehler C2259 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2259
dev_langs: C++
helpviewer_keywords: C2259
ms.assetid: e458236f-bdea-4786-9aa6-a98d8bffa5f4
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bcb7b24bb39ba204653d2a99d6bc1d3e5d8142b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2259"></a>Compilerfehler C2259
'class': abstrakte Klasse kann nicht instanziiert werden  
  
 Durch den Code wird eine Instanz einer abstrakten Klasse oder Struktur deklariert.  
  
 Eine Klasse oder Struktur mit einer oder mehreren rein virtuellen Funktionen kann nicht instanziiert werden. Damit Objekte einer abgeleiteten Klasse instanziiert werden können, muss jede rein virtuelle Funktion durch die abgeleitete Klasse überschrieben werden.  
  
 Weitere Informationen finden Sie unter [implizit abstrakte Klassen](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Implicitly_abstract_classes).  
  
 Im folgende Beispiel wird C2259 generiert:  
  
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
  
 Immer wenn Sie von einer Schnittstelle ableiten und die Schnittstellenmethoden in der abgeleiteten Klasse mit anderen als öffentlichen Zugriffsberechtigungen implementieren, wird möglicherweise der Fehler C2259 ausgegeben.  Dieser Fehler tritt auf, weil der Compiler erwartet, dass die in der abgeleiteten Klasse definierten Schnittstellenmethoden öffentlichen Zugriff haben. Wenn Sie die Memberfunktionen für eine Schnittstelle mit beschränkteren Zugriffsberechtigungen implementieren, werden diese vom Compiler nicht als Implementierungen der in der Schnittstelle definierten Schnittstellenmethoden interpretiert, sodass die abgeleitete Klasse zu einer abstrakten Klasse wird.  
  
 Das Problem kann mit zwei Methoden umgangen werden:  
  
-   Definieren Sie die Zugriffsberechtigungen für die implementierten Methoden als öffentlich.  
  
-   Verwenden Sie den Bereichsauflösungsoperator für die in der abgeleiteten Klasse definierten Schnittstellenmethoden, um den Namen der implementierten Methode mit dem Namen der Schnittstelle zu kennzeichnen.  
  
 C2259 kann außerdem infolge einer konformitätsverbesserung, die in Visual C++ 2005 erstellt wurde **/Zc: wchar_t** ist jetzt standardmäßig aktiviert. In diesem Fall kann der Fehler C2599 behoben entweder durch eine Kompilierung mit werden **/Zc:wchar_t-**, um das Verhalten abzurufen, aus früheren Versionen oder bevorzugt Aktualisierung Ihrer Typen, sodass diese kompatibel sind. Weitere Informationen finden Sie unter[/Zc:wchar_t (wchar_t ist der systemeigene Typ)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md).  
  
 Im folgende Beispiel wird C2259 generiert:  
  
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
  
 Im folgende Beispiel wird C2259 generiert:  
  
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
