---
title: 'CRowset:: MoveNext | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CRowset<TAccessor>.MoveNext
- ATL.CRowset.MoveNext
- ATL::CRowset<TAccessor>::MoveNext
- CRowset<TAccessor>.MoveNext
- CRowset.MoveNext
- CRowset<TAccessor>::MoveNext
- CRowset::MoveNext
- ATL::CRowset::MoveNext
dev_langs:
- C++
helpviewer_keywords:
- MoveNext method
ms.assetid: 0df3288c-2bce-494f-99c0-6344b54a4adf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6c56e3dc53699f47c9dc1061120a201ef5698c04
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="crowsetmovenext"></a>CRowset::MoveNext
Verschiebt den Cursor auf den nächsten Datensatz.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT MoveNext() throw();HRESULT MoveNext(LONG lSkip,   
   bool bForward= true) throw();  
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
 [CRowset::MoveFirst](../../data/oledb/crowset-movefirst.md)   
 [CRowset::MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)