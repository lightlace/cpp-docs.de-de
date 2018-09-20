---
title: Private virtuelle Funktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- virtual functions, private
- derived classes, virtual functions
- access modifiers [C++], for class members
- member access [C++], virtual members
ms.assetid: 04448086-bf72-44be-9c1f-dfda1744949e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0058d023268fa4d9ca5abe802ff45856e9855dc7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418072"
---
# <a name="private-virtual-functions"></a>Private virtuelle Funktionen

Die Möglichkeit, die private virtuelle Funktionen in abgeleiteten Klassen behandelt werden wurde von Managed Extensions für C++ in Visual C++ geändert.

In Managed Extensions schränkt die Zugriffsebene für eine virtuelle Funktion nicht die Möglichkeit, die in einer abgeleiteten Klasse außer Kraft gesetzt werden. In der neuen Syntax kann eine virtuelle Funktion keine virtuelle Funktion der Basisklasse überschreiben, die nicht darauf zugreifen können. Zum Beispiel:

```
__gc class MyBaseClass {
   // inaccessible to a derived class
   virtual void g();
};

__gc class MyDerivedClass : public MyBaseClass {
public:
   // okay in Managed Extensions; g() overrides MyBaseClass::g()
   // error in new syntax; cannot override: MyBaseClass::g() is inaccessible
   void g();
};
```

Es gibt keine echte Zuordnung dieser Art des Entwurfs auf die neue Syntax. Eine muss einfach die Member der Basisklasse zugegriffen werden kann – d. h. nicht Private ausführen. Die geerbten Methoden müssen nicht den gleichen Zugriff zu berücksichtigen. In diesem Beispiel ist die am wenigsten invasiven Änderung ist, um die MyBaseClass Bereich `protected`. Auf diese Weise wird das allgemeine Programm-Zugriff auf die Methode über MyBaseClass immer noch nicht zulässig.

```
ref class MyBaseClass {
protected:
   virtual void g();
};

ref class MyDerivedClass : MyBaseClass {
public:
   virtual void g() override;
};
```

Beachten Sie, dass das Fehlen der expliziten `virtual` Schlüsselwort in der Basisklasse, unter der neuen Syntax wird eine Warnmeldung generiert.

## <a name="see-also"></a>Siehe auch

[Memberdeklarationen innerhalb einer Klasse oder Schnittstelle (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)
