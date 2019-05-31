---
title: Erstellen eines einfachen schreibgeschützten Anbieters
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
ms.openlocfilehash: c0f31818002ce4611926d942b3bc556e31c1ae6f
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2019
ms.locfileid: "65524712"
---
# <a name="creating-a-simple-read-only-provider"></a>Erstellen eines einfachen schreibgeschützten Anbieters

::: moniker range="vs-2019"

Der ATL-OLE DB-Anbieter-Assistent ist in Visual Studio 2019 und höher nicht verfügbar.

::: moniker-end

::: moniker range="vs-2017"

Wenn Sie mit dem **ATL-Projekt-Assistenten** und dem **ATL-OLE DB-Anbieter-Assistenten** einen OLE DB-Anbieter erstellt haben, können Sie weitere Funktionen hinzufügen, die Sie unterstützen möchten. Beginnen Sie mit dem Entwerfen des Anbieters, indem Sie untersuchen, welche Arten von Daten unter welchen Bedingungen an den Consumer gesendet werden sollen. Es ist sehr wichtig, zu ermitteln, ob Sie Befehle, Transaktionen und weitere optionale Objekte unterstützen müssen. Ein von vorneherein guter Entwurf beschleunigt Implementierung und Tests.

Das Beispiel wird in zwei Teilen vorgestellt:

- Der erste Teil zeigt das [Erstellen eines einfachen schreibgeschützten Anbieters](../../data/oledb/implementing-the-simple-read-only-provider.md), der ein Zeichenfolgenpaar liest.

- Der zweite Teil zeigt das [Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md) durch Hinzufügen der `IRowsetLocate`-Schnittstelle.

::: moniker-end

## <a name="see-also"></a>Siehe auch

[Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)<br/>
