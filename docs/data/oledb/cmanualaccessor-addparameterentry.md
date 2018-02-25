---
title: 'CManualAccessor:: AddParameterEntry | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CManualAccessor::AddParameterEntry
- ATL.CManualAccessor.AddParameterEntry
- CManualAccessor.AddParameterEntry
- AddParameterEntry
- ATL::CManualAccessor::AddParameterEntry
dev_langs:
- C++
helpviewer_keywords:
- AddParameterEntry method
ms.assetid: 9048b164-052b-41b1-a861-227fc529e0b5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ab686bfed7abd3bece3effbcf9f5e2b98132bb8b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cmanualaccessoraddparameterentry"></a>CManualAccessor::AddParameterEntry
Die Parameter Eintrag Strukturen wird ein Parametereintrag eines hinzugefügt.  
  
## <a name="syntax"></a>Syntax  
  
```
void AddParameterEntry(DBORDINAL nOrdinal,  
   DBTYPE wType,  DBLENGTH nColumnSize,  
   void* pData,  
   void* pLength = NULL,  
   void* pStatus = NULL,  
   DBPARAMIO eParamIO = DBPARAMIO_INPUT) throw ();  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) in der *OLE DB Programmer's Reference*.  
  
 `nOrdinal`  
 [in] Parameter mit der Nummer.  
  
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
  
 *eParamIO*  
 [in] Gibt an, ob der Parameter, den Bindung zugeordnet ist, ein Eingabe-, Eingabe/Ausgabe- oder Ausgabeparameter besteht.  
  
## <a name="remarks"></a>Hinweise  
 Um diese Funktion verwenden zu können, müssen Sie zuerst Aufrufen [CreateParameterAccessor](../../data/oledb/cmanualaccessor-createparameteraccessor.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CManualAccessor-Klasse](../../data/oledb/cmanualaccessor-class.md)   
 [CManualAccessor::AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md)   
 [DBViewer-Beispiel](../../visual-cpp-samples.md)