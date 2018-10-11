---
title: CDynamicParameterAccessor-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 02/14/2018
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CDynamicParameterAccessor
- ATL::CDynamicParameterAccessor
- CDynamicParameterAccessor
- CDynamicParameterAccessor::CDynamicParameterAccessor
- CDynamicParameterAccessor.CDynamicParameterAccessor
- CDynamicParameterAccessor::GetParam
- ATL.CDynamicParameterAccessor.GetParam
- CDynamicParameterAccessor::GetParam<ctype>
- CDynamicParameterAccessor.GetParam
- GetParam
- ATL::CDynamicParameterAccessor::GetParam<ctype>
- ATL::CDynamicParameterAccessor::GetParam
- ATL::CDynamicParameterAccessor::GetParamCount
- CDynamicParameterAccessor::GetParamCount
- CDynamicParameterAccessor.GetParamCount
- GetParamCount
- ATL.CDynamicParameterAccessor.GetParamCount
- GetParamIO
- CDynamicParameterAccessor::GetParamIO
- ATL.CDynamicParameterAccessor.GetParamIO
- CDynamicParameterAccessor.GetParamIO
- ATL::CDynamicParameterAccessor::GetParamIO
- ATL::CDynamicParameterAccessor::GetParamLength
- ATL.CDynamicParameterAccessor.GetParamLength
- CDynamicParameterAccessor.GetParamLength
- CDynamicParameterAccessor::GetParamLength
- GetParamLength
- CDynamicParameterAccessor::GetParamName
- ATL.CDynamicParameterAccessor.GetParamName
- GetParamName
- CDynamicParameterAccessor.GetParamName
- ATL::CDynamicParameterAccessor::GetParamName
- CDynamicParameterAccessor::GetParamStatus
- CDynamicParameterAccessor.GetParamStatus
- ATL.CDynamicParameterAccessor.GetParamStatus
- ATL::CDynamicParameterAccessor::GetParamStatus
- GetParamStatus
- CDynamicParameterAccessor.GetParamString
- GetParamString
- CDynamicParameterAccessor::GetParamString
- ATL.CDynamicParameterAccessor.GetParamString
- ATL::CDynamicParameterAccessor::GetParamString
- CDynamicParameterAccessor.GetParamType
- CDynamicParameterAccessor:GetParamType
- CDynamicParameterAccessor::GetParamType
- ATL.CDynamicParameterAccessor.GetParamType
- GetParamType
- ATL::CDynamicParameterAccessor::GetParamType
- ATL::CDynamicParameterAccessor::SetParam
- ATL::CDynamicParameterAccessor::SetParam<ctype>
- CDynamicParameterAccessor.SetParam
- ATL.CDynamicParameterAccessor.SetParam
- SetParam
- CDynamicParameterAccessor:SetParam
- CDynamicParameterAccessor::SetParam<ctype>
- CDynamicParameterAccessor::SetParam
- ATL::CDynamicParameterAccessor::SetParamLength
- CDynamicParameterAccessor.SetParamLength
- ATL.CDynamicParameterAccessor.SetParamLength
- CDynamicParameterAccessor::SetParamLength
- SetParamLength
- CDynamicParameterAccessor::SetParamStatus
- ATL.CDynamicParameterAccessor.SetParamStatus
- ATL::CDynamicParameterAccessor::SetParamStatus
- CDynamicParameterAccessor.SetParamStatus
- SetParamStatus
- ATL.CDynamicParameterAccessor.SetParamString
- ATL::CDynamicParameterAccessor::SetParamString
- SetParamString
- CDynamicParameterAccessor::SetParamString
- CDynamicParameterAccessor.SetParamString
dev_langs:
- C++
helpviewer_keywords:
- CDynamicParameterAccessor class
- CDynamicParameterAccessor class, constructor
- CDynamicParameterAccessor method
- GetParam method
- GetParamCount method
- GetParamIO method
- GetParamLength method
- GetParamName method
- GetParamStatus method
- GetParamString method
- GetParamType method
- SetParam method
- SetParamLength method
- SetParamStatus method
- SetParamString method
ms.assetid: 5f22626e-e80d-491f-8b3b-cedc50331960
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d0db07c8419db53d30612e6edbbe134634e37a74
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49083943"
---
# <a name="cdynamicparameteraccessor-class"></a>CDynamicParameterAccessor-Klasse

Ähnlich wie [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) , ruft festzulegende Parameterinformationen aber durch Aufrufen der [ICommandWithParameters](/sql/relational-databases/native-client-ole-db-interfaces/icommandwithparameters) -Schnittstelle ab.

## <a name="syntax"></a>Syntax

```cpp
class CDynamicParameterAccessor : public CDynamicAccessor
```

## <a name="requirements"></a>Anforderungen

**Header**: atldbcli.h

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[CDynamicParameterAccessor](#cdynamicparameteraccessor)|Der Konstruktor.|
|[GetParam](#getparam)|Ruft die Parameterdaten aus dem Puffer ab.|
|[GetParamCount](#getparamcount)|Ruft die Anzahl von Parametern im Accessor ab.|
|[GetParamIO](#getparamio)|Ermittelt, ob der angegebene Parameter ein Eingabe- oder ein Ausgabeparameter ist.|
|[GetParamLength](#getparamlength)|Ruft die Länge des angegebenen Parameters ab, der im Puffer gespeichert ist.|
|[GetParamName](#getparamname)|Ruft den Namen eines angegebenen Parameters ab.|
|[GetParamStatus](#getparamstatus)|Ruft den Status des angegebenen Parameters ab, der im Puffer gespeichert ist.|
|[GetParamString](#getparamstring)|Ruft die Zeichenfolgendaten Status des angegebenen Parameters ab, der im Puffer gespeichert ist.|
|[GetParamType](#getparamtype)|Ruft den Datentyp eines angegebenen Parameters ab.|
|[SetParam](#setparam)|Verwendet die Parameterdaten, um den Puffer festzulegen.|
|[SetParamLength](#setparamlength)|Legt die Länge des angegebenen Parameters fest, der im Puffer gespeichert ist.|
|[SetParamStatus](#setparamstatus)|Legt den Status des angegebenen Parameters fest, der im Puffer gespeichert ist.|
|[SetParamString](#setparamstring)|Legt die Zeichenfolgendaten des angegebenen Parameters fest, der im Puffer gespeichert ist.|

## <a name="remarks"></a>Hinweise

Der Anbieter muss `ICommandWithParameters` unterstützen, damit der Consumer diese Klasse verwenden kann.

Die Parameterinformationen werden in einem Puffer gespeichert, der von dieser Klasse erstellt und verwaltet wird. Sie rufen Parameterdaten aus dem Puffer ab, indem Sie [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) und [GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md)verwenden.

Ein Beispiel veranschaulicht, wie diese Klasse zum Ausführen einer gespeicherten SQL Server-Prozedur und die Ausgabeparameterwerte zu erhalten, finden Sie die [-Beispiel](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer) Beispielcode in die [Microsoft VCSamples](https://github.com/Microsoft/VCSamples) GitHub-Repository.

## <a name="cdynamicparameteraccessor"></a> CDynamicParameterAccessor:: CDynamicParameterAccessor

Der Konstruktor.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
typedef CDynamicParameterAccessor _ParamClass;  
CDynamicParameterAccessor(DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,   
   DBLENGTH nBlobSize = 8000 )   
   : CDynamicAccessor(eBlobHandling, nBlobSize )  
```  
  
#### <a name="parameters"></a>Parameter  

*eBlobHandling*<br/>
Gibt an, wie die BLOB-Daten behandelt werden. Der Standardwert ist DBBLOBHANDLING_DEFAULT. Finden Sie unter [CDynamicAccessor:: Setblobhandling](../../data/oledb/cdynamicaccessor-setblobhandling.md) eine Beschreibung der DBBLOBHANDLINGENUM Werte.  
  
*nBlobSize*<br/>
Die maximale BLOB-Größe in Byte; Spaltendaten über diesen Wert werden als BLOB behandelt. Der Standardwert ist 8000. Finden Sie unter [CDynamicAccessor:: Setblobsizelimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md) Details.  
  
### <a name="remarks"></a>Hinweise  

Finden Sie unter den [CDynamicAccessor:: CDynamicAccessor](../../data/oledb/cdynamicaccessor-cdynamicaccessor.md) Konstruktor für Weitere Informationen zum BLOB behandeln. 

## <a name="getparam"></a> CDynamicParameterAccessor:: GetParam

Ruft die Zeichenfolgendaten nicht für einen angegebenen Parameter aus dem Parameterpuffer ab.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
template <class ctype>bool GetParam(DBORDINAL nParam,   
   ctype* pData) const throw();  

template <class ctype> bool GetParam(TCHAR* pParamName,   
   ctype* pData) const throw();  

void* GetParam(DBORDINAL nParam) const throw();  

void* GetParam(TCHAR* pParamName) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  

*ctype*<br/>
Ein auf Vorlagen basierenden Parameter, der den Datentyp darstellt.  
  
*nParam*<br/>
[in] Die Anzahl der Parameter (Offset von 1). Parameter 0 ist für Rückgabewerte reserviert. Die Anzahl der Parameter ist der Index des Parameters, die basierend auf der Reihenfolge, in der SQL oder der Aufruf der gespeicherten Prozedur. Finden Sie unter [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) verdeutlicht.  
  
*pParamName*<br/>
[in] Der Name des Parameters.  
  
*pData*<br/>
[out] Der Zeiger auf den Arbeitsspeicher mit den Daten aus dem Puffer abgerufen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  

Auf Vorlagen basierende Versionen verweist auf den Arbeitsspeicher mit den Daten aus dem Puffer abgerufen. Gibt zurück, auf Vorlagen basierende Versionen **"true"** bei Erfolg oder **"false"** bei einem Fehler.  
  
Verwendung `GetParam` keine Zeichenfolge darstellen Parameterdaten aus dem Puffer abgerufen. Verwendung [GetParamString](../../data/oledb/cdynamicparameteraccessor-getparamstring.md) zum Abrufen von Daten für Zeichenfolge-Parameter aus dem Puffer.  

## <a name="getparamcount"></a> CDynamicParameterAccessor:: Getparamcount

Ruft die Anzahl von Parametern, die im Puffer gespeichert.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
DB_UPARAMS GetParamCount() const throw();  
```  
  
### <a name="return-value"></a>Rückgabewert  

Die Anzahl der Parameter.  

## <a name="getparamio"></a> CDynamicParameterAccessor:: Getparamio

Ermittelt, ob der angegebene Parameter ein Eingabe- oder ein Ausgabeparameter ist.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
bool GetParamIO(DBORDINAL nParam,   
   DBPARAMIO* pParamIO) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  

*nParam*<br/>
[in] Die Anzahl der Parameter (Offset von 1). Parameter 0 ist für Rückgabewerte reserviert. Die Anzahl der Parameter ist der Index des Parameters, die basierend auf der Reihenfolge, in der SQL oder der Aufruf der gespeicherten Prozedur. Finden Sie unter [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) verdeutlicht.  
  
*pParamIO*<br/>
Ein Zeiger auf die Variable mit dem `DBPARAMIO` Typ (Eingabe oder Ausgabe) des angegebenen Parameters. Es ist wie folgt definiert:  
  
```cpp  
typedef DWORD DBPARAMIO;  
  
enum DBPARAMIOENUM {  
    DBPARAMIO_NOTPARAM   = 0,  
    DBPARAMIO_INPUT      = 0x1,  
    DBPARAMIO_OUTPUT     = 0x2  
};  
```  
  
### <a name="return-value"></a>Rückgabewert  

Gibt **"true"** bei Erfolg oder **"false"** bei einem Fehler.  

## <a name="getparamlength"></a> CDynamicParameterAccessor:: Getparamlength

Ruft die Länge des angegebenen Parameters ab, der im Puffer gespeichert ist.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
bool GetParamLength(DBORDINAL nParam,  
   DBLENGTH* pLength);  

DBLENGTH* GetParamLength(DBORDINAL nParam) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  

*nParam*<br/>
[in] Die Anzahl der Parameter (Offset von 1). Parameter 0 ist für Rückgabewerte reserviert. Die Anzahl der Parameter ist der Index des Parameters, die basierend auf der Reihenfolge, in der SQL oder der Aufruf der gespeicherten Prozedur. Finden Sie unter [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) verdeutlicht.  
  
*pLength*<br/>
[out] Ein Zeiger auf die Variable, die die Länge in Bytes, des angegebenen Parameters enthält.  
  
### <a name="remarks"></a>Hinweise  

Die erste, außer Kraft setzen gibt **"true"** bei Erfolg oder **"false"** bei einem Fehler. Das zweite Überschreiben verweist auf den Arbeitsspeicher, die die Länge des Parameters enthält. 

## <a name="getparamname"></a> CDynamicParameterAccessor:: Getparamname

Ruft den Namen des angegebenen Parameters ab.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
LPOLESTR GetParamName(DBORDINAL nParam) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  

*nParam*<br/>
[in] Die Anzahl der Parameter (Offset von 1). Parameter 0 ist für Rückgabewerte reserviert. Die Anzahl der Parameter ist der Index des Parameters, die basierend auf der Reihenfolge, in der SQL oder der Aufruf der gespeicherten Prozedur. Finden Sie unter [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) verdeutlicht.  
  
### <a name="return-value"></a>Rückgabewert  

Der Name des angegebenen Parameters.  

## <a name="getparamstatus"></a> CDynamicParameterAccessor:: Getparamstatus

Ruft den Status des angegebenen Parameters ab, der im Puffer gespeichert ist.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
bool GetParamStatus(DBORDINAL nParam,  
   DBSTATUS* pStatus);  

DBSTATUS* GetParamStatus(DBORDINAL nParam) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  

*nParam*<br/>
[in] Die Anzahl der Parameter (Offset von 1). Parameter 0 ist für Rückgabewerte reserviert. Die Anzahl der Parameter ist der Index des Parameters, die basierend auf der Reihenfolge, in der SQL oder der Aufruf der gespeicherten Prozedur. Finden Sie unter [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) verdeutlicht.  
  
*pStatus*<br/>
[out] Ein Zeiger auf die Variable mit dem DBSTATUS Status des angegebenen Parameters. Informationen zu DBSTATUS Werten finden Sie unter [Status](/previous-versions/windows/desktop/ms722617) in die *OLE DB-Programmierreferenz*, oder suchen Sie nach DBSTATUS in der Datei oledb.h.  
  
### <a name="remarks"></a>Hinweise  

Die erste, außer Kraft setzen gibt **"true"** bei Erfolg oder **"false"** bei einem Fehler. Das zweite Überschreiben verweist auf den Arbeitsspeicher, der den Status des angegebenen Parameters enthält.

## <a name="getparamstring"></a> CDynamicParameterAccessor:: Getparamstring

Ruft die Zeichenfolgendaten Status des angegebenen Parameters ab, der im Puffer gespeichert ist.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
bool GetParamString(DBORDINAL nParam,  
   CSimpleStringA& strOutput) throw();

bool GetParamString(DBORDINAL nParam,  
   CSimpleStringW& strOutput) throw();
   
bool GetParamString(DBORDINAL nParam,  
   CHAR* pBuffer,  
   size_t* pMaxLen) throw();

bool GetParamString(DBORDINAL nParam,  
   WCHAR* pBuffer,  
   size_t* pMaxLen) throw();  
```  
  
#### <a name="parameters"></a>Parameter  

*nParam*<br/>
[in] Die Anzahl der Parameter (Offset von 1). Parameter 0 ist für Rückgabewerte reserviert. Die Anzahl der Parameter ist der Index des Parameters, die basierend auf der Reihenfolge, in der SQL oder der Aufruf der gespeicherten Prozedur. Finden Sie unter [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) verdeutlicht.  
  
*strOutput*<br/>
[out] Die ANSI (`CSimpleStringA`) oder Unicode (`CSimpleStringW`) Zeichenfolgendaten des angegebenen Parameters. Übergeben Sie einen Parameter vom Typ `CString`, z.B.:  
  
[!code-cpp[NVC_OLEDB_Consumer#9](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-getparamstring_1.cpp)]  
  
*pBuffer*<br/>
[out] Ein Zeiger auf die ANSI (**CHAR**) oder Unicode (**WCHAR**) Zeichenfolgendaten des angegebenen Parameters.  
  
*pMaxLen*<br/>
[out] Ein Zeiger auf die Größe des Puffers verweist *pBuffer* (in Zeichen, einschließlich das abschließende NULLZEICHEN).  
  
### <a name="remarks"></a>Hinweise  

Gibt **"true"** bei Erfolg oder **"false"** bei einem Fehler.  
  
Wenn *pBuffer* NULL ist, diese Methode wird die erforderliche Puffergröße festgelegt, im Speicher verweist *pMaxLen* und zurückgeben **"true"** ohne die Daten zu kopieren.  
  
Diese Methode schlägt fehl, wenn der Puffer *pBuffer* ist nicht groß genug, um die gesamte Zeichenfolge enthalten.  
  
Verwendung `GetParamString` zum Abrufen von Daten für Zeichenfolge-Parameter aus dem Puffer. Verwendung [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) keine Zeichenfolge darstellen Parameterdaten aus dem Puffer abgerufen.  

## <a name="getparamtype"></a> CDynamicParameterAccessor:: GetParamType

Ruft den Datentyp eines angegebenen Parameters ab.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
bool GetParamType(DBORDINAL nParam,  
   DBTYPE* pType) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  

*nParam*<br/>
[in] Die Anzahl der Parameter (Offset von 1). Parameter 0 ist für Rückgabewerte reserviert. Die Anzahl der Parameter ist der Index des Parameters, die basierend auf der Reihenfolge, in der SQL oder der Aufruf der gespeicherten Prozedur. Finden Sie unter [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) verdeutlicht.  
  
*PGeben*<br/>
[out] Ein Zeiger auf die Variable, die den Datentyp des angegebenen Parameters enthält.  
  
### <a name="return-value"></a>Rückgabewert  

Gibt **"true"** bei Erfolg oder **"false"** bei einem Fehler.  

## <a name="setparam"></a> CDynamicParameterAccessor:: SetParam

Legt fest, der Parameterpuffer anhand der angegebenen (nicht-Zeichenfolge) Daten.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
template <class ctype>
bool SetParam(DBORDINAL nParam,  
   constctype* pData,  
   DBSTATUS status = DBSTATUS_S_OK) throw();  

template <class ctype>  
bool SetParam(TCHAR* pParamName,  
   const ctype* pData,  
   DBSTATUS status = DBSTATUS_S_OK) throw();  
```  
  
#### <a name="parameters"></a>Parameter  

*ctype*<br/>
Ein auf Vorlagen basierenden Parameter, der den Datentyp darstellt.  
  
*nParam*<br/>
[in] Die Anzahl der Parameter (Offset von 1). Parameter 0 ist für Rückgabewerte reserviert. Die Anzahl der Parameter ist der Index des Parameters, die basierend auf der Reihenfolge, in der SQL oder der Aufruf der gespeicherten Prozedur. Zum Beispiel:  
  
[!code-cpp[NVC_OLEDB_Consumer#8](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-setparam_1.cpp)]  
  
*pParamName*<br/>
[in] Der Name des Parameters.  
  
*pData*<br/>
[in] Der Zeiger auf den Arbeitsspeicher mit den Daten in den Puffer geschrieben werden sollen.  
  
*Status*<br/>
[in] Folgender Spaltenstatus DBSTATUS. Informationen zu DBSTATUS Werten finden Sie unter [Status](/previous-versions/windows/desktop/ms722617) in die *OLE DB-Programmierreferenz*, oder suchen Sie nach DBSTATUS in der Datei oledb.h.  
  
### <a name="return-value"></a>Rückgabewert  

Gibt **"true"** bei Erfolg oder **"false"** bei einem Fehler.  
  
Verwendung `SetParam` Zeichenfolgendaten nicht Parameter im Puffer festgelegt. Verwendung [SetParamString](../../data/oledb/cdynamicparameteraccessor-setparamstring.md) Parameterdaten Zeichenfolge im Puffer festgelegt.  

## <a name="setparamlength"></a> CDynamicParameterAccessor:: Setparamlength

Legt die Länge des angegebenen Parameters fest, der im Puffer gespeichert ist.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
bool SetParamLength(DBORDINAL nParam,  
   DBLENGTH length);  
```  
  
#### <a name="parameters"></a>Parameter  

*nParam*<br/>
[in] Die Anzahl der Parameter (Offset von 1). Parameter 0 ist für Rückgabewerte reserviert. Die Anzahl der Parameter ist der Index des Parameters, die basierend auf der Reihenfolge, in der SQL oder der Aufruf der gespeicherten Prozedur. Finden Sie unter [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) verdeutlicht.  
  
*length*<br/>
[in] Die Länge in Bytes des angegebenen Parameters.  
  
### <a name="remarks"></a>Hinweise  

Gibt **"true"** bei Erfolg oder **"false"** bei einem Fehler. 

## <a name="setparamstatus"></a> CDynamicParameterAccessor:: Setparamstatus

Legt den Status des angegebenen Parameters fest, der im Puffer gespeichert ist.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
bool SetParamStatus(DBORDINAL nParam,  
   DBSTATUS status);  
```  
  
#### <a name="parameters"></a>Parameter  

*nParam*<br/>
[in] Die Anzahl der Parameter (Offset von 1). Parameter 0 ist für Rückgabewerte reserviert. Die Anzahl der Parameter ist der Index des Parameters, die basierend auf der Reihenfolge, in der SQL oder der Aufruf der gespeicherten Prozedur. Finden Sie unter [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) verdeutlicht.  
  
*Status*<br/>
[in] Der DBSTATUS Status des angegebenen Parameters. Informationen zu DBSTATUS Werten finden Sie unter [Status](/previous-versions/windows/desktop/ms722617) in die *OLE DB-Programmierreferenz*, oder suchen Sie nach DBSTATUS in der Datei oledb.h.  
  
### <a name="remarks"></a>Hinweise  

Gibt **"true"** bei Erfolg oder **"false"** bei einem Fehler. 

## <a name="setparamstring"></a> CDynamicParameterAccessor:: Setparamstring

Legt die Zeichenfolgendaten des angegebenen Parameters fest, der im Puffer gespeichert ist.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
bool SetParamString(DBORDINAL nParam,   
   constCHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK) throw();bool SetParamString(DBORDINAL nParam,   
   constWCHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK) throw();  
```  
  
#### <a name="parameters"></a>Parameter  

*nParam*<br/>
[in] Die Anzahl der Parameter (Offset von 1). Parameter 0 ist für Rückgabewerte reserviert. Die Anzahl der Parameter ist der Index des Parameters, die basierend auf der Reihenfolge, in der SQL oder der Aufruf der gespeicherten Prozedur. Finden Sie unter [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) verdeutlicht.  
  
*pString*<br/>
[in] Ein Zeiger auf die ANSI (**CHAR**) oder Unicode (**WCHAR**) Zeichenfolgendaten des angegebenen Parameters. Sehen Sie in der Datei oledb.h DBSTATUS.  
  
*Status*<br/>
[in] Der DBSTATUS Status des angegebenen Parameters. Informationen zu DBSTATUS Werten finden Sie unter [Status](/previous-versions/windows/desktop/ms722617) in die *OLE DB-Programmierreferenz*, oder suchen Sie nach DBSTATUS in der Datei oledb.h.  
  
### <a name="remarks"></a>Hinweise  

Gibt **"true"** bei Erfolg oder **"false"** bei einem Fehler.  
  
`SetParamString` schlägt fehl, wenn Sie versuchen, eine Zeichenfolge festzulegen, die größer als die maximale Größe für angegebene *pString*.  
  
Verwendung `SetParamString` Parameterdaten Zeichenfolge im Puffer festgelegt. Verwendung [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) Zeichenfolgendaten nicht Parameter im Puffer festgelegt. 

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor-Klasse](../../data/oledb/caccessor-class.md)<br/>
[CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CManualAccessor-Klasse](../../data/oledb/cmanualaccessor-class.md)  