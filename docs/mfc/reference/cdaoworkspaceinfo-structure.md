---
title: CDaoWorkspaceInfo-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoWorkspaceInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoWorkspaceInfo structure [MFC]
- DAO (Data Access Objects), Workspaces collection
ms.assetid: a1f4b25e-f9c6-4196-b075-d1df99c54124
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 705c855a817f0c6ca342e51258c7d6c1e61fa392
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951077"
---
# <a name="cdaoworkspaceinfo-structure"></a>CDaoWorkspaceInfo-Struktur
Die `CDaoWorkspaceInfo` Struktur enthält Informationen über einen Arbeitsbereich für den Datenbankzugriff für Data Access Objects (DAO) definiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CDaoWorkspaceInfo  
{  
    CString m_strName;           // Primary  
    CString m_strUserName;       // Secondary  
    BOOL m_bIsolateODBCTrans;    // All  
};  
```  
  
#### <a name="parameters"></a>Parameter  
 *m_strName*  
 Eindeutig Objektnamen Arbeitsbereich. Um den Wert dieser Eigenschaft direkt zu abzurufen, rufen Sie des Querydef Objekts [GetName](../../mfc/reference/cdaoquerydef-class.md#getname) Memberfunktion. Weitere Informationen finden Sie im Thema "Name-Eigenschaft" DAO-Hilfe.  
  
 *m_strUserName*  
 Ein Wert, der den Besitzer eines Arbeitsbereichs-Objekts darstellt. Verwandte Informationen finden Sie im Thema "UserName-Eigenschaft" DAO-Hilfe.  
  
 *m_bIsolateODBCTrans*  
 Ein Wert, der angibt, ob mehrere Transaktionen, die die gleiche ODBC-Datenbank isoliert sind. Weitere Informationen finden Sie unter [CDaoWorkspace::SetIsolateODBCTrans](../../mfc/reference/cdaoworkspace-class.md#setisolateodbctrans). Verwandte Informationen finden Sie im Thema "IsolateODBCTrans-Eigenschaft" DAO-Hilfe.  
  
## <a name="remarks"></a>Hinweise  
 Der Arbeitsbereich ist ein Objekt der Klasse [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md). Die Verweise auf die primäre, sekundäre Datenbank und alle oben anzugeben, wie die Informationen zurückgegeben werden, durch die [GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) Memberfunktion in Klasse `CDaoWorkspace`.  
  
 Informationen, die abgerufen, indem die [CDaoWorkspace::GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) Memberfunktion befindet sich in einer `CDaoWorkspaceInfo` Struktur. `CDaoWorkspaceInfo` definiert auch einen `Dump` Memberfunktion in Debug-builds. Sie können `Dump` auf den Inhalt des Basisklassenobjekts auszugeben ein `CDaoWorkspaceInfo` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoWorkspace-Klasse](../../mfc/reference/cdaoworkspace-class.md)
