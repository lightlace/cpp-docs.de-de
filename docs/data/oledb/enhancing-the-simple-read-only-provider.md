---
title: Erweitern des einfachen schreibgeschützten Anbieters
ms.date: 10/26/2018
helpviewer_keywords:
- read-only poviders [C++]
- IRowsetLocate class
- IRowsetLocate class, adding to OLE DB template providers
- simple read-only poviders [C++]
ms.assetid: cba0e09f-44c1-41c1-9456-332aa13dc158
ms.openlocfilehash: d61f24a9a9abffe836a7f11bd5d1517fddf97fe7
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034075"
---
# <a name="enhancing-the-simple-read-only-provider"></a>Erweitern des einfachen schreibgeschützten Anbieters

In diesem Abschnitt wird gezeigt, wie zur Verbesserung der [einfachen schreibgeschützten Anbieters](../../data/oledb/implementing-the-simple-read-only-provider.md) im vorherigen Abschnitt erstellt haben. `IRowsetLocateImpl` erstellt eine Implementierung für die `IRowsetLocate` Schnittstelle und fügt die lesezeichenunterstützung für Sie hinzu.

Wenn Sie einen funktionierende-Anbieter verfügen, empfiehlt es sich um, um die Aktualisierung des Anbieters, Verarbeiten von Transaktionen, oder Erweitern Sie die Leistung des Algorithmus cursorblock machen Verbesserung. Die meisten Anbieter-Verbesserungen umfassen das Hinzufügen einer Schnittstelle zu einem vorhandenen COM-Objekt.

Im Beispiel in den folgenden Themen wird den Mechanismus zum Abrufen von Zeilen, indem die `IRowsetLocate` -Schnittstelle `CAgentRowset`. Die Themen zeigen Ihnen, wie auf:

- [Stellen RCustomRowset IRowsetLocate erben](../../data/oledb/modifying-the-inheritance-of-rmyproviderrowset.md).

- [Dynamisches Festlegen der an den Consumer zurückgegebenen Spalten](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).

## <a name="see-also"></a>Siehe auch

[Erstellen eines einfachen schreibgeschützten Anbieters](../../data/oledb/creating-a-simple-read-only-provider.md)<br/>
