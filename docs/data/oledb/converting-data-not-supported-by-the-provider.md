---
title: Konvertieren von Daten, die nicht vom Anbieter unterstützt werden
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
ms.openlocfilehash: e60f6cd4f7dca1ed3e176cabefc42f69946436a4
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033838"
---
# <a name="converting-data-not-supported-by-the-provider"></a>Konvertieren von Daten, die nicht vom Anbieter unterstützt werden

Wenn fordert der Consumer einen Datentyp, der vom Anbieter nicht unterstützt wird, wird die OLE DB-Anbieter-Vorlage für code `IRowsetImpl::GetData` Msdadc.dll aufgerufen, um den Datentyp zu konvertieren.

Wenn Sie eine Schnittstelle wie implementieren `IRowsetChange` , erfordert der Datenkonvertierung, rufen Sie Msdaenum.dll, um die Konvertierung erforderlich sind. Verwendung `GetData`, definiert in Atldb.h als Beispiel.

## <a name="see-also"></a>Siehe auch

[Arbeiten mit OLE DB-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)