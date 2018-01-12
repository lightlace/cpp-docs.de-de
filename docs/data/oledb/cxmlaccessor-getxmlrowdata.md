---
title: 'CXMLAccessor:: GetXMLRowData | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CXMLAccessor::GetXMLRowData
- ATL.CXMLAccessor.GetXMLRowData
- CXMLAccessor::GetXMLRowData
- CXMLAccessor.GetXMLRowData
- GetXMLRowData
dev_langs: C++
helpviewer_keywords: GetXMLRowData method
ms.assetid: 156b66e3-42fd-491c-8943-38cf5e36f687
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1cfd67065b267f01704bb0658b89d9bab2186100
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cxmlaccessorgetxmlrowdata"></a>CXMLAccessor::GetXMLRowData
Ruft den gesamten Inhalt einer Tabelle als XML-formatierte Zeichenfolgedaten zeilenweise ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT GetXMLRowData(   
   CSimpleStringW& strOutput,   
   bool bAppend = false    
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 `strOutput`  
 [out] Ein Verweis auf einen Puffer, enthält die Tabellendaten abgerufen werden sollen. Die Daten werden als Zeichenfolge mit XML-Tagnamen formatiert, die den Datenspeicher Spaltennamen entsprechen.  
  
 *bAppend*  
 [in] Ein boolescher Wert, der angibt, ob eine Zeichenfolge bis zum Ende der Ausgabedaten angefügt ist.  
  
## <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
## <a name="remarks"></a>Hinweise  
 Das folgende Beispiel zeigt, wie Daten aus der Zeile in XML formatiert ist. `DATA`unten stellt Sie Daten aus der Zeile dar. Verwenden Sie move Methoden, um in die gewünschte Zeile wechseln.  
  
 `<row>`  
  
 `<column name>DATA</column name>`  
  
 `</row>`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CXMLAccessor-Klasse](../../data/oledb/cxmlaccessor-class.md)