---
title: ATL-Modulklassen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CComModule class, what's changed
- ATL, module classes
- module classes
ms.assetid: fd75382d-c955-46ba-a38e-37728b7fa00f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e885ef1db8f282bbdca2e8c39c3d1221d791d1a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067635"
---
# <a name="atl-module-classes"></a>ATL-Modulklassen

Dieses Thema behandelt die Modulklassen, die neu in ATL 7.0 waren.

## <a name="ccommodule-replacement-classes"></a>CComModule-Ersatz-Klassen

Frühere Versionen von ATL verwendet `CComModule`. In ATL 7.0 `CComModule` Funktionalität wird von mehreren Klassen ersetzt:

- [CAtlBaseModule](../atl/reference/catlbasemodule-class.md) enthält Informationen, die von den meisten Anwendungen, die ATL verwenden erforderlich Enthält die HINSTANCE des Moduls und die Ressourceninstanz an.

- [CAtlComModule](../atl/reference/catlcommodule-class.md) enthält Informationen, die durch die COM-Klassen in ATL erforderlich

- [CAtlWinModule](../atl/reference/catlwinmodule-class.md) enthält Informationen, die von den Windowing-Klassen in ATL erforderlich

- [CAtlDebugInterfacesModule](../atl/reference/catldebuginterfacesmodule-class.md) enthält Unterstützung für das Debuggen.

- [CAtlModule](../atl/reference/catlmodule-class.md) Folgendes `CAtlModule`-abgeleitete Klassen werden angepasst, um die erforderlichen Informationen in einem bestimmten Anwendungstyp enthalten. Die meisten Elemente in diesen Klassen können überschrieben werden:

   - [CAtlDllModuleT](../atl/reference/catldllmodulet-class.md) in DLL-Anwendungen verwendet. Stellt den Code für die standard-Exporte bereit.

   - [CAtlExeModuleT](../atl/reference/catlexemodulet-class.md) in EXE-Anwendungen verwendet. Enthält Code, die in einer EXE-Datei erforderlich.

   - [CAtlServiceModuleT](../atl/reference/catlservicemodulet-class.md) bietet Unterstützung zum Erstellen von Windows NT und Windows 2000-Diensten.

`CComModule` ist für die Abwärtskompatibilität noch verfügbar.

## <a name="reasons-for-distributing-ccommodule-functionality"></a>Gründe für die Verteilung der CComModule-Funktion

Die Funktionalität von `CComModule` in mehrere neue Klassen verteilt wurde, den folgenden Gründen:

- Stellen Sie die Funktionalität in `CComModule` präzise.

     Unterstützung für COM, Windowing, Debuggen von Schnittstellen und anwendungsspezifischen Features für (DLL oder EXE-Datei) ist jetzt in separaten Klassen.

- Deklarieren Sie globale Instanz für jedes dieser Module automatisch.

     Eine globale Instanz das erforderliche Modul-Klassen, die in das Projekt verknüpft ist.

- Entfernen Sie die Notwendigkeit, Init "und" Begriff Methoden aufrufen.

     Init "und" Begriff Methoden wurden in den Konstruktoren und Destruktoren für Modulklassen verschoben; Es ist nicht mehr Init "und" Begriff aufrufen müssen.

## <a name="see-also"></a>Siehe auch

[Konzepte](../atl/active-template-library-atl-concepts.md)<br/>
[Übersicht über die Klasse](../atl/atl-class-overview.md)

