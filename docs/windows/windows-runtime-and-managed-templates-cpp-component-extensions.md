---
title: "Windows Runtime and Managed Templates (C++ Component Extensions)"
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
  - "templates, with CLR types"
ms.assetid: cf59d16b-5514-448b-9a95-e0b4fcb616a6
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Runtime and Managed Templates (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vorlagen können Sie, um einen Prototyp eines Windows Common Language Runtime oder Runtime\-Typs zu definieren und instanziieren dann Variationen dieses Typs, indem verschiedene Vorlagentypparameter verwenden.  
  
## Alle Laufzeiten  
 Sie können Vorlagen im Wert oder von Referenztypen erstellen.  Weitere Informationen zum Erstellen des Werts oder der Verweistypen, finden Sie unter [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md).  
  
 Weitere Informationen über Standard\-C\+\+\-Klassenvorlagen, finden Sie unter [Klassenvorlagen](../cpp/class-templates.md).  
  
## Windows\-Runtime  
 \(Es gibt keine Hinweise für diese Sprachfunktion, die nur für Windows\-Runtime gelten.\)  
  
### Voraussetzungen  
 Compileroption: **\/ZW**  
  
## Common Language Runtime  
 Es gibt einige Einschränkungen zum Erstellen von Klassenvorlagen in verwalteten Typen, die in den folgenden Codebeispielen veranschaulicht werden.  
  
### Voraussetzungen  
 Compileroption: **\/clr**  
  
### Beispiele  
 **Beispiel**  
  
 Es ist möglich, einen generischen Typ mit einem Vorlagenparameter des verwalteten Typs zu instanziieren, aber Sie können eine verwaltete Vorlage mit dem Vorlagenparameter des generischen Typs nicht instanziieren.  Dies ist, da generische Typen zur Laufzeit aufgelöst werden.  Weitere Informationen finden Sie unter [Generics and Templates \(Visual C\+\+\)](../windows/generics-and-templates-visual-cpp.md).  
  
```cpp  
// managed_templates.cpp  
// compile with: /clr /c  
  
generic<class T>   
ref class R;   
  
template<class T>   
ref class Z {  
   // Instantiate a generic with a template parameter.  
   R<T>^ r;    // OK  
};  
  
generic<class T>   
ref class R {  
   // Cannot instantiate a template with a generic parameter.  
   Z<T>^ z;   // C3231  
};  
```  
  
 **Beispiel**  
  
 Ein generischer Typ oder eine verwaltete Funktion kann nicht in einer verwalteten Vorlage geschachtelt werden.  
  
```cpp  
// managed_templates_2.cpp  
// compile with: /clr /c  
  
template<class T> public ref class R {  
   generic<class T> ref class W {};   // C2959  
};  
```  
  
 **Beispiel**  
  
 Sie können auf die Vorlagen nicht zugreifen, die in einer Assembly, auf die verwiesen wird, mit C\+\+\/CLI\-Sprachensyntax definiert sind, aber Sie können Reflektion verwenden.  Wenn eine Vorlage nicht instanziiert wird, wird sie nicht in den Metadaten ausgegeben.  Wenn eine Vorlage instanziiert wird, wird nur Memberfunktionen in den Metadaten angezeigt werden.  
  
```cpp  
// managed_templates_3.cpp  
// compile with: /clr  
  
// Will not appear in metadata.  
template<class T> public ref class A {};  
  
// Will appear in metadata as a specialized type.  
template<class T> public ref class R {  
public:  
   // Test is referenced, will appear in metadata  
   void Test() {}  
  
   // Test2 is not referenced, will not appear in metadata  
   void Test2() {}  
};  
  
// Will appear in metadata.  
generic<class T> public ref class G { };  
  
public ref class S { };  
  
int main() {  
   R<int>^ r = gcnew R<int>;  
   r->Test();  
}  
```  
  
 **Beispiel**  
  
 Sie können den verwalteten Modifizierer einer Klasse in einer teilweisen Spezialisierung oder der expliziten Spezialisierung einer Klassenvorlage ändern.  
  
```cpp  
// managed_templates_4.cpp  
// compile with: /clr /c  
  
// class template  
// ref class  
template <class T>  
ref class A {};  
  
// partial template specialization  
// value type  
template <class T>  
value class A <T *> {};  
  
// partial template specialization  
// interface  
template <class T>   
interface class A<T%> {};  
  
// explicit template specialization  
// native class  
template <>  
class A <int> {};  
  
```  
  
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)