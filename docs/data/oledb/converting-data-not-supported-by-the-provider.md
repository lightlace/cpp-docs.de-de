---
title: Konvertieren von Daten, die vom Anbieter nicht unterstützt. | Microsoft Docs
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
ms.openlocfilehash: d0be19345ff6c425cfbc020f2096ca82680586d8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="converting-data-not-supported-by-the-provider"></a>Konvertieren von Daten, die nicht vom Anbieter unterstützt werden
Wenn fordert der Consumer einen Datentyp, der vom Anbieter nicht unterstützt wird, wird die Vorlage für OLE DB-Anbieter für code `IRowsetImpl::GetData` Msdadc.dll aufgerufen, um den Datentyp zu konvertieren.  
  
 Wenn Sie eine Schnittstelle wie implementieren `IRowsetChange` , Datenkonvertierung erfordert, rufen Sie Msdaenum.dll, um die Konvertierung erforderlich sind. Verwendung `GetData`, die in "Atldb.h" als Beispiel definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit OLE DB-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)