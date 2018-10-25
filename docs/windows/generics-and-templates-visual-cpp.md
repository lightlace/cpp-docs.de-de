---
title: Generika und Vorlagen (C++ / CLI) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/12/2018
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
ms.openlocfilehash: 4cc12d48bc6de95d55ba56f34df54b60c0ded846
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50066668"
---
# <a name="generics-and-templates-ccli"></a>Generika und Vorlagen (C++ / CLI)

Generika und Vorlagen sind Sprachfunktionen, die Unterstützung für parametrisierte Typen ermöglichen. Allerdings unterscheiden sich und haben unterschiedliche Verwendungen. Dieses Thema enthält eine Übersicht über die Unterschiede.

Weitere Informationen finden Sie unter [Windows-Laufzeit und verwaltete Vorlagen](../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md).

## <a name="comparing-templates-and-generics"></a>Vergleichen von Vorlagen und Generika

Wichtige Unterschiede zwischen Generika und C++-Vorlagen:

- Generika sind generisch, bis die Typen, die für sie zur Laufzeit ersetzt werden. Vorlagen sind zum Zeitpunkt der Kompilierung spezialisiert, sodass sie nicht immer noch parametrisierte Typen zur Laufzeit sind

- Die common Language Runtime unterstützt insbesondere Generika in MSIL. Da die Common Language Runtime Informationen über Generika kennt, können bestimmte Typen für generische Typen ersetzt werden, wenn Sie eine Assembly mit einem generischen Typ verweisen. Vorlagen, die im Gegensatz dazu in normale Typen zum Zeitpunkt der Kompilierung aufgelöst werden, und die resultierenden Typen können nicht in anderen Assemblys spezialisiert sein.

- Generika spezialisiert in zwei verschiedenen Assemblys mit demselben Typ Argumente, die den gleichen Typ sind. Vorlagen werden in zwei verschiedenen Assemblys mit demselben Typ, die von der Laufzeit als Argumente betrachtet werden, als von unterschiedlichen Typen spezialisiert.

- Generika werden als einzelnes Softwareprodukt von ausführbarem Code generiert, die für alle Verweisargumente Typ verwendet wird (Dies gilt nicht für Werttypen, die eine einmalige Implementierung pro Werttyp haben). Der JIT-Compiler Generika kennt und den Code für die Typen von Verweis- oder Werttyp zu optimieren, die als Typargumente verwendet werden kann. Vorlagen werden separate Laufzeit-Code, für jede Spezialisierung generieren.

- Generische Typen dürfen keine Nichttyp-Vorlagenparameter zu, wie z. B. `template <int i> C {}`. Vorlagen können sie.

- Generika gestatten keine explizite Spezialisierung (d. h. eine benutzerdefinierte Implementierung einer Vorlage für einen bestimmten Typ). Führen Sie die Vorlagen.

- Generika lassen sich nicht auf teilweise Spezialisierung (eine benutzerdefinierte Implementierung für eine Teilmenge der Typargumente) aus. Führen Sie die Vorlagen.

- Generika lassen nicht den Typparameter als Basisklasse für den generischen Typ verwendet werden. Führen Sie die Vorlagen.

- Vorlagen unterstützen Vorlage-Template-Parameter (z. B. `template<template<class T> class X> class MyClass`), jedoch nicht für generische Typen.

## <a name="combining-templates-and-generics"></a>Kombinieren von Vorlagen und Generika

Der grundlegende Unterschied in Generika wirkt sich zum Erstellen von Anwendungen, die Vorlagen und Generika kombinieren. Nehmen wir beispielsweise an, dass Sie eine Klasse verfügen, der Sie erstellen einen generischen Wrapper für diese Vorlage für andere Sprachen als generische verfügbar machen möchten. Keine der generischen dauert einen Typparameter, den dann an die Vorlage übergeben werden soll, da die Vorlage dieser Parameter vom Typ zur Kompilierzeit muss, aber die generische wird nicht den Typparameter bis zur Laufzeit aufgelöst werden. Schachteln einer Vorlage in eine generische funktioniert entweder nicht, da es gibt keine Möglichkeit, um die Vorlagen zum Zeitpunkt der Kompilierung für beliebige generische Typen zu erweitern, der zur Laufzeit instanziiert werden kann.

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Das folgende Beispiel zeigt ein einfaches Beispiel der Verwendung von Vorlagen und Generika zusammen. In diesem Beispiel übergibt die Vorlagenklasse als Parameter durch für dem generischen Typ an. Umgekehrt ist dies nicht möglich.

Dieses Idiom kann verwendet werden, wenn Sie möchten, auf eine generische API mit Vorlagencode zu erstellen, die lokal an einen C++ ist c++ / CLI-Assembly, oder wenn Sie eine zusätzliche Ebene der Parametrisierung in einen generischen Typ hinzufügen müssen, unterstützt Sie nicht bestimmte Features von Vorlagen nutzen b y-Generika.

### <a name="code"></a>Code

```cpp
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

```Output
F
```

## <a name="see-also"></a>Siehe auch

[Generika](../windows/generics-cpp-component-extensions.md)