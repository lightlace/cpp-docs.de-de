---
title: Konvertieren von Daten, die vom Anbieter nicht unterstützt. | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 79889125675a3e544802eb700718dee0829457c5
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50066122"
---
# <a name="converting-data-not-supported-by-the-provider"></a>Konvertieren von Daten, die nicht vom Anbieter unterstützt werden

Wenn fordert der Consumer einen Datentyp, der vom Anbieter nicht unterstützt wird, wird die OLE DB-Anbieter-Vorlage für code `IRowsetImpl::GetData` Msdadc.dll aufgerufen, um den Datentyp zu konvertieren.

Wenn Sie eine Schnittstelle wie implementieren `IRowsetChange` , erfordert der Datenkonvertierung, rufen Sie Msdaenum.dll, um die Konvertierung erforderlich sind. Verwendung `GetData`, definiert in Atldb.h als Beispiel.

## <a name="see-also"></a>Siehe auch

[Arbeiten mit OLE DB-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)