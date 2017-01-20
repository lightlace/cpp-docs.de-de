---
title: "Generics and Templates (Visual C++)"
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
  - "generics [C++], vs. templates"
  - "templates, C++"
ms.assetid: 63adec79-b1dc-4a1a-a21d-b8a72a8fce31
caps.latest.revision: 19
caps.handback.revision: "19"
ms.author: "mblome"
manager: "ghogen"
---
# Generics and Templates (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Generika und Vorlagen sind beide Sprachfunktionen, die Unterstützung für parametrisierte Typen unterstützen.  Allerdings sind sie voneinander unterschiedlich Verwendung.  Dieses Thema enthält eine Übersicht über die zahlreichen Unterschiede.  
  
 Weitere Informationen finden Sie unter [Windows Runtime and Managed Templates](../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md) und [Übersicht über Vorlagen](../Topic/Templates%20Overview.md).  
  
## Vergleichen von Vorlagen und von Generika  
 Wesentliche Unterschiede zwischen Generika und C\+\+\-Vorlagen:  
  
-   Generika sind generisch, bis die für Typen zur Laufzeit ersetzt sind.  Vorlagen werden zur Kompilierzeit spezialisiert, daher sind sie noch nicht parametrisierte Typen zur Laufzeit  
  
-   Die Common Language Runtime unterstützt speziell Generika in MSIL.  Da die Laufzeit bei Generika auskennt, können bestimmte Typen für generische Typen ersetzt werden, wenn eine Assembly verweist, die ein generischer Typ enthält.  Vorlagen lösen demgegenüber sich in normaler Typ zur Kompilierzeit auf und die resultierenden Typen nicht in anderen Assemblys spezialisiert werden.  
  
-   Das Generika, das in zwei unterschiedlichen Assemblys mit gleichem Typargumenten spezialisiert ist, ist der gleiche Typ.  Die Vorlagen, die in zwei verschiedenen Assemblys mit gleichem Typargumenten spezialisiert werden, werden von der Laufzeit als unterschiedliche Typen betrachtet.  
  
-   Generika als einzelner wird von ausführbarem Code generiert, der für alle Verweistypargumente verwendet wird \(dies gilt für Werttypen nicht, die eine eindeutige Implementierung pro Werttyp haben\).  Der JIT\-Compiler kennt in Generika aus und ist, den Code für den Verweis oder die Werttypen optimieren, das als Typargumente verwendet werden.  Generierung Vorlagen separaten Laufzeitcode für eine Spezialisierung.  
  
-   Generika können nicht den Nichttyp\-Vorlagenparameter, wie `template <int i> C {}`.  Vorlagen ermöglichen es.  
  
-   Generika lässt keine explizite Spezialisierung \(das heißt, eine benutzerdefinierte Implementierung von einer Vorlage für einen bestimmten Typ\).  Vorlagen ausführen.  
  
-   Generika können nicht teilweise Spezialisierung \(eine benutzerdefinierte Implementierung für eine Teilmenge der Typargumente\).  Vorlagen ausführen.  
  
-   Generika können nicht den als Basisklasse für den generischen Typ verwendet werden, Typparameter.  Vorlagen ausführen.  
  
-   Vorlagenstützvorlagevorlagenparameter \(z.  `template<template<class T> class X> class MyClass`\), aber Generika jedoch nicht.  
  
## Kombination von Vorlagen und von Generika  
  
-   Der wesentliche Unterschied von Generika sich auf das Erstellen von Anwendungen, Vorlagen und Generika kombinieren.  Angenommen, Sie haben eine Vorlagenklasse, dass Sie ein generischer Wrapper für erstellen möchten, um diese Vorlage anderen Sprachen als generisches verfügbar zu machen.  Sie können das generische einen Typparameter nicht verwenden können, der anschließend an obwohl der Vorlage, da die Vorlage den Typparameter verfügen muss zur Kompilierzeit, aber das generische lösen keine den Typparameter bis zur Laufzeit auf.  Das Schachteln einer Vorlage innerhalb eines generischen funktioniert auch nicht, da es keine Möglichkeit gibt, die Vorlagen für beliebige generische Typen zur Kompilierungszeit zu erweitern, die zur Laufzeit instanziiert werden können.  
  
## Beispiel  
  
### **Beschreibung**  
 Das folgende Beispiel zeigt ein einfaches Beispiel für Anwendungsvorlagen und \-Generika gemeinsam an.  In diesem Beispiel führt die Vorlagenklasse den Parameter durch den generischen Typ.  Umgekehrt ist nicht möglich.  
  
 Diese Ausdrucksweise wurde kann verwendet werden, wenn Sie an einer vorhandenen generischen API mit Vorlagencode erstellen möchten, der in eine Visual C\+\+\-Assembly lokal ist, oder, wenn Sie eine zusätzliche Ebene Parametrisierung einem generischen Typ hinzufügen müssen, bestimmte Funktionen von Vorlagen nutzen unterstützt nicht von Generika.  
  
### Code  
  
```  
// templates_and_generics.cpp  
// compile with: /clr  
using namespace System;  
  
generic <class ItemType>  
ref class MyGeneric {  
   ItemType m_item;  
  
public:  
   MyGeneric(ItemType item) : m_item(item) {}  
   void F() {   
      Console::WriteLine("F");   
   }  
};  
  
template <class T>  
public ref class MyRef {  
MyGeneric<T>^ ig;  
  
public:  
   MyRef(T t) {  
      ig = gcnew MyGeneric<T>(t);  
      ig->F();  
    }      
};  
  
int main() {  
   // instantiate the template  
   MyRef<int>^ mref = gcnew MyRef<int>(11);  
}  
```  
  
### Ausgabe  
  
```  
F  
```  
  
## Siehe auch  
 [Generics](../windows/generics-cpp-component-extensions.md)