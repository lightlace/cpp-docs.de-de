---
title: "Memberfunktionsvorlagen"
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
  - "Funktionsvorlagen, Memberfunktionen"
ms.assetid: 83d51835-6a27-40ed-997c-7d90dc9182d8
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Memberfunktionsvorlagen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Ausdruck "Membervorlage" bezieht sich auf Memberfunktionsvorlagen und geschachtelte Klassenvorlagen.  Memberfunktionsvorlagen sind Vorlagenfunktionen, die Member einer Klasse oder einer Klassenvorlage sind.  Weitere Informationen finden Sie unter [Geschachtelte Klassenvorlagen](../Topic/Nested%20Class%20Templates.md).  
  
 Memberfunktionen können in mehreren Kontexten Funktionsvorlagen sein.  Alle Funktionen von Klassenvorlagen sind generisch, werden jedoch nicht als Membervorlagen oder Memberfunktionsvorlagen bezeichnet.  Wenn diese Memberfunktionen eigene Vorlagenargumente übernehmen, werden sie als Memberfunktionsvorlagen betrachtet.  Ausführliche Informationen finden Sie unter [Memberfunktionen von Vorlagenklassen](../Topic/Member%20Functions%20of%20Template%20Classes.md).  
  
## Beispiel  
 Memberfunktionsvorlagen von nicht auf Vorlagen basierenden Klassen oder Vorlagenklassen werden als Funktionsvorlagen mit ihren Vorlagenparametern deklariert.  
  
```  
// member_function_templates.cpp  
struct X  
{  
   template <class T> void mf(T* t) {}  
};  
  
int main()  
{  
   int i;  
   X* x = new X();  
   x->mf(&i);  
}  
```  
  
## Beispiel  
 Das folgende Beispiel zeigt eine Memberfunktionsvorlage einer Vorlagenklasse.  
  
```  
// member_function_templates2.cpp  
template<typename T>  
class X  
{  
public:  
   template<typename U>  
   void mf(const U &u)  
   {  
   }  
};  
  
int main()  
{  
}  
```  
  
## Beispiel  
 Darüber hinaus können in Visual Studio .NET 2003 und höher Membervorlagen auch außerhalb einer Klasse definiert werden.  
  
```  
// defining_member_templates_outside_class.cpp  
template<typename T>  
class X  
{  
public:  
   template<typename U>  
   void mf(const U &u);  
};  
  
template<typename T> template <typename U>  
void X<T>::mf(const U &u)  
{  
}  
  
int main()  
{  
}  
```  
  
## Beispiel  
 Lokale Klassen dürfen keine Membervorlagen haben.  
  
 Membervorlagenfunktionen können keine virtuellen Funktionen sein und können keine virtuellen Funktionen einer Basisklasse überschreiben, wenn sie mit dem gleichen Namen wie eine virtuelle Funktion der Basisklasse deklariert werden.  
  
 Mit Visual C\+\+ .NET 2003 wurde die Unterstützung für auf Vorlagen basierende benutzerdefinierte Konvertierungen eingeführt.  Das folgende Beispiel funktioniert in Visual C\+\+ .NET 2003 wie im Standard angegeben.  
  
```  
// templated_user_defined_conversions.cpp  
template <class T>  
struct S  
{  
   template <class U> operator S<U>()  
   {  
      return S<U>();  
   }  
};  
  
int main()  
{  
   S<int> s1;  
   S<long> s2 = s1;  // Convert s1 using UDC and copy constructs S<long>.  
}  
```  
  
## Siehe auch  
 [Funktionsvorlagen](../cpp/function-templates.md)