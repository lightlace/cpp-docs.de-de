---
title: "Konvertieren von Daten, die vom Anbieter nicht unterstützt. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2fd46e57397eba0e8e732bba586df384951a86dc
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="converting-data-not-supported-by-the-provider"></a>Konvertieren von Daten, die nicht vom Anbieter unterstützt werden
Wenn fordert der Consumer einen Datentyp, der vom Anbieter nicht unterstützt wird, wird die Vorlage für OLE DB-Anbieter für code `IRowsetImpl::GetData` Msdadc.dll aufgerufen, um den Datentyp zu konvertieren.  
  
 Wenn Sie eine Schnittstelle wie implementieren `IRowsetChange` , Datenkonvertierung erfordert, rufen Sie Msdaenum.dll, um die Konvertierung erforderlich sind. Verwendung `GetData`, die in "Atldb.h" als Beispiel definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit OLE DB-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)