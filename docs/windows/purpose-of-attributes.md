---
title: Attributzwecke | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], about attributes
ms.assetid: 3aff8bfa-a2a3-4fcb-a2c6-1d96a2b4c68d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2b34ff9641df4d102c2902e5b8ea42a80db4db50
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607099"
---
# <a name="purpose-of-attributes"></a>Attributzwecke

Attribute erweitern C++ in Anweisungen, die derzeit nicht möglich, ohne die klassischen Struktur der Sprache. Attribute können Anbieter (separate DLLs), um Funktionalität Language dynamisch zu erweitern. Das Hauptziel von Attributen ist zur Vereinfachung der Erstellung von COM-Komponenten sowie gleichzeitig die Produktivität der Komponentenentwickler. Es können Attribute angewendet werden, nahezu jedem C++-Konstrukt, wie z. B. Klassen, die Datenmember oder Memberfunktionen. Im folgenden finden eine Hervorhebung der Vorteile dieser neuen Technologie:

- Stellt eine vertraute und einfache Aufrufkonvention.

- Verwendet eingefügten Code, der, im Gegensatz zu Makros, die vom Debugger erkannt wird.

- Ermöglicht die einfache Ableitung von Basisklassen ohne aufwändige Implementierungsdetails.

- Ersetzt die große Menge der IDL-Code, die von einer COM‑Komponente, einige Attribute, die präzise erforderlich.

Beispielsweise um einen einfachen Ereignisempfänger für eine generische ATL-Klasse zu implementieren, Sie können Anwenden der [Event_receiver](../windows/event-receiver.md) Attribut für eine bestimmte Objektklasse, z. B. `CMyReceiver`. Die `event_receiver` Attribut wird dann kompiliert, vom Visual C++-Compiler, die den entsprechenden Code in der Objektdatei einfügt.

```cpp
[event_receiver(com)]
class CMyReceiver
{
   void handler1(int i) { ... }
   void handler2(int i, float j) { ... }
}
```

Anschließend können Sie festlegen, um die `CMyReceiver` Methoden `handler1` und `handler2` zum Behandeln von Ereignissen (verwenden die intrinsische Funktion [__hook](../cpp/hook.md)) aus einer Ereignisquelle, die Sie erstellen können, mit [Event_source](../windows/event-source.md).

## <a name="see-also"></a>Siehe auch

[Konzepte](../windows/attributed-programming-concepts.md)