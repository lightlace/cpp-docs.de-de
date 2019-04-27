---
title: Duale Mehrfachschnittstellen
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- multiple dual interfaces
- COM_INTERFACE_ENTRY2 macro
- dual interfaces, exposing multiple
- multiple dual interfaces, exposing with ATL
- IDispatchImpl class, multiple dual interfaces
- COM_INTERFACE_ENTRY_IID macro
ms.assetid: 7fea86e6-247f-4063-be6e-85588a9e3719
ms.openlocfilehash: 2ed0e9e8c74e02917e852b8f95ebff1b048afaef
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62261578"
---
# <a name="multiple-dual-interfaces"></a>Duale Mehrfachschnittstellen

Möglicherweise möchten Sie die Vorteile eine duale Schnittstelle (d. h. die Flexibilität von Vtable und späte Bindung, daher die Klasse verfügbar zu machen. Skriptsprachen als auch für C++) kombinieren mit den Methoden der mehrfachvererbung.

Obwohl es möglich, mehrere duale Schnittstellen für ein einzelnes COM-Objekt verfügbar zu machen, ist es nicht empfohlen. Wenn mehrere duale Schnittstellen vorhanden sind, ist nur eine `IDispatch` Schnittstelle verfügbar gemacht werden. Techniken zur Verfügung, um sicherzustellen, dass dies der Fall ist, tragen zur Folge haben, z. B. geringere-Funktion oder erhöhten Codekomplexität. Die Entwickler und möchten diesen Ansatz sollte sorgfältig abwägen, die vor- und Nachteile.

## <a name="exposing-a-single-idispatch-interface"></a>Verfügbarmachen von einer einzelnen IDispatch-Schnittstelle

Es ist möglich, mehrere duale Schnittstellen für ein einzelnes Objekt verfügbar machen, durch Ableiten von mindestens zwei spezialisierungen `IDispatchImpl`. Jedoch wenn Sie zulassen, dass Clients bei der Abfrage die `IDispatch` -Schnittstelle, Sie benötigen, verwenden Sie die [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) Makro (oder [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid))) an die Basisklasse für die Verwendung der Implementierung von `IDispatch`.

[!code-cpp[NVC_ATL_COM#23](../atl/codesnippet/cpp/multiple-dual-interfaces_1.h)]

Da nur ein `IDispatch` Schnittstelle verfügbar gemacht wird, Clients, die nur die Objekte über zugreifen können die `IDispatch` Schnittstelle werden nicht auf die Methoden oder Eigenschaften in einer beliebigen anderen Schnittstelle zugreifen.

## <a name="combining-multiple-dual-interfaces-into-a-single-implementation-of-idispatch"></a>Kombinieren von mehreren duale Schnittstellen in eine einzelne Implementierung von IDispatch

ATL bietet keine Unterstützung für das Kombinieren von mehreren duale Schnittstellen in eine einzelne Implementierung von `IDispatch`. Es gibt jedoch mehrere Methoden für die manuelle kombiniert die Schnittstellen, z. B. das Erstellen einer auf Vorlagen basierenden Klasse, die eine Kombination der separaten enthält `IDispatch` Schnittstellen, erstellen ein neues Objekt zum Ausführen der `QueryInterface` -Funktion oder über eine TypeInfo-basierte Implementierung eines geschachtelten Objekte zum Erstellen der `IDispatch` Schnittstelle.

Diese Ansätze haben Probleme mit möglichen Namespacekonflikte, als auch Komplexität von Code und verwaltbarkeit. Es wird nicht empfohlen, dass Sie duale mehrfachschnittstellen erstellen.

## <a name="see-also"></a>Siehe auch

[Duale Schnittstellen und ATL](../atl/dual-interfaces-and-atl.md)
