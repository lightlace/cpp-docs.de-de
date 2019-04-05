---
title: Erstellen eines einfachen schreibgeschützten Anbieters
ms.date: 10/26/2018
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
ms.openlocfilehash: a80678f6bc512c45c0df2ea5cbfc4708f1252ac0
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59035360"
---
# <a name="creating-a-simple-read-only-provider"></a>Erstellen eines einfachen schreibgeschützten Anbieters

Wenn Sie einen OLE DB-Anbieter erstellt haben die **ATL-Projektassistenten** und **ATL-OLE DB-Anbieter-Assistenten**, Sie können andere Funktionen, die Sie unterstützen möchten hinzufügen. Starten Sie das Entwerfen von Ihrem Anbieter anhand der Art von Daten, die an den Consumer und unter welchen Bedingungen gesendet werden müssen. Es ist besonders wichtig, um festzustellen, ob die Befehle, Transaktionen und andere optionale Objekte unterstützt werden müssen. Ein guter Entwurf voraus wird die Implementierung und Testen beschleunigen.

Im Beispiel wird in zwei Teile untergliedert:

- Der erste Teil zeigt wie [erstellen ein einfaches schreibgeschützten Anbieters](../../data/oledb/implementing-the-simple-read-only-provider.md) , liest es sich um ein Paar von Zeichenfolgen.

- Der zweite Teil zeigt wie [Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md) durch Hinzufügen der `IRowsetLocate` Schnittstelle.

## <a name="see-also"></a>Siehe auch

[Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)<br/>
