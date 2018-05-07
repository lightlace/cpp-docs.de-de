---
title: 'CRestrictions:: Open | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRestrictions.Open
- ATL::CRestrictions::Open
- ATL.CRestrictions.Open
- CRestrictions::Open
dev_langs:
- C++
helpviewer_keywords:
- Open method
ms.assetid: 0aff0cc3-543a-47d2-8d6b-ebb36926b6db
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8039d55312687cc28be27f2ed7726b9bda1b44aa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="crestrictionsopen"></a>CRestrictions::Open
Gibt ein Resultset entsprechend die benutzerdefinierte Einschränkungen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT Open(const CSession& session,  
   LPCTSTR lpszParam 1 = NULL,  
   LPCTSTR lpszParam 2 = NULL,  
   LPCTSTR lpszParam 3 = NULL,  
   LPCTSTR lpszParam 4 = NULL,  
   LPCTSTR lpszParam 5 = NULL,  
   LPCTSTR lpszParam 6 = NULL,  
   LPCTSTR lpszParam 7 = NULL,  
   bool bBind = true);  
```  
  
#### <a name="parameters"></a>Parameter  
 `session`  
 [in] Gibt ein vorhandenes Session-Objekt, das für die Verbindung mit der Datenquelle verwendet.  
  
 *lpszParam*  
 [in] Gibt an, die Einschränkungen für das Schemarowset.  
  
 `bBind`  
 [in] Gibt an, ob die spaltenzuordnung automatisch zu binden. Die Standardeinstellung ist **"true"**, womit die spaltenzuordnung automatisch gebunden werden. Festlegen von `bBind` auf **"false"** wird verhindert, dass die automatische Bindung der spaltenzuordnung, damit Sie manuell binden können. (Manuelle Bindung ist von besonderem Interesse für OLAP-Benutzer).  
  
## <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
## <a name="remarks"></a>Hinweise  
 Sie können maximal sieben Einschränkungen für ein Schemarowset angeben.  
  
 Finden Sie unter [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) für Informationen zu den definierten Einschränkungen für jedes Schemarowset.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** "atldbsch.h" Einfügen  
  
## <a name="see-also"></a>Siehe auch  
 [CRestrictions-Klasse](../../data/oledb/crestrictions-class.md)   
 [Schemarowset-Klassen und Typedef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)