---
title: Explizites Überschreiben eines Schnittstellenmembers | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- virtual functions, explicit overrides
- overriding functions
- interface members, explicit overrides
- functions [C++], overriding
- explicit override of virtual function
ms.assetid: 46f1f536-bf43-4311-9a17-ff2282e528a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 57c26c1185eff0e88e18ef23cb8506fb1fed407a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409024"
---
# <a name="explicit-override-of-an-interface-member"></a>Explizites Überschreiben eines Schnittstellenmembers

Die Syntax zum Deklarieren eines expliziten Überschreiben eines Schnittstellenmembers innerhalb einer Klasse hat Visual c++ von Managed Extensions for C++ geändert.

Häufig möchten Sie zwei Instanzen eines Schnittstellenmembers innerhalb einer Klasse bereitstellen, die der Benutzeroberfläche: eine, die verwendet wird, wenn Klassenobjekte über ein Handle für die Benutzeroberfläche bearbeitet werden und eine, die verwendet wird, wenn Klassenobjekte verwendet werden über die Schnittstelle für Klassen implementiert. Zum Beispiel:

```
public __gc class R : public ICloneable {
   // to be used through ICloneable
   Object* ICloneable::Clone();

   // to be used through an R
   R* Clone();
};
```

In Managed Extensions geschieht dies durch den Namen der Methode mit dem Namen der Schnittstelle qualifiziert eine explizite Deklaration der Schnittstellenmethode bereitstellen. Die mandantenklassen geltenden schemaanpassungen-Instanz ist nicht qualifiziert. Dadurch muss eine Umwandlung den Rückgabewert von `Clone`, in diesem Beispiel, wenn er durch eine Instanz der explizit aufgerufen `R`.

In der neuen Syntax wurde ein allgemeiner Mechanismus für die überschreibende eingeführt, die Managed Extensions-Syntax ersetzt. In unserem Beispiel würde wie folgt umgeschrieben werden:

```
public ref class R : public ICloneable {
public:
   // to be used through ICloneable
   virtual Object^ InterfaceClone() = ICloneable::Clone;

   // to be used through an R
   virtual R^ Clone();
};
```

Diese Version erfordert, dass die Schnittstellenmember explizit überschrieben werden erhält einen eindeutigen Namen innerhalb der Klasse. Hier habe ich der komplizierte Name bereitgestellt `InterfaceClone`. Das Verhalten ist immer noch - Aufruf über die `ICloneable` Schnittstelle ruft der umbenannten clienteinstellungsgruppe `InterfaceClone`, aufgerufen, während über ein Objekt des Typs `R` Ruft das zweite `Clone` Instanz.

## <a name="see-also"></a>Siehe auch

[Memberdeklarationen innerhalb einer Klasse oder Schnittstelle (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)<br/>
[Explizite Überschreibungen](../windows/explicit-overrides-cpp-component-extensions.md)