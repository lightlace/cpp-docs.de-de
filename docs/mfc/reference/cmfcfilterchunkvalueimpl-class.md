---
title: Klasse CMFCFilterChunkValueImpl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl::Clear
- AFXWIN/CMFCFilterChunkValueImpl::CopyChunk
- AFXWIN/CMFCFilterChunkValueImpl::CopyFrom
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkGUID
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkPID
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkType
- AFXWIN/CMFCFilterChunkValueImpl::GetString
- AFXWIN/CMFCFilterChunkValueImpl::GetValue
- AFXWIN/CMFCFilterChunkValueImpl::GetValueNoAlloc
- AFXWIN/CMFCFilterChunkValueImpl::IsValid
- AFXWIN/CMFCFilterChunkValueImpl::SetBoolValue
- AFXWIN/CMFCFilterChunkValueImpl::SetDwordValue
- AFXWIN/CMFCFilterChunkValueImpl::SetFileTimeValue
- AFXWIN/CMFCFilterChunkValueImpl::SetInt64Value
- AFXWIN/CMFCFilterChunkValueImpl::SetIntValue
- AFXWIN/CMFCFilterChunkValueImpl::SetLongValue
- AFXWIN/CMFCFilterChunkValueImpl::SetSystemTimeValue
- AFXWIN/CMFCFilterChunkValueImpl::SetTextValue
- AFXWIN/CMFCFilterChunkValueImpl::SetChunk
dev_langs:
- C++
helpviewer_keywords:
- CMFCFilterChunkValueImpl class
ms.assetid: 3c833f23-5b88-4d08-9e09-ca6a8aec88bf
caps.latest.revision: 25
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 8de3cba19a60b8022df96a9edafd13677fa3fecb
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcfilterchunkvalueimpl-class"></a>CMFCFilterChunkValueImpl-Klasse
Dies ist eine Klasse, die Segment und Eigenschaft-Wert-Paar-Logik vereinfacht.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCFilterChunkValueImpl : public ATL::IFilterChunkValue;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl:: ~ CMFCFilterChunkValueImpl](#_dtorcmfcfilterchunkvalueimpl)|Destructs des Objekts.|  
|[CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl](#cmfcfilterchunkvalueimpl)|Erstellt das Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl::Clear](#clear)|Löscht die ChunkValue.|  
|[CMFCFilterChunkValueImpl::CopyChunk](#copychunk)|Dieses Segment kopiert in eine Struktur, beschreibt die Merkmale eines.|  
|[CMFCFilterChunkValueImpl::CopyFrom](#copyfrom)|Dieser Block-Wert aus der andere Wert initialisiert.|  
|[CMFCFilterChunkValueImpl::GetChunkGUID](#getchunkguid)|Ruft das Segment GUID ab.|  
|[CMFCFilterChunkValueImpl::GetChunkPID](#getchunkpid)|Ruft das Segment PID (ID der Eigenschaft) ab.|  
|[CMFCFilterChunkValueImpl::GetChunkType](#getchunktype)|Ruft segmentiert Typ.|  
|[CMFCFilterChunkValueImpl::GetString](#getstring)|Ruft den String-Wert.|  
|[CMFCFilterChunkValueImpl::GetValue](#getvalue)|Ruft den Wert als einen zugeordneten Propvariant ab.|  
|[CMFCFilterChunkValueImpl::GetValueNoAlloc](#getvaluenoalloc)|Gibt nicht reserviert (interne Wert) den Wert.|  
|[CMFCFilterChunkValueImpl::IsValid](#isvalid)|Überprüft, ob der Wert dieser Eigenschaft gültig ist.|  
|[CMFCFilterChunkValueImpl::SetBoolValue](#setboolvalue)|Überladen. Legt die Eigenschaft durch Schlüssel in einen booleschen Wert fest.|  
|[CMFCFilterChunkValueImpl::SetDwordValue](#setdwordvalue)|Legt die Eigenschaft durch den Schlüssel für einen DWORD-Wert.|  
|[CMFCFilterChunkValueImpl::SetFileTimeValue](#setfiletimevalue)|Legt die Eigenschaft durch Schlüssel zu einer Filetime fest.|  
|[CMFCFilterChunkValueImpl::SetInt64Value](#setint64value)|Legt die Eigenschaft durch Schlüssel zu einem Int64-Typ.|  
|[CMFCFilterChunkValueImpl::SetIntValue](#setintvalue)|Legt die Eigenschaft durch Schlüssel in int|  
|[CMFCFilterChunkValueImpl::SetLongValue](#setlongvalue)|Legt die Eigenschaft durch-Taste, um einen Long-Wert.|  
|[CMFCFilterChunkValueImpl::SetSystemTimeValue](#setsystemtimevalue)|Legt die Eigenschaft durch den Schlüssel für die SystemTime.|  
|[CMFCFilterChunkValueImpl::SetTextValue](#settextvalue)|Legt die Eigenschaft durch Schlüssel in eine Unicode-Zeichenfolge.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl::SetChunk](#setchunk)|Eine Hilfsfunktion, mit der das Segment allgemeine Eigenschaften festgelegt.|  
  
## <a name="remarks"></a>Hinweise  
 Um zu verwenden, erstellen Sie einfach eine CMFCFilterChunkValueImpl-Klasse, von der richtigen  
  
 Beispiel:  
  
 Segment CMFCFilterChunkValueImpl;  
  
 HR = Block. SetBoolValue(PKEY_IsAttachment, true);  
  
 oder  
  
 HR = Block. SetFileTimeValue (PKEY_ItemDate, FtLastModified);  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ATL::IFilterChunkValue`  
  
 [CMFCFilterChunkValueImpl](../../mfc/reference/cmfcfilterchunkvalueimpl-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="clear"></a>CMFCFilterChunkValueImpl::Clear  
 Löscht die ChunkValue.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="cmfcfilterchunkvalueimpl"></a>CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl  
 Erstellt das Objekt.  
  
```  
CMFCFilterChunkValueImpl();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="_dtorcmfcfilterchunkvalueimpl"></a>CMFCFilterChunkValueImpl:: ~ CMFCFilterChunkValueImpl  
 Destructs des Objekts.  
  
```  
virtual ~CMFCFilterChunkValueImpl();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="copychunk"></a>CMFCFilterChunkValueImpl::CopyChunk  
 Dieses Segment kopiert in eine Struktur, beschreibt die Merkmale eines.  
  
```  
HRESULT CopyChunk(STAT_CHUNK* pStatChunk);
```  
  
### <a name="parameters"></a>Parameter  
 `pStatChunk`  
 Ein Zeiger auf den Zielwert beschreiben die Merkmale des Segments.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="copyfrom"></a>CMFCFilterChunkValueImpl::CopyFrom  
 Dieser Block-Wert aus der andere Wert initialisiert.  
  
```  
void CopyFrom (IFilterChunkValue* pValue);
```  
  
### <a name="parameters"></a>Parameter  
 `pValue`  
 Gibt den Quellwert zum Kopieren aus.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getchunkguid"></a>CMFCFilterChunkValueImpl::GetChunkGUID  
 Ruft das Segment GUID ab.  
  
```  
REFGUID GetChunkGUID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf eine GUID zur Kennzeichnung des Blocks.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getchunkpid"></a>CMFCFilterChunkValueImpl::GetChunkPID  
 Ruft das Segment PID (ID der Eigenschaft) ab.  
  
```  
DWORD GetChunkPID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein DWORD-Wert, der Eigenschaft-ID enthält.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getchunktype"></a>CMFCFilterChunkValueImpl::GetChunkType  
 Ruft den Segment-Typ ab.  
  
```  
CHUNKSTATE GetChunkType() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine CHUNKSTATE Enumerationswert, der angibt, ob der aktuelle Datenblock ein Text-Datentyp-Eigenschaft oder eine Eigenschaft Werttyp ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getstring"></a>CMFCFilterChunkValueImpl::GetString  
 Ruft den Zeichenfolgenwert ab.  
  
```  
CString &GetString();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge mit der Block-Wert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getvalue"></a>CMFCFilterChunkValueImpl::GetValue  
 Ruft den Wert als einen zugeordneten Propvariant ab.  
  
```  
HRESULT GetValue(PROPVARIANT** ppPropVariant);
```  
  
### <a name="parameters"></a>Parameter  
 `ppPropVariant`  
 Wenn die Funktion zurückgibt, enthält dieser Parameter den Segment-Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn PROPVARIANT erfolgreich zugewiesen wurde und der Segment-Wert erfolgreich, um kopiert wurde `ppPropVariant`; andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getvaluenoalloc"></a>CMFCFilterChunkValueImpl::GetValueNoAlloc  
 Gibt den Wert nicht reserviert (interne Wert).  
  
```  
PROPVARIANT GetValueNoAlloc ();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den aktuellen Wert des Blocks zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isvalid"></a>CMFCFilterChunkValueImpl::IsValid  
 Überprüft, ob der Wert dieser Eigenschaft gültig ist.  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der aktuelle Block-Wert gültig ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setboolvalue"></a>CMFCFilterChunkValueImpl::SetBoolValue  
 Überladen. Legt die Eigenschaft durch Schlüssel in einen booleschen Wert fest.  
  
```  
HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,  
    BOOL bVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);

 
HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,  
    VARIANT_BOOL bVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Parameter  
 `pkey`  
 Gibt einen Schlüssel an.  
  
 `bVal`  
 Gibt den Block-Wert festgelegt.  
  
 `chunkType`  
 Flags geben an, ob dieses Segment eine Text-Datentyp oder ein Werttyp-Eigenschaft enthält. Flagwerte stammen aus der CHUNKSTATE-Enumeration.  
  
 `locale`  
 Die Sprache und Teilsprache eines Teils der Text zugeordnet. Segment Gebietsschema wird von Indexern Dokument zum richtigen Wortumbruch des Texts nicht durchführen. Wenn das Segment weder ein Werttyp mit dem Datentyp VT_LPWSTR, VT_LPSTR oder VT_BSTR als auch Text-Datentyp ist, wird dieses Feld ignoriert.  
  
 `cwcLenSource`  
 Die Länge in Zeichen des Quelltexts aus dem aktuellen Abschnitt abgeleitet wurde. Der Wert&0; gibt an, Zeichen von Entsprechung zwischen den Quelltext und den abgeleiteten Text. Ein Wert ungleich NULL bedeutet, dass keine solchen direkte Entsprechung vorhanden ist.  
  
 `cwcStartSource`  
 Der Offset, von dem im Abschnitt Quelle der Quelltext für alle abgeleiteten gestartet wird.  
  
 `chunkBreakType`  
 Der Typ der Pause, die das vorherige Segment aus dem aktuellen Abschnitt trennt. Werte werden aus der CHUNK_BREAKTYPE-Enumeration.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setchunk"></a>CMFCFilterChunkValueImpl::SetChunk  
 Eine Hilfsfunktion, mit der das Segment allgemeine Eigenschaften festgelegt.  
  
```  
HRESULT SetChunk(
    REFPROPERTYKEY pkey,  
    CHUNKSTATE chunkType=CHUNK_VALUE,  
    LCID locale=0,  
    DWORD cwcLenSource=0,  
    DWORD cwcStartSource=0,  
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Parameter  
 `pkey`  
 Gibt einen Schlüssel an.  
  
 `chunkType`  
 Flags geben an, ob dieses Segment eine Text-Datentyp oder ein Werttyp-Eigenschaft enthält. Flagwerte stammen aus der CHUNKSTATE-Enumeration.  
  
 `locale`  
 Die Sprache und Teilsprache eines Teils der Text zugeordnet. Segment Gebietsschema wird von Indexern Dokument zum richtigen Wortumbruch des Texts nicht durchführen. Wenn das Segment weder ein Werttyp mit dem Datentyp VT_LPWSTR, VT_LPSTR oder VT_BSTR als auch Text-Datentyp ist, wird dieses Feld ignoriert.  
  
 `cwcLenSource`  
 Die Länge in Zeichen des Quelltexts aus dem aktuellen Abschnitt abgeleitet wurde. Der Wert&0; gibt an, Zeichen von Entsprechung zwischen den Quelltext und den abgeleiteten Text. Ein Wert ungleich NULL bedeutet, dass keine solchen direkte Entsprechung vorhanden ist.  
  
 `cwcStartSource`  
 Der Offset, von dem im Abschnitt Quelle der Quelltext für alle abgeleiteten gestartet wird.  
  
 `chunkBreakType`  
 Der Typ der Pause, die das vorherige Segment aus dem aktuellen Abschnitt trennt. Werte werden aus der CHUNK_BREAKTYPE-Enumeration.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setdwordvalue"></a>CMFCFilterChunkValueImpl::SetDwordValue  
 -Taste, um einen DWORD-Wert festlegen Sie die Eigenschaft.  
  
```  
HRESULT SetDwordValue(
    REFPROPERTYKEY pkey,  
    DWORD dwVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Parameter  
 `pkey`  
 Gibt einen Schlüssel an.  
  
 `dwVal`  
 Gibt den Block-Wert festgelegt.  
  
 `chunkType`  
 Flags geben an, ob dieses Segment eine Text-Datentyp oder ein Werttyp-Eigenschaft enthält. Flagwerte stammen aus der CHUNKSTATE-Enumeration.  
  
 `locale`  
 Die Sprache und Teilsprache eines Teils der Text zugeordnet. Segment Gebietsschema wird von Indexern Dokument zum richtigen Wortumbruch des Texts nicht durchführen. Wenn das Segment weder ein Werttyp mit dem Datentyp VT_LPWSTR, VT_LPSTR oder VT_BSTR als auch Text-Datentyp ist, wird dieses Feld ignoriert.  
  
 `cwcLenSource`  
 Die Länge in Zeichen des Quelltexts aus dem aktuellen Abschnitt abgeleitet wurde. Der Wert&0; gibt an, Zeichen von Entsprechung zwischen den Quelltext und den abgeleiteten Text. Ein Wert ungleich NULL bedeutet, dass keine solchen direkte Entsprechung vorhanden ist.  
  
 `cwcStartSource`  
 Der Offset, von dem im Abschnitt Quelle der Quelltext für alle abgeleiteten gestartet wird.  
  
 `chunkBreakType`  
 Der Typ der Pause, die das vorherige Segment aus dem aktuellen Abschnitt trennt. Werte werden aus der CHUNK_BREAKTYPE-Enumeration.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setfiletimevalue"></a>CMFCFilterChunkValueImpl::SetFileTimeValue  
 Legen Sie die Eigenschaft durch Schlüssel zu einer Filetime an.  
  
```  
HRESULT SetFileTimeValue(
    REFPROPERTYKEY pkey,  
    FILETIME dtVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Parameter  
 `pkey`  
 Gibt einen Schlüssel an.  
  
 `dtVal`  
 Gibt den Block-Wert festgelegt.  
  
 `chunkType`  
 Flags geben an, ob dieses Segment eine Text-Datentyp oder ein Werttyp-Eigenschaft enthält. Flagwerte stammen aus der CHUNKSTATE-Enumeration.  
  
 `locale`  
 Die Sprache und Teilsprache eines Teils der Text zugeordnet. Segment Gebietsschema wird von Indexern Dokument zum richtigen Wortumbruch des Texts nicht durchführen. Wenn das Segment weder ein Werttyp mit dem Datentyp VT_LPWSTR, VT_LPSTR oder VT_BSTR als auch Text-Datentyp ist, wird dieses Feld ignoriert.  
  
 `cwcLenSource`  
 Die Länge in Zeichen des Quelltexts aus dem aktuellen Abschnitt abgeleitet wurde. Der Wert&0; gibt an, Zeichen von Entsprechung zwischen den Quelltext und den abgeleiteten Text. Ein Wert ungleich NULL bedeutet, dass keine solchen direkte Entsprechung vorhanden ist.  
  
 `cwcStartSource`  
 Der Offset, von dem im Abschnitt Quelle der Quelltext für alle abgeleiteten gestartet wird.  
  
 `chunkBreakType`  
 Der Typ der Pause, die das vorherige Segment aus dem aktuellen Abschnitt trennt. Werte werden aus der CHUNK_BREAKTYPE-Enumeration.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setint64value"></a>CMFCFilterChunkValueImpl::SetInt64Value  
 Legen Sie die Eigenschaft durch Schlüssel zu einem Int64-Typ.  
  
```  
HRESULT SetInt64Value(
    REFPROPERTYKEY pkey,  
    __int64 nVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Parameter  
 `pkey`  
 Gibt einen Schlüssel an.  
  
 `nVal`  
 Gibt den Block-Wert festgelegt.  
  
 `chunkType`  
 Flags geben an, ob dieses Segment eine Text-Datentyp oder ein Werttyp-Eigenschaft enthält. Flagwerte stammen aus der CHUNKSTATE-Enumeration.  
  
 `locale`  
 Die Sprache und Teilsprache eines Teils der Text zugeordnet. Segment Gebietsschema wird von Indexern Dokument zum richtigen Wortumbruch des Texts nicht durchführen. Wenn das Segment weder ein Werttyp mit dem Datentyp VT_LPWSTR, VT_LPSTR oder VT_BSTR als auch Text-Datentyp ist, wird dieses Feld ignoriert.  
  
 `cwcLenSource`  
 Die Länge in Zeichen des Quelltexts aus dem aktuellen Abschnitt abgeleitet wurde. Der Wert&0; gibt an, Zeichen von Entsprechung zwischen den Quelltext und den abgeleiteten Text. Ein Wert ungleich NULL bedeutet, dass keine solchen direkte Entsprechung vorhanden ist.  
  
 `cwcStartSource`  
 Der Offset, von dem im Abschnitt Quelle der Quelltext für alle abgeleiteten gestartet wird.  
  
 `chunkBreakType`  
 Der Typ der Pause, die das vorherige Segment aus dem aktuellen Abschnitt trennt. Werte werden aus der CHUNK_BREAKTYPE-Enumeration.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setintvalue"></a>CMFCFilterChunkValueImpl::SetIntValue  
 Legen Sie die Eigenschaft durch Schlüssel in int  
  
```  
HRESULT SetIntValue(
    REFPROPERTYKEY pkey,  
    int nVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Parameter  
 `pkey`  
 Gibt einen Schlüssel an.  
  
 `nVal`  
 Gibt den Block-Wert festgelegt.  
  
 `chunkType`  
 Flags geben an, ob dieses Segment eine Text-Datentyp oder ein Werttyp-Eigenschaft enthält. Flagwerte stammen aus der CHUNKSTATE-Enumeration.  
  
 `locale`  
 Die Sprache und Teilsprache eines Teils der Text zugeordnet. Segment Gebietsschema wird von Indexern Dokument zum richtigen Wortumbruch des Texts nicht durchführen. Wenn das Segment weder ein Werttyp mit dem Datentyp VT_LPWSTR, VT_LPSTR oder VT_BSTR als auch Text-Datentyp ist, wird dieses Feld ignoriert.  
  
 `cwcLenSource`  
 Die Länge in Zeichen des Quelltexts aus dem aktuellen Abschnitt abgeleitet wurde. Der Wert&0; gibt an, Zeichen von Entsprechung zwischen den Quelltext und den abgeleiteten Text. Ein Wert ungleich NULL bedeutet, dass keine solchen direkte Entsprechung vorhanden ist.  
  
 `cwcStartSource`  
 Der Offset, von dem im Abschnitt Quelle der Quelltext für alle abgeleiteten gestartet wird.  
  
 `chunkBreakType`  
 Der Typ der Pause, die das vorherige Segment aus dem aktuellen Abschnitt trennt. Werte werden aus der CHUNK_BREAKTYPE-Enumeration.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setlongvalue"></a>CMFCFilterChunkValueImpl::SetLongValue  
 -Taste, um einen Long-Wert festlegen Sie die Eigenschaft.  
  
```  
HRESULT SetLongValue(
    REFPROPERTYKEY pkey,  
    long lVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Parameter  
 `pkey`  
 Gibt einen Schlüssel an.  
  
 `lVal`  
 Gibt den Block-Wert festgelegt.  
  
 `chunkType`  
 Flags geben an, ob dieses Segment eine Text-Datentyp oder ein Werttyp-Eigenschaft enthält. Flagwerte stammen aus der CHUNKSTATE-Enumeration.  
  
 `locale`  
 Die Sprache und Teilsprache eines Teils der Text zugeordnet. Segment Gebietsschema wird von Indexern Dokument zum richtigen Wortumbruch des Texts nicht durchführen. Wenn das Segment weder ein Werttyp mit dem Datentyp VT_LPWSTR, VT_LPSTR oder VT_BSTR als auch Text-Datentyp ist, wird dieses Feld ignoriert.  
  
 `cwcLenSource`  
 Die Länge in Zeichen des Quelltexts aus dem aktuellen Abschnitt abgeleitet wurde. Der Wert&0; gibt an, Zeichen von Entsprechung zwischen den Quelltext und den abgeleiteten Text. Ein Wert ungleich NULL bedeutet, dass keine solchen direkte Entsprechung vorhanden ist.  
  
 `cwcStartSource`  
 Der Offset, von dem im Abschnitt Quelle der Quelltext für alle abgeleiteten gestartet wird.  
  
 `chunkBreakType`  
 Der Typ der Pause, die das vorherige Segment aus dem aktuellen Abschnitt trennt. Werte werden aus der CHUNK_BREAKTYPE-Enumeration.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setsystemtimevalue"></a>CMFCFilterChunkValueImpl::SetSystemTimeValue  
 Legt die Eigenschaft durch den Schlüssel für die SystemTime.  
  
```  
HRESULT SetSystemTimeValue(
    REFPROPERTYKEY pkey,  
    const SYSTEMTIME& systemTime,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale=0,  
    DWORD cwcLenSource=0,  
    DWORD cwcStartSource=0,  
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Parameter  
 `pkey`  
 Gibt einen Schlüssel an.  
  
 `systemTime`  
 Gibt den Block-Wert festgelegt.  
  
 `chunkType`  
 Flags geben an, ob dieses Segment eine Text-Datentyp oder ein Werttyp-Eigenschaft enthält. Flagwerte stammen aus der CHUNKSTATE-Enumeration.  
  
 `locale`  
 Die Sprache und Teilsprache eines Teils der Text zugeordnet. Segment Gebietsschema wird von Indexern Dokument zum richtigen Wortumbruch des Texts nicht durchführen. Wenn das Segment weder ein Werttyp mit dem Datentyp VT_LPWSTR, VT_LPSTR oder VT_BSTR als auch Text-Datentyp ist, wird dieses Feld ignoriert.  
  
 `cwcLenSource`  
 Die Länge in Zeichen des Quelltexts aus dem aktuellen Abschnitt abgeleitet wurde. Der Wert&0; gibt an, Zeichen von Entsprechung zwischen den Quelltext und den abgeleiteten Text. Ein Wert ungleich NULL bedeutet, dass keine solchen direkte Entsprechung vorhanden ist.  
  
 `cwcStartSource`  
 Der Offset, von dem im Abschnitt Quelle der Quelltext für alle abgeleiteten gestartet wird.  
  
 `chunkBreakType`  
 Der Typ der Pause, die das vorherige Segment aus dem aktuellen Abschnitt trennt. Werte werden aus der CHUNK_BREAKTYPE-Enumeration.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="settextvalue"></a>CMFCFilterChunkValueImpl::SetTextValue  
 Legt die Eigenschaft durch Schlüssel in eine Unicode-Zeichenfolge.  
  
```  
HRESULT SetTextValue(
    REFPROPERTYKEY pkey,  
    LPCTSTR pszValue,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Parameter  
 `pkey`  
 Gibt einen Schlüssel an.  
  
 `pszValue`  
 Gibt den Block-Wert festgelegt.  
  
 `chunkType`  
 Flags geben an, ob dieses Segment eine Text-Datentyp oder ein Werttyp-Eigenschaft enthält. Flagwerte stammen aus der CHUNKSTATE-Enumeration.  
  
 `locale`  
 Die Sprache und Teilsprache eines Teils der Text zugeordnet. Segment Gebietsschema wird von Indexern Dokument zum richtigen Wortumbruch des Texts nicht durchführen. Wenn das Segment weder ein Werttyp mit dem Datentyp VT_LPWSTR, VT_LPSTR oder VT_BSTR als auch Text-Datentyp ist, wird dieses Feld ignoriert.  
  
 `cwcLenSource`  
 Die Länge in Zeichen des Quelltexts aus dem aktuellen Abschnitt abgeleitet wurde. Der Wert&0; gibt an, Zeichen von Entsprechung zwischen den Quelltext und den abgeleiteten Text. Ein Wert ungleich NULL bedeutet, dass keine solchen direkte Entsprechung vorhanden ist.  
  
 `cwcStartSource`  
 Der Offset, von dem im Abschnitt Quelle der Quelltext für alle abgeleiteten gestartet wird.  
  
 `chunkBreakType`  
 Der Typ der Pause, die das vorherige Segment aus dem aktuellen Abschnitt trennt. Werte werden aus der CHUNK_BREAKTYPE-Enumeration.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

