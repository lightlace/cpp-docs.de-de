---
title: Generika und Vorlagen (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- generics [C++], vs. templates
- templates, C++
ms.assetid: 63adec79-b1dc-4a1a-a21d-b8a72a8fce31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5d6dc0a64c5d225f6e80a21dc008e5a2486ad3d9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="generics-and-templates-visual-c"></a>Generika und Vorlagen (Visual C++)
Generika und Vorlagen sind beide Sprachfunktionen, die parametrisierte Typen unterstützen. Allerdings unterscheiden sich und andere verwendet haben. Dieses Thema enthält eine Übersicht über die viele Unterschiede.  
  
 Weitere Informationen finden Sie unter [Windows-Runtime und verwaltete Vorlagen](../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md).  
  
## <a name="comparing-templates-and-generics"></a>Vergleichen von Vorlagen und Generika  
 Wichtige Unterschiede zwischen Generika und C++-Vorlagen:  
  
-   Generika sind generisch, bis die Typen, die für sie zur Laufzeit ersetzt werden. Vorlagen werden zum Zeitpunkt der Kompilierung spezialisiert, sodass sie nicht immer noch parametrisierte Typen zur Laufzeit werden  
  
-   Die common Language Runtime unterstützt speziell Generika in MSIL. Daran, dass die Common Language Runtime Informationen über Generika bekannt, können bestimmte Typen für generische Typen ersetzt werden, wenn Sie eine Assembly mit einem generischen Typ verweisen. Vorlagen, die im Gegensatz dazu in normale Typen zur Kompilierzeit aufgelöst werden und die resultierenden Typen können nicht in anderen Assemblys spezialisiert sein.  
  
-   Generika spezialisiert in zwei verschiedenen Assemblys mit dem gleichen Typ sind Argumente vom gleichen Typ. Vorlagen spezialisiert in zwei verschiedenen Assemblys mit dem gleichen Typ, der von der Laufzeit als Argumente betrachtet werden, um unterschiedliche Typen aufweisen.  
  
-   Generika werden als ein einzelnes Stück von ausführbarem Code generiert, die für alle Verweis Typargumente verwendet wird (Dies gilt nicht für Werttypen, die eine eindeutige Implementierung pro Werttyp haben). Der JIT-Compiler Generika kennt und den Code für die Verweis- oder Werttyp Typen zu optimieren, die als Typargumente verwendet werden kann. Vorlagen werden separate Laufzeit-Code für jede Spezialisierung generieren.  
  
-   Generika lassen keine Nichttyp-Vorlagenparameter, z. B. `template <int i> C {}`. Vorlagen lassen.  
  
-   Generika sind explizite Spezialisierung (d. h. eine benutzerdefinierte Implementierung einer Vorlage für einen bestimmten Typ) nicht zulässig. Führen Sie die Vorlagen.  
  
-   Generika sind teilweise Spezialisierung (eine benutzerdefinierte Implementierung für eine Teilmenge der Typargumente) nicht zulässig. Führen Sie die Vorlagen.  
  
-   Den Typparameter für den generischen Typ als Basisklasse verwendet werden zulassen Generika nicht. Führen Sie die Vorlagen.  
  
-   Vorlagen unterstützen Vorlage Parameter (z. B. `template<template<class T> class X> class MyClass`), aber Generika nicht der Fall.  
  
## <a name="combining-templates-and-generics"></a>Kombinieren von Vorlagen und Generika  
  
-   Der grundlegende Unterschied in Generika wirkt sich zum Erstellen von Anwendungen, die Vorlagen und Generika kombinieren. Angenommen Sie, Sie verfügen über eine Vorlagenklasse, der Sie erstellen einen generischen Wrapper für die Vorlage für andere Sprachen als generische verfügbar machen möchten. Keine generischen akzeptieren einen Typparameter, den dann an die Vorlage übergeben werden soll, da die Vorlage zum Zeitpunkt der Kompilierung den Typparameter verfügen muss, aber die generische wird nicht den Typparameter bis zur Laufzeit aufgelöst werden. Schachteln von einer Vorlage in eine generische funktioniert entweder nicht, da es gibt keine Möglichkeit, um die Vorlagen zum Zeitpunkt der Kompilierung für beliebige generische Typen zu erweitern, die zur Laufzeit instanziiert werden kann.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Das folgende Beispiel zeigt ein einfaches Beispiel für die gemeinsame Verwendung von Vorlagen und Generika. In diesem Beispiel übergibt die Vorlagenklasse Parameter durch für dem generischen Typ an. Umgekehrt ist nicht möglich.  
  
 Diese Technik kann verwendet werden, wenn Sie auf eine vorhandene generische API mit den Vorlagencode zu erstellen, die lokal auf einer Visual C++-Assembly ist, oder wenn Sie eine zusätzliche Ebene für die Parametrisierung für einen generischen Typ, um bestimmte Funktionen der Vorlagen nicht Supporte nutzen hinzufügen müssen d von Generika.  
  
### <a name="code"></a>Code  
  
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
  
### <a name="output"></a>Ausgabe  
  
```  
F  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Generika](../windows/generics-cpp-component-extensions.md)