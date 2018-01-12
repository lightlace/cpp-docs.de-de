---
title: 'CRestrictions:: Open | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRestrictions.Open
- ATL::CRestrictions::Open
- ATL.CRestrictions.Open
- CRestrictions::Open
dev_langs: C++
helpviewer_keywords: Open method
ms.assetid: 0aff0cc3-543a-47d2-8d6b-ebb36926b6db
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bbb0b175a6fa5a6cf93b4fe107884d5bb84f2487
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="crestrictionsopen"></a>CRestrictions::Open
Gibt ein Resultset entsprechend die benutzerdefinierte Einschränkungen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT Open(  
   const CSession& session,  
   LPCTSTR lpszParam 1 = NULL,  
   LPCTSTR lpszParam 2 = NULL,  
   LPCTSTR lpszParam 3 = NULL,  
   LPCTSTR lpszParam 4 = NULL,  
   LPCTSTR lpszParam 5 = NULL,  
   LPCTSTR lpszParam 6 = NULL,  
   LPCTSTR lpszParam 7 = NULL,  
   bool bBind = true  
);  
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