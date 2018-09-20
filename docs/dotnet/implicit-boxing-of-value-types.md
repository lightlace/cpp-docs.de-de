---
title: Implizites Boxing von Werttypen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- boxing, Visual C++
- __box keyword
- boxing
- boxing, __box keyword
- value types, boxed
ms.assetid: 9597c92f-a3fe-44af-ad80-f9d656847a35
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e9c232dba6d766d0855bb4bb29e33d85b5fd5a2d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387587"
---
# <a name="implicit-boxing-of-value-types"></a>Implizites Boxing von Werttypen

Das Boxing von Werttypen wurde von Managed Extensions für C++ in Visual C++ geändert.

Im Sprachentwurf wir eine philosophischer Position praktische Erfahrung mit der Funktion und bedingt, in der Praxis ist ein Fehler vorlag. Als eine Analogie entschieden in der ursprünglichen mehrere Vererbung-Sprachentwurf, Stroustrup, dass eine virtuelle Basisklasse untergeordnete Objekt nicht werden, im Konstruktor einer abgeleiteten Klasse initialisiert konnte, und daher die Sprache erforderlich, die alle als virtuelle Basisklasse für Klassen -Klasse muss einen Standardkonstruktor definiert werden. Es ist dieser Standardkonstruktor, der von jeder nachfolgenden virtuellen Ableitung aufgerufen werden sollen.

Das Problem einer Hierarchie für die virtuelle Basisklasse ist, dass die Verantwortung für die Initialisierung der freigegebenen virtuellen untergeordneten Objekts mit jeder nachfolgenden Ableitung verschiebt. Z. B. wenn definiere ich eine Basisklasse für kann die Initialisierung erfordert, die Zuordnung eines Puffers, der vom Benutzer angegebenen Größe dieses Puffers als Argument an den Konstruktor übergeben werden. Wenn ich dann zwei weitere virtuelle ableitungen bereitstellen, Aufrufen `inputb` und `outputb`, jeweils einen bestimmten Wert an den Konstruktor der Basisklasse enthält. Wenn ich nun abgeleitet eine `in_out` -Klasse `inputb` und `outputb`, keiner dieser Werte auf das freigegebene virtuelle Basisklasse untergeordnete Objekt kann auf angemessene Weise auszuwertende zugelassen werden.

Aus diesem Grund nicht Stroustrup des ursprünglichen Entwurfs der Sprache, eine virtuelle Basisklasse in der Liste der Member-Initialisierung der Konstruktor der abgeleiteten Klasse die explizite Initialisierung zulässig. Während dies das Problem gelöst, erwies sich als in der Praxis die Unfähigkeit, leiten die Initialisierung der virtuellen Basisklasse nicht praktikabel. Keith Gorlen war vom National Institute of Health, der eine Freewareversion Nihcl wird aufgerufen, der die SmallTalk Auflistung implementiert hatte, eine Stimme Prinzip Stroustrup, die er mussten, um ein flexibleres Sprachdesign zu überzeugen.

Ein Prinzip der objektorientierten hierarchische Entwurf enthält, dass eine abgeleitete Klasse nur mit der privaten Implementierung seiner unmittelbar Basisklassen darum kümmern soll. Stroustrup musste, um einen flexiblen Initialisierung-Entwurf für die virtuelle Vererbung unterstützen, dieses Prinzip verstoßen. Die am stärksten abgeleitete Klasse in einer Hierarchie übernimmt die Verantwortung für alle virtuellen Unterobjekt Initialisierung unabhängig davon, wie viele Ebenen in der Hierarchie, wenn er vorkommt. Z. B. `inputb` und `outputb` sind verantwortlich für das explizite ihrer unmittelbaren virtuelle Basisklasse initialisieren. Wenn `in_out` leitet sich von sowohl `inputb` und `outputb`, `in_out` verantwortlich ist, für die Initialisierung der einmal virtuelle Basisklasse entfernt, und die Initialisierung innerhalb expliziter `inputb` und `outputb` ist unterdrückt.

Dies bietet die Flexibilität, die erforderlich sind, von Sprachenentwicklern, jedoch auch zu einer komplizierten Semantik. Diese Last der Komplikation wird sofort entfernt werden, wenn wir eine virtuelle Basisklasse um zustandslos ist und einfach an eine Schnittstelle einschränken. Dies ist eine empfohlene Entwurfsausdruck in C++. In CLR-Programmierung wird es für die Richtlinie mit dem Schnittstellentyp ausgelöst.

Hier ist eine einfache Code-Beispiel – und das explizite Boxing ist in diesem Fall nicht erforderlich:

```
// Managed Extensions for C++ requires explicit __box operation
int my1DIntArray __gc[] = { 1, 2, 3, 4, 5 };
Object* myObjArray __gc[] = {
   __box(26), __box(27), __box(28), __box(29), __box(30)
};

Console::WriteLine( "{0}\t{1}\t{2}", __box(0),
   __box(my1DIntArray->GetLowerBound(0)),
   __box(my1DIntArray->GetUpperBound(0)) );
```

Wie Sie sehen können, ist es viel Boxing statt. Unter Visual C++-Werttyp Boxing ist implizit:

```
// new syntax makes boxing implicit
array<int>^ my1DIntArray = {1,2,3,4,5};
array<Object^>^ myObjArray = {26,27,28,29,30};

Console::WriteLine( "{0}\t{1}\t{2}", 0,
   my1DIntArray->GetLowerBound( 0 ),
   my1DIntArray->GetUpperBound( 0 ) );
```

## <a name="see-also"></a>Siehe auch

[Werttypen und ihr Verhalten (C++/CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)<br/>
[Boxing](../windows/boxing-cpp-component-extensions.md)