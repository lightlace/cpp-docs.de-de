---
title: 'CDataSource:: Openwithpromptfilename | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataSource.OpenWithPromptFileName
- OpenWithPromptFileName
- ATL::CDataSource::OpenWithPromptFileName
- ATL.CDataSource.OpenWithPromptFileName
- CDataSource::OpenWithPromptFileName
dev_langs:
- C++
helpviewer_keywords:
- OpenWithPromptFileName method
ms.assetid: 89460504-1aaf-4412-aa7b-fa5a4b39ada3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 318ec8fbba3845fd3e7a15d2efea6ba658712cf0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cdatasourceopenwithpromptfilename"></a>CDataSource::OpenWithPromptFileName
Mit dieser Methode wird dem Benutzer ein Dialogfeld angezeigt und anschließend eine Datenquelle mithilfe der vom Benutzer angegebenen Datei geöffnet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT OpenWithPromptFileName(HWND hWnd = GetActiveWindow(   ),   
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_NONE,   
   LPCOLESTR szInitialDirectory = NULL) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `hWnd`  
 [in] Handle für das Fenster, das als das übergeordnete Element des Dialogfelds festgelegt werden soll.  
  
 `dwPromptOptions`  
 [in] Bestimmt den Stil des anzuzeigenden Locatordialogfelds. Mögliche Werte sind in Msdasc.h aufgeführt.  
  
 *szInitialDirectory*  
 [in] Das im Locatordialogfeld anzuzeigende Ausgangsverzeichnis.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode öffnet ein Datenquellenobjekt mit den Dienstkomponenten im oledb32.dll; Diese DLL enthält die Implementierung von Dienstkomponentenfunktionen wie z. B. Ressourcenpooling, automatische Transaktionseintragung usw. Weitere Informationen finden Sie unter "OLE DB-Dienste" in der OLE DB Programmer's Reference am [ http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true ](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDataSource-Klasse](../../data/oledb/cdatasource-class.md)