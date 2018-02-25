---
title: 'CRowset:: SetData | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CRowset<TAccessor>.SetData
- SetData
- ATL::CRowset::SetData
- CRowset<TAccessor>.SetData
- CRowset::SetData
- ATL.CRowset.SetData
- CRowset.SetData
- CRowset<TAccessor>::SetData
- ATL::CRowset<TAccessor>::SetData
dev_langs:
- C++
helpviewer_keywords:
- SetData method
ms.assetid: 68125142-8510-4132-9393-e39efd39c784
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2d9f42397ffaa186bfd96db454251c687b634d69
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="crowsetsetdata"></a>CRowset::SetData
Legt Datenwerte in einer oder mehreren Spalten einer Zeile fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT SetData() const throw();   


HRESULT SetData(int nAccessor) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `nAccessor`  
 [in] Die Anzahl der Zugriffsmethode für den Zugriff auf die Daten verwendet werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Für die `SetData` Formular, das akzeptiert keine Argumente verwendet, sind alle Accessoren werden zum Aktualisieren. Rufen Sie in der Regel **SetData** aufrufen, um Datenwerte in Spalten in einer Zeile festzulegen, klicken Sie dann [Update](../../data/oledb/crowset-update.md) diese Änderungen zu übertragen.  
  
 Bei dieser Methode muss die optionale Schnittstelle `IRowsetChange`, die möglicherweise nicht auf allen Anbietern unterstützt, wenn dies der Fall ist, gibt die Methode **E_NOINTERFACE**. Sie müssen auch festlegen **DBPROP_IRowsetChange** auf `VARIANT_TRUE` vor dem Aufruf **öffnen** für die Tabelle oder einen Befehl, der das Rowset enthält.  
  
 Der Vorgang kann fehlschlagen, wenn eine oder mehrere Spalten ist nicht beschreibbar. Ändern Sie die Cursorzuordnung, um diesen Fehler zu beheben.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CRowset-Klasse](../../data/oledb/crowset-class.md)   
 [CRowset::Update](../../data/oledb/crowset-update.md)