---
title: "Friend-Vorlagen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 077acea5-0d0f-4b33-916d-1211797e5e28
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
caps.handback.revision: 9
---
# Friend-Vorlagen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Klassenvorlagen können [Friends](assetId:///bf412640-d857-4acb-b2b5-513131cb9681) haben.  Eine Klasse oder Klassenvorlage, Funktion oder Funktionsvorlage kann ein Friend einer Vorlagenklasse sein.  Friends können auch Spezialisierungen einer Klassenvorlage oder Funktionsvorlage sein, jedoch keine teilweisen Spezialisierungen.  
  
## Beispiel  
 Im folgenden Beispiel wird eine Friend\-Funktion als Funktionsvorlage innerhalb der Klassenvorlage definiert.  Dieser Code erstellt eine Version der Friend\-Funktion für jede Instanziierung der Vorlage.  Dieses Konstrukt ist nützlich, wenn die Friend\-Funktion von denselben Vorlagenparametern wie die Klasse abhängt.  
  
```  
// template_friend1.cpp  
// compile with: /EHsc  
  
#include <iostream>  
using namespace std;  
  
template <class T> class Array {  
   T* array;  
   int size;  
  
public:  
   Array(int sz): size(sz) {  
      array = new T[size];  
      memset(array, 0, size * sizeof(T));  
   }  
  
   Array(const Array& a) {  
      size = a.size;  
      array = new T[size];  
      memcpy_s(array, a.array, sizeof(T));  
   }  
  
   T& operator[](int i) {  
      return *(array + i);  
   }  
  
   int Length() { return size; }  
  
   void print() {  
      for (int i = 0; i < size; i++)        
         cout << *(array + i) << " ";  
  
      cout << endl;  
   }  
  
   template<class T>  
   friend Array<T>* combine(Array<T>& a1, Array<T>& a2);  
};  
  
template<class T>  
Array<T>* combine(Array<T>& a1, Array<T>& a2) {  
   Array<T>* a = new Array<T>(a1.size + a2.size);  
   for (int i = 0; i < a1.size; i++)  
      (*a)[i] = *(a1.array + i);  
  
   for (int i = 0; i < a2.size; i++)  
      (*a)[i + a1.size] = *(a2.array + i);  
  
   return a;  
}  
  
int main() {  
   Array<char> alpha1(26);  
   for (int i = 0 ; i < alpha1.Length() ; i++)  
      alpha1[i] = 'A' + i;  
  
   alpha1.print();  
  
   Array<char> alpha2(26);  
   for (int i = 0 ; i < alpha2.Length() ; i++)  
      alpha2[i] = 'a' + i;  
  
   alpha2.print();  
   Array<char>*alpha3 = combine(alpha1, alpha2);  
   alpha3->print();  
   delete alpha3;  
}  
```  
  
  **A B C D E F G H I J K L M N O P Q R S T U V W X Y Z**   
**a b c d e f g h i j k l m n o p q r s t u v w x y z**   
**A B C D E F G H I J K L M N O P Q R S T U V W X Y Z a b c d e f g h i j k l m n o p q r s t u v w x y z**    
## Beispiel  
 Das folgenden Beispiel befasst sich mit einem Friend mit Vorlagenspezialisierung.  Eine Funktionsvorlagenspezialisierung ist automatisch ein Friend, wenn die ursprüngliche Funktionsvorlage ein Friend ist.  
  
 Es ist auch möglich, nur die spezielle Version der Vorlage als Friend zu deklarieren, wie der Kommentar vor der Friend\-Deklaration im folgenden Code veranschaulicht.  In diesem Fall müssen Sie die Definition der Friend\-Vorlagenspezialisierung außerhalb der Vorlagenklasse stellen.  
  
```  
// template_friend2.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
template <class T>  
class Array;  
  
template <class T>  
void f(Array<T>& a);  
  
template <class T> class Array  
{  
    T* array;  
    int size;  
  
public:  
    Array(int sz): size(sz)  
    {  
        array = new T[size];  
        memset(array, 0, size * sizeof(T));  
    }  
    Array(const Array& a)  
    {  
        size = a.size;  
        array = new T[size];  
        memcpy_s(array, a.array, sizeof(T));  
    }  
    T& operator[](int i)  
    {  
        return *(array + i);  
    }  
    int Length()  
    {   
        return size;  
    }  
    void print()  
    {  
        for (int i = 0; i < size; i++)  
        {  
            cout << *(array + i) << " ";  
        }  
        cout << endl;  
    }  
    // If you replace the friend declaration with the int-specific  
    // version, only the int specialization will be a friend.  
    // The code in the generic f will fail  
    // with C2248: 'Array<T>::size' :  
    // cannot access private member declared in class 'Array<T>'.  
    //friend void f<int>(Array<int>& a);  
  
    friend void f<>(Array<T>& a);  
};  
  
// f function template, friend of Array<T>  
template <class T>  
void f(Array<T>& a)  
{  
    cout << a.size << " generic" << endl;  
}  
  
// Specialization of f for int arrays  
// will be a friend because the template f is a friend.  
template<> void f(Array<int>& a)  
{  
    cout << a.size << " int" << endl;  
}  
  
int main()  
{  
    Array<char> ac(10);  
    f(ac);  
  
    Array<int> a(10);  
    f(a);  
}  
```  
  
  **10 generisch**  
**10 int**   
## Beispiel  
 Das folgende Beispiel zeigt eine Friend\-Klassenvorlage, die innerhalb einer Klassenvorlage wurde.  Die Klassenvorlage wird dann als Vorlagenargument für die Friend\-Klasse verwendet.  Friend\-Klassenvorlagen müssen außerhalb der Klassenvorlage definiert werden, in der sie deklariert werden.  Alle Spezialisierungen oder Teilspezialisierungen der Friend\-Vorlage sind auch Friends der ursprünglichen Klassenvorlage.  
  
```  
// template_friend3.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
template <class T>  
class X  
{  
private:  
   T* data;  
   void InitData(int seed) { data = new T(seed); }  
public:  
   void print() { cout << *data << endl; }  
   template <class U> friend class Factory;  
};  
  
template <class U>  
class Factory  
{  
public:  
   U* GetNewObject(int seed)  
   {  
      U* pu = new U;  
      pu->InitData(seed);  
      return pu;  
   }  
};  
  
int main()  
{  
   Factory< X<int> > XintFactory;  
   X<int>* x1 = XintFactory.GetNewObject(65);  
   X<int>* x2 = XintFactory.GetNewObject(97);  
  
   Factory< X<char> > XcharFactory;  
   X<char>* x3 = XcharFactory.GetNewObject(65);  
   X<char>* x4 = XcharFactory.GetNewObject(97);  
   x1->print();  
   x2->print();  
   x3->print();  
   x4->print();  
}  
```  
  
  **65**  
**97**  
**A**  
**a**   
## Siehe auch  
 [Standardargumente](../cpp/default-arguments.md)