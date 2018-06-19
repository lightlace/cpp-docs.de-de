---
title: 'CManualAccessor:: AddBindEntry | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CManualAccessor::AddBindEntry
- ATL.CManualAccessor.AddBindEntry
- CManualAccessor::AddBindEntry
- AddBindEntry
- CManualAccessor.AddBindEntry
dev_langs:
- C++
helpviewer_keywords:
- AddBindEntry method
ms.assetid: 8556dda9-dda1-4f67-96bc-6031e6c6a271
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 59793bd61b17fe2ead4948932efa1b583da8e1a8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098047"
---
# <a name="cmanualaccessoraddbindentry"></a>CManualAccessor::AddBindEntry
Fügt einen Eintrag für die Bindung den Ausgabespalten.  
  
## <a name="syntax"></a>Syntax  
  
```
void AddBindEntry(DBORDINAL nOrdinal,  
   DBTYPE wType,  DBLENGTH nColumnSize,  
   void* pData,  
   void* pLength = NULL,  
   void* pStatus = NULL) throw ();  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) in der *OLE DB Programmer's Reference*.  
  
 `nOrdinal`  
 [in] Nummer der Spalte.  
  
 `wType`  
 [in] -Datentyp.  
  
 `nColumnSize`  
 [in] Die Größe der Spalte in Bytes.  
  
 `pData`  
 [in] Ein Zeiger auf die Daten der Spalte im Puffer gespeichert.  
  
 `pLength`  
 [in] Ein Zeiger auf die Feldlänge, falls erforderlich.  
  
 `pStatus`  
 [in] Ein Zeiger auf die Variable an den Status der Spalte gebunden werden, falls erforderlich.  
  
## <a name="remarks"></a>Hinweise  
 Um diese Funktion verwenden zu können, müssen Sie zuerst Aufrufen [CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md). Fügen Sie können nicht mehrere Einträge als die Anzahl der Spalten im angegebenen `CreateAccessor`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CManualAccessor-Klasse](../../data/oledb/cmanualaccessor-class.md)   
 [DBViewer-Beispiel](../../visual-cpp-samples.md)