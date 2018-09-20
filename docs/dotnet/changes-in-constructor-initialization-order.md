---
title: Änderungen in der Initialisierungsreihenfolge für Konstruktoren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- constructors, C++
ms.assetid: 8892c38d-6bf7-4cf7-ac8f-15e052135a79
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fd54e9810131f3ddfabe458c70ddef081568a9cd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46397688"
---
# <a name="changes-in-constructor-initialization-order"></a>Änderungen in der Initialisierungsreihenfolge für Konstruktoren

Die Reihenfolge der Initialisierung für die Klasse, Konstruktoren wurde von Managed Extensions für C++ in Visual C++ geändert.

## <a name="comparison-of-constructor-initialization-order"></a>Vergleich der Initialisierungsreihenfolge für Konstruktoren

In Managed Extensions für C++ Konstruktorinitialisierung, die in der folgenden Reihenfolge ist aufgetreten:

1. Der Konstruktor der Basisklasse, wenn vorhanden, aufgerufen.

1. Die Initialisierungsliste der Klasse wird ausgewertet.

1. Der Codetext der Konstruktor der Klasse ausgeführt wird.

Diese Reihenfolge der Ausführung folgt die gleichen Konventionen wie systemeigene C++-Programmierung. Die neue Visual C++-Sprache gibt die folgenden Ausführungsreihenfolge für CLR-Klassen:

1. Die Initialisierungsliste der Klasse wird ausgewertet.

1. Der Konstruktor der Basisklasse, wenn vorhanden, aufgerufen.

1. Der Codetext der Konstruktor der Klasse ausgeführt wird.

Beachten Sie, dass diese Änderung nur für CLR-Klassen gilt. native Klassen in Visual C++ folgen weiterhin früheren Konventionen. In beiden Fällen Kaskadieren über die gesamte Hierarchie-Kette, der eine bestimmte Klasse nach oben diese Regeln.

Beachten Sie im folgenden Codebeispiel wird die Verwendung von Managed Extensions für C++:

```
__gc class A
{
public:
   A() : _n(1)
   {
   }

protected:
   int _n;
};

__gc class B : public A
{
public:
   B() : _m(_n)
   {
   }
private:
   int _m;
};
```

Der Initialisierungsreihenfolge für Konstruktoren befolgen oben vorgeschrieben, sehen Sie die folgende Reihenfolge der Ausführung, wenn neue Instanzen der Klasse `B` erstellt werden:

1. Der Konstruktor der Basisklasse `A` aufgerufen wird. Die `_n` Member wird initialisiert, um `1`.

1. Der Initialisierungsliste für Klasse `B` ausgewertet wird. Die `_m` Member wird initialisiert, um `1`.

1. Den Codetext der Klasse `B` ausgeführt wird.

Betrachten Sie nun den gleichen Code in der neuen Visual C++-Syntax aus:

```
ref class A
{
public:
   A() : _n(1)
   {
   }

protected:
   int _n;
};

ref class B : A
{
public:
   B() : _m(_n)
   {
   }
private:
   int _m;
};
```

Die Reihenfolge der Ausführung, wenn neue Instanzen der Klasse `B` erstellt werden, unter der neuen Syntax lautet:

1. Der Initialisierungsliste für Klasse `B` ausgewertet wird. Die `_m` Member wird initialisiert, um `0` (`0` ist der Wert nicht initialisierte, der die `_m` Klassenmember).

1. Der Konstruktor der Basisklasse `A` aufgerufen wird. Die `_n` Member wird initialisiert, um `1`.

1. Den Codetext der Klasse `B` ausgeführt wird.

Beachten Sie, dass eine ähnliche Syntax unterschiedliche Ergebnisse für diese Codebeispiele erzeugt. Der Konstruktor der Klasse `B` benötigt einen Wert aus der Basisklasse `A` seine Member zu initialisieren. Jedoch der Konstruktor für Klasse `A` wurde noch nicht aufgerufen. Diese Abhängigkeit kann besonders gefährlich sein, wenn eine Zuordnung Arbeitsspeicher oder Ressourcen in den Basisklassenkonstruktor auftreten die geerbte Klasse abhängt.

## <a name="what-this-means-going-from-managed-extensions-for-c-to-visual-c-2010"></a>Was dies bedeutet, die für den Wechsel von Managed Extensions for C++ zu Visual C++ 2010

In vielen Fällen sollte die Änderungen an die Ausführungsreihenfolge der-Klasse, Konstruktoren für den Programmierer transparent sein, da Basisklassen keine das Verhalten des geerbten Klassen aufweisen. Allerdings wie die folgenden Codebeispiele veranschaulichen, können die Konstruktoren der geerbten Klassen erheblich beeinflusst werden, wenn die Liste der Initialisierung von den Werten der Member der Basisklasse abhängen. Wenn Sie Ihren Code von Managed Extensions für C++ in der neuen Syntax verschieben, sollten Sie solche Konstrukte in den Hauptteil der Konstruktor der Klasse, in denen Ausführung garantiert wird, zuletzt ausgeführt.

## <a name="see-also"></a>Siehe auch

[Verwaltete Typen (C++ / CL)](../dotnet/managed-types-cpp-cl.md)<br/>
[Konstruktoren](../cpp/constructors-cpp.md)
