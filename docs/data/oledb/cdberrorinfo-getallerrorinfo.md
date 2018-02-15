---
title: 'Cdberrorinfo:: Getallerrorinfo | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDBErrorInfo.GetAllErrorInfo
- CDBErrorInfo::GetAllErrorInfo
- ATL::CDBErrorInfo::GetAllErrorInfo
- GetAllErrorInfo
- CDBErrorInfo.GetAllErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- GetAllErrorInfo method
ms.assetid: 630049fa-d296-497a-bbf6-f5d3d71d271d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 90086d0760e477ef41c4d6b59505ff90115f964b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="cdberrorinfogetallerrorinfo"></a>CDBErrorInfo::GetAllErrorInfo
Gibt alle Typen von Fehlerinformationen enthalten sind, in einen Fehlerdatensatz zurück.  
  
## <a name="syntax"></a>Syntax  
  
```
HRESULT GetAllErrorInfo(ULONG ulRecordNum,  
   LCID lcid,  BSTR* pbstrDescription,  
   BSTR* pbstrSource = NULL,  
   GUID* pguid = NULL,  
   DWORD* pdwHelpContext = NULL,  
   BSTR* pbstrHelpFile = NULL) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 *ulRecordNum*  
 [in] Die nullbasierte Nummer des Datensatzes für die Fehlerinformationen zurückgegeben.  
  
 `lcid`  
 [in] Die Gebietsschema-ID für die Fehlerinformationen zurückgegeben werden.  
  
 `pbstrDescription`  
 [out] Ein Zeiger auf eine textbeschreibung des Fehlers oder NULL, wenn das Gebietsschema nicht unterstützt wird. Siehe Hinweise.  
  
 `pbstrSource`  
 [out] Ein Zeiger auf eine Zeichenfolge, die mit dem Namen der Komponente, die den Fehler generiert hat.  
  
 `pguid`  
 [out] Ein Zeiger auf die GUID der Schnittstelle, die den Fehler definiert.  
  
 *pdwHelpContext*  
 [out] Ein Zeiger auf die Hilfekontext-ID für den Fehler.  
  
 *pbstrHelpFile*  
 [out] Ein Zeiger auf eine Zeichenfolge, enthält des Pfads zur Hilfedatei, die den Fehler beschreibt.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei Erfolg `S_OK`. Finden Sie unter [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) in der *OLE DB Programmer's Reference* für andere Werte zurückgeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="remarks"></a>Hinweise  
 Der Ausgabewert `pbstrDescription` intern erhalten, indem Sie aufrufende IErrorInfo:: GetDescription, die den Wert auf NULL festlegt, wenn das Gebietsschema nicht unterstützt wird, oder wenn beide der folgenden Bedingungen zutreffen:  
  
1.  der Wert des `lcid` ist nicht USA Englisch und  
  
2.  der Wert des `lcid` ist nicht gleich der vom GetUserDefaultLCID zurückgegebene Wert.  
  
## <a name="see-also"></a>Siehe auch  
 [CDBErrorInfo-Klasse](../../data/oledb/cdberrorinfo-class.md)