---
title: "typename"
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
  - "typename"
  - "typename_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "typename-Vorlagenspezifizierer"
ms.assetid: 52e1d901-220d-4f0d-ab43-dae7e05fb491
caps.latest.revision: 7
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# typename
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teilt dem Compiler mit, dass ein unbekannter Bezeichner ein Typ ist.  
  
## Syntax  
  
```  
  
typename identifier;  
```  
  
## Hinweise  
 Verwenden Sie dieses Schlüsselwort nur in Vorlagendefinitionen.  
  
 Dieses Schlüsselwort muss verwendet werden, wenn der Name ein qualifizierter Name ist, der von einem Vorlagenargument abhängig ist; er ist optional, wenn der qualifizierte Name nicht abhängig ist.  Weitere Informationen finden Sie unter [Vorlagen und Namensauflösung](../cpp/templates-and-name-resolution.md).  
  
 Das **typename**\-Schlüsselwort kann von jedem Typ an einer beliebigen Stelle in der Vorlagendeklaration oder \-definition verwendet werden.  Es ist in der Basisklassenliste nicht zulässig, außer als Vorlagenargument für eine Vorlagenbasisklasse.  
  
```  
template <class T>  
class C1 : typename T::InnerType // Error - typename not allowed.  
{};  
template <class T>  
class C2 : A<typename T::InnerType>  // typename OK.  
{};  
```  
  
 Das **typename**\-Schlüsselwort kann in Vorlagenparameterlisten auch anstelle von **class** verwendet werden.  Die folgenden Anweisungen sind beispielsweise identisch:  
  
```  
template<class T1, class T2>...  
template<typename T1, typename T2>...  
```  
  
## Beispiel  
  
```  
// typename.cpp  
template<class T> class X  
{  
   typename T::Y m_y;   // treat Y as a type  
};  
  
int main()  
{  
}  
```  
  
## Siehe auch  
 [Vorlagen](../cpp/templates-cpp.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)