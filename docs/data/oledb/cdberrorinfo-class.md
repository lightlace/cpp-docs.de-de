---
title: CDBErrorInfo-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDBErrorInfo
- ATL::CDBErrorInfo
- ATL.CDBErrorInfo
- ATL.CDBErrorInfo.GetAllErrorInfo
- CDBErrorInfo::GetAllErrorInfo
- ATL::CDBErrorInfo::GetAllErrorInfo
- GetAllErrorInfo
- CDBErrorInfo.GetAllErrorInfo
- CDBErrorInfo::GetBasicErrorInfo
- ATL.CDBErrorInfo.GetBasicErrorInfo
- CDBErrorInfo.GetBasicErrorInfo
- ATL::CDBErrorInfo::GetBasicErrorInfo
- GetBasicErrorInfo
- CDBErrorInfo::GetCustomErrorObject
- ATL.CDBErrorInfo.GetCustomErrorObject
- CDBErrorInfo.GetCustomErrorObject
- ATL::CDBErrorInfo::GetCustomErrorObject
- GetCustomErrorObject
- GetErrorInfo
- ATL.CDBErrorInfo.GetErrorInfo
- CDBErrorInfo.GetErrorInfo
- ATL::CDBErrorInfo::GetErrorInfo
- CDBErrorInfo::GetErrorInfo
- ATL.CDBErrorInfo.GetErrorParameters
- CDBErrorInfo::GetErrorParameters
- ATL::CDBErrorInfo::GetErrorParameters
- CDBErrorInfo.GetErrorParameters
- GetErrorParameters
- CDBErrorInfo.GetErrorRecords
- ATL.CDBErrorInfo.GetErrorRecords
- ATL::CDBErrorInfo::GetErrorRecords
- GetErrorRecords
- CDBErrorInfo::GetErrorRecords
dev_langs:
- C++
helpviewer_keywords:
- CDBErrorInfo class
- GetAllErrorInfo method
- GetBasicErrorInfo method
- GetCustomErrorObject method
- GetErrorInfo method
- GetErrorParameters method
- GetErrorRecords method
ms.assetid: 9a5c18a2-ee3e-40f5-ab4c-581288d7f737
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0a219024c56bd1b976682c7262d84ce26bce0930
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2018
ms.locfileid: "39208610"
---
# <a name="cdberrorinfo-class"></a>CDBErrorInfo-Klasse
Bietet Unterstützung für OLE DB-fehlerverarbeitung mit dem OLE DB [IErrorRecords](https://msdn.microsoft.com/library/ms718112.aspx) Schnittstelle.  
  
## <a name="syntax"></a>Syntax

```cpp
class CDBErrorInfo  
``` 

## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h 
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[GetAllErrorInfo](#getallerrorinfo)|Gibt alle Fehlerinformationen, die innerhalb eines fehlerdatensatzes.|  
|[GetBasicErrorInfo](#getbasicerrorinfo)|Aufrufe [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/library/ms723907.aspx) grundlegende Informationen zu dem angegebenen Fehler zurückgegeben werden sollen.|  
|[GetCustomErrorObject](#getcustomerrorobject)|Aufrufe [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/library/ms725417.aspx) um einen Zeiger auf eine Schnittstelle für ein Objekt für die benutzerdefinierten Fehler zurückzugeben.|  
|[GetErrorInfo](#geterrorinfo)|Aufrufe [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/library/ms711230.aspx) zurückzugebenden ein `IErrorInfo` Schnittstellenzeiger auf den angegebenen Datensatz.|  
|[GetErrorParameters](#geterrorparameters)|Aufrufe [IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/library/ms715793.aspx) die Fehlerparameter zurückgegeben.|  
|[GetErrorRecords](#geterrorrecords)|Ruft die Error-Datensätze für das angegebene Objekt ab.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle gibt einen oder mehrere Error-Datensätze für den Benutzer zurück. Rufen Sie [cdberrorinfo:: Geterrorrecords](../../data/oledb/cdberrorinfo-geterrorrecords.md) zuerst, damit die Anzahl der Fehlerdatensätze zu erhalten. Dann eine der der Zugriff Funktionen, z. B. [cdberrorinfo:: Getallerrorinfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md), um Fehlerinformationen für jeden Datensatz abzurufen.  
  
## <a name="getallerrorinfo"></a> Cdberrorinfo:: Getallerrorinfo
Gibt alle Typen von Fehlerinformationen enthalten, die in einen Fehlerdatensatz zurück.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetAllErrorInfo(ULONG ulRecordNum,  
   LCID lcid,  BSTR* pbstrDescription,  
   BSTR* pbstrSource = NULL,  
   GUID* pguid = NULL,  
   DWORD* pdwHelpContext = NULL,  
   BSTR* pbstrHelpFile = NULL) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 *ulRecordNum*  
 [in] Die nullbasierte Nummer des Datensatzes für die Fehlerinformationen zurückgegeben werden sollen.  
  
 *lcid*  
 [in] Die Gebietsschema-ID für die Fehlerinformationen zurückgegeben werden.  
  
 *pbstrDescription*  
 [out] Ein Zeiger auf eine textbeschreibung des Fehlers oder NULL, wenn das Gebietsschema nicht unterstützt wird. Siehe Hinweise.  
  
 *pbstrSource*  
 [out] Ein Zeiger auf eine Zeichenfolge, die mit dem Namen der Komponente, die den Fehler generiert hat.  
  
 *pguid*  
 [out] Ein Zeiger auf die GUID der Schnittstelle, die den Fehler definiert.  
  
 *pdwHelpContext*  
 [out] Ein Zeiger auf die Hilfekontext-ID für den Fehler.  
  
 *pbstrHelpFile*  
 [out] Ein Zeiger auf eine Zeichenfolge, die mit dem Pfad zur Hilfedatei, die den Fehler beschreibt.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich. Finden Sie unter [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/library/ms711230.aspx) in die *OLE DB-Programmierreferenz* für andere Werte zurückgeben.  
  
### <a name="remarks"></a>Hinweise  
 Der Ausgabewert des *PbstrDescription* wird intern durch den Aufruf abgerufen `IErrorInfo::GetDescription`, wodurch den Wert auf NULL festgelegt, wenn das Gebietsschema nicht unterstützt wird, oder wenn beide der folgenden Bedingungen zutreffen:  
  
1.  der Wert des *Lcid* ist nicht-US Englisch und  
  
2.  der Wert des *Lcid* ist nicht gleich dem Wert, der von GetUserDefaultLCID zurückgegeben. 

## <a name="getbasicerrorinfo"></a> Cdberrorinfo:: Getbasicerrorinfo
Aufrufe [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/library/ms723907.aspx) grundlegende Informationen über den Fehler, z. B. den Rückgabecode und die Anzahl der Anbieter-spezifischer Fehler zurückgegeben werden sollen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetBasicErrorInfo(ULONG ulRecordNum,   
  ERRORINFO* pErrorInfo) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/library/ms723907.aspx) in die *OLE DB-Programmierreferenz*.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard-HRESULT.  

## <a name="getcustomerrorobject"></a> Cdberrorinfo:: Getcustomerrorobject
Aufrufe [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/library/ms725417.aspx) um einen Zeiger auf eine Schnittstelle für ein Objekt für die benutzerdefinierten Fehler zurückzugeben.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetCustomErrorObject(ULONG ulRecordNum,   
   REFIID riid,IUnknown** ppObject) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/library/ms725417.aspx) in die *OLE DB-Programmierreferenz*.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard-HRESULT.  

## <a name="geterrorinfo"></a> Cdberrorinfo:: GetErrorInfo
Aufrufe [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/library/ms711230.aspx) zurückzugebenden ein [IErrorInfo](https://msdn.microsoft.com/library/ms718112.aspx) Schnittstellenzeiger auf den angegebenen Datensatz.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetErrorInfo(ULONG ulRecordNum,   
   LCID lcid,IErrorInfo** ppErrorInfo) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/library/ms711230.aspx) in die *OLE DB-Programmierreferenz*.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard-HRESULT.  

## <a name="geterrorparameters"></a> Cdberrorinfo:: Geterrorparameters
Aufrufe [IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/library/ms715793.aspx) die Fehlerparameter zurückgegeben.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetErrorParameters(ULONG ulRecordNum,   
  DISPPARAMS* pdispparams) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/library/ms715793.aspx) in die *OLE DB-Programmierreferenz*.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard-HRESULT.  

## <a name="geterrorrecords"></a> Cdberrorinfo:: Geterrorrecords
Ruft die Error-Datensätze für das angegebene Objekt ab.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetErrorRecords(IUnknown* pUnk,   
   const IID& iid,   
   ULONG* pcRecords) throw();  


HRESULT GetErrorRecords(ULONG* pcRecords) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 *pUnk*  
 [in] Eine Schnittstelle für das Objekt für die Error-Datensätze abgerufen.  
  
 *IID*  
 [in] Die IID der Schnittstelle mit dem Fehler verknüpft ist.  
  
 *pcRecords*  
 [out] Ein Zeiger auf die (1-basiert) Anzahl von Datensätzen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard-HRESULT.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie die erste Form der Funktion, wenn Sie die Schnittstelle zum Abrufen der Fehlerinformationen von überprüfen möchten. Verwenden Sie andernfalls die zweite Form.  
  
## <a name="see-also"></a>Siehe auch  
 [DBViewer](../../visual-cpp-samples.md)   
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)