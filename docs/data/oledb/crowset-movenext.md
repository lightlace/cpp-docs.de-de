---
title: 'CRowset:: MoveNext | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CRowset<TAccessor>.MoveNext
- ATL.CRowset.MoveNext
- ATL::CRowset<TAccessor>::MoveNext
- CRowset<TAccessor>.MoveNext
- CRowset.MoveNext
- CRowset<TAccessor>::MoveNext
- CRowset::MoveNext
- ATL::CRowset::MoveNext
dev_langs: C++
helpviewer_keywords: MoveNext method
ms.assetid: 0df3288c-2bce-494f-99c0-6344b54a4adf
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bd997b25125a48dd6103629e6957843295532901
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetmovenext"></a>CRowset::MoveNext
Verschiebt den Cursor auf den nächsten Datensatz.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT MoveNext( ) throw( );   
HRESULT MoveNext(   
   LONG lSkip,   
   bool bForward = true    
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 `lSkip`  
 [in] Die Anzahl der zu überspringenden vor dem Abrufen der Zeilen.  
  
 `bForward`  
 [in] Übergeben Sie **"true"** auf den nächsten Datensatz weitergehen **"false"** um rückwärts zu bewegen.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt. Gibt zurück, wenn das Ende des Rowsets erreicht wurde, **DB_S_ENDOFROWSET**.  
  
## <a name="remarks"></a>Hinweise  
 Dadurch wird die nächste sequenzielle Zeile aus der `CRowset` Objekt, das zum Speichern der vorherigen Position. Wahlweise können Sie zu fortfahren auswählen `lSkip` Zeilen oder rückwärts navigieren.  
  
 Legen Sie die folgenden Eigenschaften vor dem Aufrufen dieser Methode müssen **öffnen** für die Tabelle oder einen Befehl, der das Rowset enthält:  
  
-   **DBPROP_CANSCROLLBACKWARDS** muss `VARIANT_TRUE` Wenn `lSkip` < 0  
  
-   **DBPROP_CANFETCHBACKWARDS** muss `VARIANT_TRUE` Wenn `bForward` = "false"  
  
 Andernfalls (Wenn `lSkip` > = 0 und `bForward` = "true"), müssen Sie keine zusätzlichen Eigenschaften festgelegt werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CRowset-Klasse](../../data/oledb/crowset-class.md)   
 [CRowset:: MoveFirst](../../data/oledb/crowset-movefirst.md)   
 [CRowset:: MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)   
 [CRowset:: MovePrev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)