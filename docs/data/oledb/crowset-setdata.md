---
title: 'CRowset:: SetData | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b8885c6e64fa7e7e22f6858d916a8e1afa8738d6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098471"
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