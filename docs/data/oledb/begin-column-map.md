---
title: BEGIN_COLUMN_MAP | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BEGIN_COLUMN_MAP
dev_langs: C++
helpviewer_keywords: BEGIN_COLUMN_MAP macro
ms.assetid: d6ffe633-e0da-4e33-8faa-f7f259d05420
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 29e62e08ef03d863b17ea0d269cf049b23602774
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="begincolumnmap"></a>BEGIN_COLUMN_MAP
Kennzeichnet den Anfang eines Spaltenzuordnungseintrags.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
BEGIN_COLUMN_MAP(  
x  
 )  
  
```  
  
#### <a name="parameters"></a>Parameter  
 *x*  
 [in] Der Name der Benutzerdatensatzklasse, abgeleitet aus `CAccessor`.  
  
## <a name="remarks"></a>Hinweise  
 Dieses Makro wird im Fall eines einzelnen Accessors in einem Rowset verwendet. Wenn Sie über mehrere Accessoren in einem Rowset verfügen, verwenden Sie [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).  
  
 Das `BEGIN_COLUMN_MAP` -Makro wird mit dem `END_COLUMN_MAP` -Makro abgeschlossen. Dieses Makro wird verwendet, wenn nur ein Accessor im Benutzerdatensatz erforderlich ist.  
  
 Spalten entsprechen den Feldern in dem Rowset, das Sie binden möchten.  
  
## <a name="example"></a>Beispiel  
 Hier sehen Sie ein Beispiel für eine Spalten- und Parameterzuordnung:  
  
 <!--[!CODE [NVC_OLEDB_Consumer#16](../codesnippet/vs_snippets_cpp/nvc_oledb_consumer#16)]  -->
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Funktionen für OLE DB-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN_ENTRY_EX](../../data/oledb/column-entry-ex.md)