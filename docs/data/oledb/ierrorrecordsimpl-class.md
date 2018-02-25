---
title: IErrorRecordsImpl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::IErrorRecordsImpl
- ATL.IErrorRecordsImpl
- IErrorRecordsImpl
dev_langs:
- C++
helpviewer_keywords:
- IErrorRecordsImpl class
ms.assetid: dea8e938-c5d8-45ab-86de-eb8fbf534ffb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f3d466cbf761342706774a9b5a52c5b4e69a7328
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ierrorrecordsimpl-class"></a>IErrorRecordsImpl-Klasse
Implementiert die OLE DB- [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx) -Schnittstelle, Hinzufügen von Datensätzen an und Abrufen von Datensätzen aus einem Datenmember ([M_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)) vom Typ **CAtlArray <** `RecordClass`**>**.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T, class RecordClass = ATLERRORINFO>  
class IErrorRecordsImpl : public IErrorRecords  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Eine abgeleitete Klasse `IErrorRecordsImpl`.  
  
 `RecordClass`  
 Eine Klasse, die ein OLE DB-Fehler-Objekt darstellt.  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[GetErrorDescriptionString](../../data/oledb/ierrorrecordsimpl-geterrordescriptionstring.md)|Ruft die Zeichenfolge zur fehlerbeschreibung aus Error-Datensatzes ab.|  
|[GetErrorGUID](../../data/oledb/ierrorrecordsimpl-geterrorguid.md)|Ruft den Fehler GUID aus einer Error-Datensatzes ab.|  
|[GetErrorHelpContext](../../data/oledb/ierrorrecordsimpl-geterrorhelpcontext.md)|Ruft die Hilfekontext-ID aus einer Error-Datensatzes ab.|  
|[GetErrorHelpFile](../../data/oledb/ierrorrecordsimpl-geterrorhelpfile.md)|Ruft den vollständigen Pfadnamen der Hilfedatei von Error-Datensatzes ab.|  
|[GetErrorSource](../../data/oledb/ierrorrecordsimpl-geterrorsource.md)|Ruft den Fehlercode für die Datenquelle aus einer Error-Datensatzes ab.|  
  
### <a name="interface-methods"></a>Schnittstellenmethoden  
  
|||  
|-|-|  
|[AddErrorRecord](../../data/oledb/ierrorrecordsimpl-adderrorrecord.md)|Fügt einen Datensatz mit dem OLE DB-Fehler-Objekt.|  
|[GetBasicErrorInfo](../../data/oledb/cdberrorinfo-getbasicerrorinfo.md)|Gibt grundlegende Informationen über den Fehler, z. B. den Rückgabecode und die anbieterspezifische Fehlernummer zurück.|  
|[GetCustomErrorObject](../../data/oledb/cdberrorinfo-getcustomerrorobject.md)|Gibt einen Zeiger auf eine Schnittstelle für eine benutzerdefinierte Fehlerobjekt.|  
|[GetErrorInfo](../../data/oledb/cdberrorinfo-geterrorinfo.md)|Gibt eine [IErrorInfo](https://msdn.microsoft.com/en-us/library/ms718112.aspx) Schnittstellenzeiger auf den angegebenen Datensatz.|  
|[GetErrorParameters](../../data/oledb/cdberrorinfo-geterrorparameters.md)|Der Fehlerparameter zurückgegeben.|  
|[GetRecordCount](../../mfc/reference/cdaorecordset-class.md#getrecordcount)|Gibt die Anzahl der Datensätze in der OLE DB-Datensatz-Objekt zurück.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[m_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)|Ein Array von fehlerdatensätzen.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)