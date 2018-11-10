---
title: Konvertieren von Daten, die nicht vom Anbieter unterstützt werden
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
ms.openlocfilehash: 44cdde2bad24d21adbc728c90ecd173717c02b04
ms.sourcegitcommit: 943c792fdabf01c98c31465f23949a829eab9aad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2018
ms.locfileid: "51265190"
---
# <a name="converting-data-not-supported-by-the-provider"></a>Konvertieren von Daten, die nicht vom Anbieter unterstützt werden

Wenn fordert der Consumer einen Datentyp, der vom Anbieter nicht unterstützt wird, wird die OLE DB-Anbieter-Vorlage für code `IRowsetImpl::GetData` Msdadc.dll aufgerufen, um den Datentyp zu konvertieren.

Wenn Sie eine Schnittstelle wie implementieren `IRowsetChange` , erfordert der Datenkonvertierung, rufen Sie Msdaenum.dll, um die Konvertierung erforderlich sind. Verwendung `GetData`, definiert in Atldb.h als Beispiel.

## <a name="see-also"></a>Siehe auch

[Arbeiten mit OLE DB-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)