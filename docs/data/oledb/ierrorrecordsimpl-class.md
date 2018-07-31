---
title: IErrorRecordsImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IErrorRecordsImpl
- ATL.IErrorRecordsImpl
- IErrorRecordsImpl
- GetErrorDescriptionString
- IErrorRecordsImpl.GetErrorDescriptionString
- IErrorRecordsImpl::GetErrorDescriptionString
- GetErrorGUID
- IErrorRecordsImpl.GetErrorGUID
- IErrorRecordsImpl::GetErrorGUID
- GetErrorHelpContext
- IErrorRecordsImpl::GetErrorHelpContext
- IErrorRecordsImpl.GetErrorHelpContext
- IErrorRecordsImpl::GetErrorHelpFile
- GetErrorHelpFile
- IErrorRecordsImpl.GetErrorHelpFile
- IErrorRecordsImpl.GetErrorSource
- GetErrorSource
- IErrorRecordsImpl::GetErrorSource
- IErrorRecordsImpl.AddErrorRecord
- AddErrorRecord
- IErrorRecordsImpl::AddErrorRecord
- ATL::IErrorRecordsImpl::GetBasicErrorInfo
- IErrorRecordsImpl::GetBasicErrorInfo
- GetBasicErrorInfo
- ATL.IErrorRecordsImpl.GetBasicErrorInfo
- IErrorRecordsImpl.GetBasicErrorInfo
- ATL::IErrorRecordsImpl::GetCustomErrorObject
- IErrorRecordsImpl::GetCustomErrorObject
- ATL.IErrorRecordsImpl.GetCustomErrorObject
- IErrorRecordsImpl.GetCustomErrorObject
- GetCustomErrorObject
- GetErrorInfo
- IErrorRecordsImpl.GetErrorInfo
- IErrorRecordsImpl::GetErrorInfo
- IErrorRecordsImpl::GetErrorParameters
- ATL.IErrorRecordsImpl.GetErrorParameters
- IErrorRecordsImpl.GetErrorParameters
- GetErrorParameters
- ATL::IErrorRecordsImpl::GetErrorParameters
- IErrorRecordsImpl::GetRecordCount
- ATL::IErrorRecordsImpl::GetRecordCount
- IErrorRecordsImpl.GetRecordCount
- ATL.IErrorRecordsImpl.GetRecordCount
- IErrorRecordsImpl::m_rgErrors
- IErrorRecordsImpl.m_rgErrors
- ATL.IErrorRecordsImpl.m_rgErrors
- m_rgErrors
- ATL::IErrorRecordsImpl::m_rgErrors
dev_langs:
- C++
helpviewer_keywords:
- IErrorRecordsImpl class
- GetErrorDescriptionString method
- GetErrorGUID method
- GetErrorHelpContext method
- GetErrorHelpFile method
- GetErrorSource method
- AddErrorRecord method
- GetBasicErrorInfo method
- GetCustomErrorObject method
- GetErrorInfo method
- GetErrorParameters method
- GetRecordCount method
- m_rgErrors
ms.assetid: dea8e938-c5d8-45ab-86de-eb8fbf534ffb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7339b345ad63f59a2db24251c06b80774305ab00
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338118"
---
# <a name="ierrorrecordsimpl-class"></a>IErrorRecordsImpl-Klasse
Implementiert die OLE DB [IErrorRecords](https://msdn.microsoft.com/library/ms718112.aspx) Schnittstelle, Hinzufügen von Einträgen zu und Abrufen von Datensätzen aus einem Datenmember ([M_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)) vom Typ **CAtlArray <** `RecordClass`**>**.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T, class RecordClass = ATLERRORINFO>  
class IErrorRecordsImpl : public IErrorRecords  
```  
  
### <a name="parameters"></a>Parameter  
 *T*  
 Eine abgeleitete Klasse `IErrorRecordsImpl`.  
  
 *RecordClass*  
 Eine Klasse, die ein OLE DB-Error-Objekt darstellt.  

## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[GetErrorDescriptionString](#geterrordescriptionstring)|Ruft die Zeichenfolge zur fehlerbeschreibung aus einen Fehlerdatensatz ab.|  
|[GetErrorGUID](#geterrorguid)|Ruft den GUID-Fehler aus einen Fehlerdatensatz ab.|  
|[GetErrorHelpContext](#geterrorhelpcontext)|Ruft die Hilfekontext-ID aus einen Fehlerdatensatz ab.|  
|[GetErrorHelpFile](#geterrorhelpfile)|Ruft den vollständigen Pfadnamen der Hilfedatei aus einen Fehlerdatensatz ab.|  
|[GetErrorSource](#geterrorsource)|Ruft den Fehlercode für die Quelle über einen Fehlerdatensatz ab.|  
  
### <a name="interface-methods"></a>Schnittstellenmethoden  
  
|||  
|-|-|  
|[AddErrorRecord](#adderrorrecord)|Fügt einen Datensatz auf den OLE DB-Error-Objekt.|  
|[GetBasicErrorInfo](#getbasicerrorinfo)|Gibt grundlegende Informationen über den Fehler, z. B. den Rückgabecode und die Anzahl der Anbieter-spezifischer Fehler zurück.|  
|[GetCustomErrorObject](#getcustomerrorobject)|Gibt einen Zeiger auf eine Schnittstelle für einen benutzerdefinierten Fehler-Objekt zurück.|  
|[GetErrorInfo](#geterrorinfo)|Gibt eine [IErrorInfo](https://msdn.microsoft.com/library/ms718112.aspx) Schnittstellenzeiger auf den angegebenen Datensatz.|  
|[GetErrorParameters](#geterrorparameters)|Gibt die Fehlerparameter zurück.|  
|[GetRecordCount](#getrecordcount)|Gibt die Anzahl der Datensätze in der OLE DB-Datensatz-Objekt zurück.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[m_rgErrors](#rgerrors)|Ein Array von fehlerdatensätzen.|  

## <a name="geterrordescriptionstring"></a> IErrorRecordsImpl:: Geterrordescriptionstring
Ruft die Zeichenfolge zur fehlerbeschreibung aus einen Fehlerdatensatz ab.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
LPOLESTR GetErrorDescriptionString(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>Parameter  
 *rCurError*  
 Ein `ERRORINFO` Datensatz in einer `IErrorInfo` Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine Zeichenfolge, die den Fehler beschreibt.  
  
## <a name="geterrorguid"></a> IErrorRecordsImpl:: Geterrorguid
Ruft den GUID-Fehler aus einen Fehlerdatensatz ab.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
REFGUID GetErrorGUID(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>Parameter  
 *rCurError*  
 Ein `ERRORINFO` Datensatz in einer `IErrorInfo` Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf eine GUID für den Fehler.  

## <a name="geterrorhelpcontext"></a> IErrorRecordsImpl:: Geterrorhelpcontext
Ruft die Hilfekontext-ID aus einen Fehlerdatensatz ab.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
DWORD GetErrorHelpContext(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>Parameter  
 *rCurError*  
 Ein `ERRORINFO` Datensatz in einer `IErrorInfo` Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Hilfekontext-ID für den Fehler.  

## <a name="geterrorhelpfile"></a> IErrorRecordsImpl:: Geterrorhelpfile
Ruft den Pfadnamen der Hilfedatei aus einen Fehlerdatensatz ab.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
LPOLESTR GetErrorHelpFile(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>Parameter  
 *rCurError*  
 Ein `ERRORINFO` Datensatz in einer `IErrorInfo` Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine Zeichenfolge, die den Pfadnamen der Hilfedatei für den Fehler enthält.

## <a name="geterrorsource"></a> IErrorRecordsImpl:: Geterrorsource
Ruft den Quellcode, der den Fehler verursacht, über einen Fehlerdatensatz hat ab.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
LPOLESTR GetErrorSource(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>Parameter  
 *rCurError*  
 Ein `ERRORINFO` Datensatz in einer `IErrorInfo` Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine Zeichenfolge, die den Quellcode für den Fehler enthält. 

## <a name="adderrorrecord"></a> IErrorRecordsImpl:: Adderrorrecord
Fügt einen Datensatz auf den OLE DB-Error-Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
STDMETHOD(AddErrorRecord )(ERRORINFO *pErrorInfo,  
   DWORD dwLookupID,  
   DISPPARAMS *pdispparams,  
   IUnknown *punkCustomError,  
   DWORD dwDynamicErrorID);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IErrorRecords::AddErrorRecord](https://msdn.microsoft.com/library/ms725362.aspx) in die *OLE DB-Programmierreferenz*.  

## <a name="getbasicerrorinfo"></a> IErrorRecordsImpl:: Getbasicerrorinfo
Gibt grundlegende Informationen über den Fehler, z. B. den Rückgabecode und die Anzahl der Anbieter-spezifischer Fehler zurück.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
STDMETHOD(GetBasicErrorInfo )(ULONG ulRecordNum,  
   ERRORINFO *pErrorInfo);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/library/ms723907.aspx) in die *OLE DB-Programmierreferenz*. 

## <a name="getcustomerrorobject"></a> IErrorRecordsImpl:: Getcustomerrorobject
Gibt einen Zeiger auf eine Schnittstelle für einen benutzerdefinierten Fehler-Objekt zurück.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
STDMETHOD(GetCustomErrorObject )(ULONG ulRecordNum,  
   REFIID riid,  
   IUnknown **ppObject);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/library/ms725417.aspx) in die *OLE DB-Programmierreferenz*.  

## <a name="geterrorinfo"></a> IErrorRecordsImpl:: GetErrorInfo
Gibt eine [IErrorInfo](https://msdn.microsoft.com/library/ms718112.aspx) Schnittstellenzeiger auf den angegebenen Datensatz.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
STDMETHOD(GetErrorInfo )(ULONG ulRecordNum,  
   LCID lcid,  
   IErrorInfo **ppErrorInfo);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/library/ms711230.aspx) in die *OLE DB-Programmierreferenz*.

## <a name="geterrorparameters"></a> IErrorRecordsImpl:: Geterrorparameters
Gibt die Fehlerparameter zurück.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
STDMETHOD(GetErrorParameters )(ULONG ulRecordNum,  
   DISPPARAMS *pdispparams);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/library/ms715793.aspx) in die *OLE DB-Programmierreferenz*.  

## <a name="getrecordcount"></a> IErrorRecordsImpl:: GetRecordCount
Gibt die Anzahl der Datensätze in der OLE DB-Datensatz-Objekt zurück.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
STDMETHOD(GetRecordCount )(ULONG *pcRecords);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IErrorRecords::GetRecordCount](https://msdn.microsoft.com/library/ms722724.aspx) in die *OLE DB-Programmierreferenz*.  

## <a name="rgerrors"></a> IErrorRecordsImpl:: M_rgerrors
Ein Array von fehlerdatensätzen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
CAtlArray< RecordClass > m_rgErrors;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)