---
title: Compilerattribute (C++-COM-) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, attributes
- attributes [C++/CLI], compiler
ms.assetid: 53cd9bee-1521-48ec-b171-80feac2096cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9f0483676fd0dd60d893f8931511083d369539dd
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791191"
---
# <a name="compiler-attributes"></a>Compilerattribute

Compilerattribute bieten eine Vielzahl von Funktionen.

|Attribut|Beschreibung|
|---------------|-----------------|
|[emitidl](emitidl.md)|Bestimmt, ob alle nachfolgenden IDL-Attribute verarbeitet und in der generierten IDL-Datei platziert werden.|
|[event_receiver](event-receiver.md)|Erstellt einen Ereignisempfänger an.|
|[event_source](event-source.md)|Erstellt eine Ereignisquelle.|
|[export](export.md)|Bewirkt, dass eine Datenstruktur, in der IDL-Datei platziert wird.|
|[Implementiert](implements-cpp.md)|Gibt die Dispatch-Schnittstellen, die erzwungen werden, um die IDL-Co-Klasse angehören.|
|[importidl](importidl.md)|Fügt die angegebenen IDL-Datei in der generierten IDL-Datei an.|
|[importlib](importlib.md)|Stellt Typen, die bereits in einer anderen Typbibliothek kompiliert wurden, der erstellten Typbibliothek zur Verfügung.|
|[includelib](includelib-cpp.md)|Bewirkt, dass eine IDL- oder h-Datei, die in der generierten IDL-Datei eingeschlossen werden.|
|[library_block](library-block.md)|Fügt ein Konstrukt in bibliotheksblock der IDL-Datei an.|
|[no_injected_text](no-injected-text.md)|Verhindert, dass den Compiler Einfügen von Code durch Verwendung des Attributs.|
|[satype](satype.md)|Gibt den Datentyp, der die `SAFEARRAY`.|
|[version](version-cpp.md)|Identifiziert eine bestimmte Version mehrere Versionen einer Schnittstelle oder Klasse an.|

## <a name="see-also"></a>Siehe auch

[Attribute nach Gruppen](attributes-by-group.md)