---
title: Erstellen eines einfachen schreibgeschützten Anbieters | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/26/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c8fd4e5eb25ab1e8e6b20b576a0688da7b5aa2ef
ms.sourcegitcommit: 840033ddcfab51543072604ccd5656fc6d4a5d3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "50216395"
---
# <a name="creating-a-simple-read-only-provider"></a>Erstellen eines einfachen schreibgeschützten Anbieters

Wenn Sie einen OLE DB-Anbieter erstellt haben die **ATL-Projektassistenten** und **ATL-OLE DB-Anbieter-Assistenten**, Sie können andere Funktionen, die Sie unterstützen möchten hinzufügen. Starten Sie das Entwerfen von Ihrem Anbieter anhand der Art von Daten, die an den Consumer und unter welchen Bedingungen gesendet werden müssen. Es ist besonders wichtig, um festzustellen, ob die Befehle, Transaktionen und andere optionale Objekte unterstützt werden müssen. Ein guter Entwurf voraus wird die Implementierung und Testen beschleunigen.

Im Beispiel wird in zwei Teile untergliedert:

- Der erste Teil zeigt wie [erstellen ein einfaches schreibgeschützten Anbieters](../../data/oledb/implementing-the-simple-read-only-provider.md) , liest es sich um ein Paar von Zeichenfolgen.

- Der zweite Teil zeigt wie [Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md) durch Hinzufügen der `IRowsetLocate` Schnittstelle.

## <a name="see-also"></a>Siehe auch

[Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)<br/>
