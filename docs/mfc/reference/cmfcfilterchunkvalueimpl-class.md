---
title: CMFCFilterChunkValueImpl-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CMFCFilterChunkValueImpl [MFC], CMFCFilterChunkValueImpl
- CMFCFilterChunkValueImpl [MFC], Clear
- CMFCFilterChunkValueImpl [MFC], CopyChunk
- CMFCFilterChunkValueImpl [MFC], CopyFrom
- CMFCFilterChunkValueImpl [MFC], GetChunkGUID
- CMFCFilterChunkValueImpl [MFC], GetChunkPID
- CMFCFilterChunkValueImpl [MFC], GetChunkType
- CMFCFilterChunkValueImpl [MFC], GetString
- CMFCFilterChunkValueImpl [MFC], GetValue
- CMFCFilterChunkValueImpl [MFC], GetValueNoAlloc
- CMFCFilterChunkValueImpl [MFC], IsValid
- CMFCFilterChunkValueImpl [MFC], SetBoolValue
- CMFCFilterChunkValueImpl [MFC], SetDwordValue
- CMFCFilterChunkValueImpl [MFC], SetFileTimeValue
- CMFCFilterChunkValueImpl [MFC], SetInt64Value
- CMFCFilterChunkValueImpl [MFC], SetIntValue
- CMFCFilterChunkValueImpl [MFC], SetLongValue
- CMFCFilterChunkValueImpl [MFC], SetSystemTimeValue
- CMFCFilterChunkValueImpl [MFC], SetTextValue
- CMFCFilterChunkValueImpl [MFC], SetChunk
ms.assetid: 3c833f23-5b88-4d08-9e09-ca6a8aec88bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1f2fcdedb6b01025b06e4384ec2c32e95d08b6e
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040128"
---
# <a name="cmfcfilterchunkvalueimpl-class"></a>CMFCFilterChunkValueImpl-Klasse
Dies ist eine Klasse, die Segment und Eigenschaft-Wert-Paar Logik vereinfacht.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCFilterChunkValueImpl : public ATL::IFilterChunkValue;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl:: ~ CMFCFilterChunkValueImpl](#_dtorcmfcfilterchunkvalueimpl)|Destructs das Objekt an.|  
|[CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl](#cmfcfilterchunkvalueimpl)|Erstellt das Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl::Clear](#clear)|Löscht die ChunkValue an.|  
|[CMFCFilterChunkValueImpl::CopyChunk](#copychunk)|Kopiert dieses Segment in eine Struktur, beschreibt die Merkmale eines Teils an.|  
|[CMFCFilterChunkValueImpl::CopyFrom](#copyfrom)|Dieser Block-Wert aus der andere Wert initialisiert.|  
|[CMFCFilterChunkValueImpl::GetChunkGUID](#getchunkguid)|Ruft die GUID des Segments ab.|  
|[CMFCFilterChunkValueImpl::GetChunkPID](#getchunkpid)|Ruft das Segment PID (Eigenschafts-ID) ab.|  
|[CMFCFilterChunkValueImpl::GetChunkType](#getchunktype)|Ruft in Blöcken Typ.|  
|[CMFCFilterChunkValueImpl::GetString](#getstring)|Ruft ab, der den Zeichenfolgenwert.|  
|[CMFCFilterChunkValueImpl::GetValue](#getvalue)|Ruft den Wert als eine zugeordnete Propvariant ab.|  
|[CMFCFilterChunkValueImpl::GetValueNoAlloc](#getvaluenoalloc)|Gibt nicht reserviert (interne Wert)-Wert.|  
|[CMFCFilterChunkValueImpl::IsValid](#isvalid)|Überprüft, ob der Wert dieser Eigenschaft gültig ist.|  
|[CMFCFilterChunkValueImpl::SetBoolValue](#setboolvalue)|Überladen. Legt die Eigenschaft durch Schlüssel in einen booleschen Wert fest.|  
|[CMFCFilterChunkValueImpl::SetDwordValue](#setdwordvalue)|Legt die Eigenschaft durch Taste, um einen DWORD-Wert.|  
|[CMFCFilterChunkValueImpl::SetFileTimeValue](#setfiletimevalue)|Legt die Eigenschaft durch Schlüssel zu einer Filetime fest.|  
|[CMFCFilterChunkValueImpl::SetInt64Value](#setint64value)|Legt die Eigenschaft durch den Schlüssel zu einem Int64-Typ.|  
|[CMFCFilterChunkValueImpl::SetIntValue](#setintvalue)|Legt die Eigenschaft durch den Schlüssel für ein "int".|  
|[CMFCFilterChunkValueImpl::SetLongValue](#setlongvalue)|Legt die Eigenschaft durch Taste, um einen Long-Wert fest.|  
|[CMFCFilterChunkValueImpl::SetSystemTimeValue](#setsystemtimevalue)|Legt die Eigenschaft durch Schlüssel in eine SystemTime.|  
|[CMFCFilterChunkValueImpl::SetTextValue](#settextvalue)|Legt die Eigenschaft durch Schlüssel in eine Unicode-Zeichenfolge.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl::SetChunk](#setchunk)|Eine Hilfsfunktion, die allgemeine Eigenschaften für das Segment festlegt.|  
  
## <a name="remarks"></a>Hinweise  
 Um zu verwenden, erstellen Sie einfach eine CMFCFilterChunkValueImpl-Klasse, der die richtige Art  
  
 Beispiel:  
  
 CMFCFilterChunkValueImpl-Segment;  
  
 HR = Block. SetBoolValue(PKEY_IsAttachment, true);  
  
 oder  
  
 HR = Block. SetFileTimeValue (PKEY_ItemDate FtLastModified);  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ATL::IFilterChunkValue`  
  
 [CMFCFilterChunkValueImpl](../../mfc/reference/cmfcfilterchunkvalueimpl-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="clear"></a>  CMFCFilterChunkValueImpl::Clear  
 Löscht die ChunkValue an.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="cmfcfilterchunkvalueimpl"></a>  CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl  
 Erstellt das Objekt.  
  
```  
CMFCFilterChunkValueImpl();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="_dtorcmfcfilterchunkvalueimpl"></a>  CMFCFilterChunkValueImpl:: ~ CMFCFilterChunkValueImpl  
 Destructs das Objekt an.  
  
```  
virtual ~CMFCFilterChunkValueImpl();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="copychunk"></a>  CMFCFilterChunkValueImpl::CopyChunk  
 Kopiert dieses Segment in eine Struktur, beschreibt die Merkmale eines Teils an.  
  
```  
HRESULT CopyChunk(STAT_CHUNK* pStatChunk);
```  
  
### <a name="parameters"></a>Parameter  
 *pStatChunk*  
 Ein Zeiger auf den Zielwert, beschreibt die Merkmale des Segments.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="copyfrom"></a>  CMFCFilterChunkValueImpl::CopyFrom  
 Dieser Block-Wert aus der andere Wert initialisiert.  
  
```  
void CopyFrom (IFilterChunkValue* pValue);
```  
  
### <a name="parameters"></a>Parameter  
 *pValue*  
 Gibt den Quellwert, aus dem kopiert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getchunkguid"></a>  CMFCFilterChunkValueImpl::GetChunkGUID  
 Ruft die GUID des Segments ab.  
  
```  
REFGUID GetChunkGUID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf eine GUID zur Kennzeichnung des Segments benötigten.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getchunkpid"></a>  CMFCFilterChunkValueImpl::GetChunkPID  
 Ruft das Segment PID (Eigenschafts-ID) ab.  
  
```  
DWORD GetChunkPID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine DWORD-Wert, der mit der Eigenschafts-ID an.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getchunktype"></a>  CMFCFilterChunkValueImpl::GetChunkType  
 Ruft den Typ des Segments ab.  
  
```  
CHUNKSTATE GetChunkType() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein CHUNKSTATE aufgezählt-Wert, der angibt, ob das aktuelle Segment einen Text-Type-Eigenschaft oder eine Eigenschaft Werttyp ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getstring"></a>  CMFCFilterChunkValueImpl::GetString  
 Ruft den Zeichenfolgenwert ab.  
  
```  
CString &GetString();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge mit der Segment-Wert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getvalue"></a>  CMFCFilterChunkValueImpl::GetValue  
 Ruft den Wert als eine zugeordnete Propvariant ab.  
  
```  
HRESULT GetValue(PROPVARIANT** ppPropVariant);
```  
  
### <a name="parameters"></a>Parameter  
 *ppPropVariant*  
 Wenn die Funktion zurückgibt, enthält dieser Parameter die Block-Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn PROPVARIANT erfolgreich zugewiesen wurde und die Block-Wert wurde erfolgreich kopiert wurde *PpPropVariant*andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getvaluenoalloc"></a>  CMFCFilterChunkValueImpl::GetValueNoAlloc  
 Gibt den nicht reservierten (interne) Wert zurück.  
  
```  
PROPVARIANT GetValueNoAlloc ();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der aktuelle Block-Wert zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isvalid"></a>  CMFCFilterChunkValueImpl::IsValid  
 Überprüft, ob der Wert dieser Eigenschaft gültig ist.  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der aktuelle Block-Wert gültig ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setboolvalue"></a>  CMFCFilterChunkValueImpl::SetBoolValue  
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
 *Primärschlüssel*  
 Gibt einen Schlüssel an.  
  
 *bVal*  
 Gibt den Block-Wert festgelegt.  
  
 *chunkType*  
 Flags geben an, ob dieses Segment einen Text-Typ oder ein Werttyp Eigenschaft enthält. Flagwerte stammen aus der CHUNKSTATE-Enumeration.  
  
 *locale*  
 Die Sprache und der untersprachen eines Teils der Text zugeordnet. Block-Gebietsschema Dokument Indexer wird von führen Sie die richtige wörtertrennung des Texts. Wenn das Segment weder ein Werttyp, mit dem Datentyp VT_LPWSTR, VT_LPSTR oder "VT_BSTR" als auch Text-Datentyp ist, wird dieses Feld ignoriert.  
  
 *cwcLenSource*  
 Die Länge in Zeichen des Quelltexts aus dem das aktuelle Segment abgeleitet wurde. Ein NULL-Wert gibt die Zeichen für Zeichen-Entsprechung zwischen den Quell- und die abgeleiteten Text an. Ein Wert ungleich NULL bedeutet, dass keine solche direkte Entsprechung vorhanden ist.  
  
 *cwcStartSource*  
 Der Offset aus dem des Quelltexts für einen abgeleiteten Datenblock in den Quell-Block beginnt.  
  
 *chunkBreakType*  
 Der Typ der Pause, die von der aktuellen Block den vorherigen Block trennt. Werte reichen von der CHUNK_BREAKTYPE-Enumeration.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setchunk"></a>  CMFCFilterChunkValueImpl::SetChunk  
 Eine Hilfsfunktion, die allgemeine Eigenschaften für das Segment festlegt.  
  
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
 *Primärschlüssel*  
 Gibt einen Schlüssel an.  
  
 *chunkType*  
 Flags geben an, ob dieses Segment einen Text-Typ oder ein Werttyp Eigenschaft enthält. Flagwerte stammen aus der CHUNKSTATE-Enumeration.  
  
 *locale*  
 Die Sprache und der untersprachen eines Teils der Text zugeordnet. Block-Gebietsschema Dokument Indexer wird von führen Sie die richtige wörtertrennung des Texts. Wenn das Segment weder ein Werttyp, mit dem Datentyp VT_LPWSTR, VT_LPSTR oder "VT_BSTR" als auch Text-Datentyp ist, wird dieses Feld ignoriert.  
  
 *cwcLenSource*  
 Die Länge in Zeichen des Quelltexts aus dem das aktuelle Segment abgeleitet wurde. Ein NULL-Wert gibt die Zeichen für Zeichen-Entsprechung zwischen den Quell- und die abgeleiteten Text an. Ein Wert ungleich NULL bedeutet, dass keine solche direkte Entsprechung vorhanden ist.  
  
 *cwcStartSource*  
 Der Offset aus dem des Quelltexts für einen abgeleiteten Datenblock in den Quell-Block beginnt.  
  
 *chunkBreakType*  
 Der Typ der Pause, die von der aktuellen Block den vorherigen Block trennt. Werte reichen von der CHUNK_BREAKTYPE-Enumeration.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setdwordvalue"></a>  CMFCFilterChunkValueImpl::SetDwordValue  
 Legen Sie die Eigenschaft durch Taste, um einen DWORD-Wert.  
  
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
 *Primärschlüssel*  
 Gibt einen Schlüssel an.  
  
 *dwVal*  
 Gibt den Block-Wert festgelegt.  
  
 *chunkType*  
 Flags geben an, ob dieses Segment einen Text-Typ oder ein Werttyp Eigenschaft enthält. Flagwerte stammen aus der CHUNKSTATE-Enumeration.  
  
 *locale*  
 Die Sprache und der untersprachen eines Teils der Text zugeordnet. Block-Gebietsschema Dokument Indexer wird von führen Sie die richtige wörtertrennung des Texts. Wenn das Segment weder ein Werttyp, mit dem Datentyp VT_LPWSTR, VT_LPSTR oder "VT_BSTR" als auch Text-Datentyp ist, wird dieses Feld ignoriert.  
  
 *cwcLenSource*  
 Die Länge in Zeichen des Quelltexts aus dem das aktuelle Segment abgeleitet wurde. Ein NULL-Wert gibt die Zeichen für Zeichen-Entsprechung zwischen den Quell- und die abgeleiteten Text an. Ein Wert ungleich NULL bedeutet, dass keine solche direkte Entsprechung vorhanden ist.  
  
 *cwcStartSource*  
 Der Offset aus dem des Quelltexts für einen abgeleiteten Datenblock in den Quell-Block beginnt.  
  
 *chunkBreakType*  
 Der Typ der Pause, die von der aktuellen Block den vorherigen Block trennt. Werte reichen von der CHUNK_BREAKTYPE-Enumeration.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setfiletimevalue"></a>  CMFCFilterChunkValueImpl::SetFileTimeValue  
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
 *Primärschlüssel*  
 Gibt einen Schlüssel an.  
  
 *dtVal*  
 Gibt den Block-Wert festgelegt.  
  
 *chunkType*  
 Flags geben an, ob dieses Segment einen Text-Typ oder ein Werttyp Eigenschaft enthält. Flagwerte stammen aus der CHUNKSTATE-Enumeration.  
  
 *locale*  
 Die Sprache und der untersprachen eines Teils der Text zugeordnet. Block-Gebietsschema Dokument Indexer wird von führen Sie die richtige wörtertrennung des Texts. Wenn das Segment weder ein Werttyp, mit dem Datentyp VT_LPWSTR, VT_LPSTR oder "VT_BSTR" als auch Text-Datentyp ist, wird dieses Feld ignoriert.  
  
 *cwcLenSource*  
 Die Länge in Zeichen des Quelltexts aus dem das aktuelle Segment abgeleitet wurde. Ein NULL-Wert gibt die Zeichen für Zeichen-Entsprechung zwischen den Quell- und die abgeleiteten Text an. Ein Wert ungleich NULL bedeutet, dass keine solche direkte Entsprechung vorhanden ist.  
  
 *cwcStartSource*  
 Der Offset aus dem des Quelltexts für einen abgeleiteten Datenblock in den Quell-Block beginnt.  
  
 *chunkBreakType*  
 Der Typ der Pause, die von der aktuellen Block den vorherigen Block trennt. Werte reichen von der CHUNK_BREAKTYPE-Enumeration.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setint64value"></a>  CMFCFilterChunkValueImpl::SetInt64Value  
 Legen Sie die Eigenschaft durch den Schlüssel zu einem Int64-Typ.  
  
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
 *Primärschlüssel*  
 Gibt einen Schlüssel an.  
  
 *nVal*  
 Gibt den Block-Wert festgelegt.  
  
 *chunkType*  
 Flags geben an, ob dieses Segment einen Text-Typ oder ein Werttyp Eigenschaft enthält. Flagwerte stammen aus der CHUNKSTATE-Enumeration.  
  
 *locale*  
 Die Sprache und der untersprachen eines Teils der Text zugeordnet. Block-Gebietsschema Dokument Indexer wird von führen Sie die richtige wörtertrennung des Texts. Wenn das Segment weder ein Werttyp, mit dem Datentyp VT_LPWSTR, VT_LPSTR oder "VT_BSTR" als auch Text-Datentyp ist, wird dieses Feld ignoriert.  
  
 *cwcLenSource*  
 Die Länge in Zeichen des Quelltexts aus dem das aktuelle Segment abgeleitet wurde. Ein NULL-Wert gibt die Zeichen für Zeichen-Entsprechung zwischen den Quell- und die abgeleiteten Text an. Ein Wert ungleich NULL bedeutet, dass keine solche direkte Entsprechung vorhanden ist.  
  
 *cwcStartSource*  
 Der Offset aus dem des Quelltexts für einen abgeleiteten Datenblock in den Quell-Block beginnt.  
  
 *chunkBreakType*  
 Der Typ der Pause, die von der aktuellen Block den vorherigen Block trennt. Werte reichen von der CHUNK_BREAKTYPE-Enumeration.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setintvalue"></a>  CMFCFilterChunkValueImpl::SetIntValue  
 Legen Sie die Eigenschaft durch den Schlüssel für ein "int".  
  
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
 *Primärschlüssel*  
 Gibt einen Schlüssel an.  
  
 *nVal*  
 Gibt den Block-Wert festgelegt.  
  
 *chunkType*  
 Flags geben an, ob dieses Segment einen Text-Typ oder ein Werttyp Eigenschaft enthält. Flagwerte stammen aus der CHUNKSTATE-Enumeration.  
  
 *locale*  
 Die Sprache und der untersprachen eines Teils der Text zugeordnet. Block-Gebietsschema Dokument Indexer wird von führen Sie die richtige wörtertrennung des Texts. Wenn das Segment weder ein Werttyp, mit dem Datentyp VT_LPWSTR, VT_LPSTR oder "VT_BSTR" als auch Text-Datentyp ist, wird dieses Feld ignoriert.  
  
 *cwcLenSource*  
 Die Länge in Zeichen des Quelltexts aus dem das aktuelle Segment abgeleitet wurde. Ein NULL-Wert gibt die Zeichen für Zeichen-Entsprechung zwischen den Quell- und die abgeleiteten Text an. Ein Wert ungleich NULL bedeutet, dass keine solche direkte Entsprechung vorhanden ist.  
  
 *cwcStartSource*  
 Der Offset aus dem des Quelltexts für einen abgeleiteten Datenblock in den Quell-Block beginnt.  
  
 *chunkBreakType*  
 Der Typ der Pause, die von der aktuellen Block den vorherigen Block trennt. Werte reichen von der CHUNK_BREAKTYPE-Enumeration.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setlongvalue"></a>  CMFCFilterChunkValueImpl::SetLongValue  
 Legen Sie die Eigenschaft durch Taste, um einen Long-Wert.  
  
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
 *Primärschlüssel*  
 Gibt einen Schlüssel an.  
  
 *lVal*  
 Gibt den Block-Wert festgelegt.  
  
 *chunkType*  
 Flags geben an, ob dieses Segment einen Text-Typ oder ein Werttyp Eigenschaft enthält. Flagwerte stammen aus der CHUNKSTATE-Enumeration.  
  
 *locale*  
 Die Sprache und der untersprachen eines Teils der Text zugeordnet. Block-Gebietsschema Dokument Indexer wird von führen Sie die richtige wörtertrennung des Texts. Wenn das Segment weder ein Werttyp, mit dem Datentyp VT_LPWSTR, VT_LPSTR oder "VT_BSTR" als auch Text-Datentyp ist, wird dieses Feld ignoriert.  
  
 *cwcLenSource*  
 Die Länge in Zeichen des Quelltexts aus dem das aktuelle Segment abgeleitet wurde. Ein NULL-Wert gibt die Zeichen für Zeichen-Entsprechung zwischen den Quell- und die abgeleiteten Text an. Ein Wert ungleich NULL bedeutet, dass keine solche direkte Entsprechung vorhanden ist.  
  
 *cwcStartSource*  
 Der Offset aus dem des Quelltexts für einen abgeleiteten Datenblock in den Quell-Block beginnt.  
  
 *chunkBreakType*  
 Der Typ der Pause, die von der aktuellen Block den vorherigen Block trennt. Werte reichen von der CHUNK_BREAKTYPE-Enumeration.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setsystemtimevalue"></a>  CMFCFilterChunkValueImpl::SetSystemTimeValue  
 Legt die Eigenschaft durch Schlüssel in eine SystemTime.  
  
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
 *Primärschlüssel*  
 Gibt einen Schlüssel an.  
  
 *systemTime*  
 Gibt den Block-Wert festgelegt.  
  
 *chunkType*  
 Flags geben an, ob dieses Segment einen Text-Typ oder ein Werttyp Eigenschaft enthält. Flagwerte stammen aus der CHUNKSTATE-Enumeration.  
  
 *locale*  
 Die Sprache und der untersprachen eines Teils der Text zugeordnet. Block-Gebietsschema Dokument Indexer wird von führen Sie die richtige wörtertrennung des Texts. Wenn das Segment weder ein Werttyp, mit dem Datentyp VT_LPWSTR, VT_LPSTR oder "VT_BSTR" als auch Text-Datentyp ist, wird dieses Feld ignoriert.  
  
 *cwcLenSource*  
 Die Länge in Zeichen des Quelltexts aus dem das aktuelle Segment abgeleitet wurde. Ein NULL-Wert gibt die Zeichen für Zeichen-Entsprechung zwischen den Quell- und die abgeleiteten Text an. Ein Wert ungleich NULL bedeutet, dass keine solche direkte Entsprechung vorhanden ist.  
  
 *cwcStartSource*  
 Der Offset aus dem des Quelltexts für einen abgeleiteten Datenblock in den Quell-Block beginnt.  
  
 *chunkBreakType*  
 Der Typ der Pause, die von der aktuellen Block den vorherigen Block trennt. Werte reichen von der CHUNK_BREAKTYPE-Enumeration.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="settextvalue"></a>  CMFCFilterChunkValueImpl::SetTextValue  
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
 *Primärschlüssel*  
 Gibt einen Schlüssel an.  
  
 *pszValue*  
 Gibt den Block-Wert festgelegt.  
  
 *chunkType*  
 Flags geben an, ob dieses Segment einen Text-Typ oder ein Werttyp Eigenschaft enthält. Flagwerte stammen aus der CHUNKSTATE-Enumeration.  
  
 *locale*  
 Die Sprache und der untersprachen eines Teils der Text zugeordnet. Block-Gebietsschema Dokument Indexer wird von führen Sie die richtige wörtertrennung des Texts. Wenn das Segment weder ein Werttyp, mit dem Datentyp VT_LPWSTR, VT_LPSTR oder "VT_BSTR" als auch Text-Datentyp ist, wird dieses Feld ignoriert.  
  
 *cwcLenSource*  
 Die Länge in Zeichen des Quelltexts aus dem das aktuelle Segment abgeleitet wurde. Ein NULL-Wert gibt die Zeichen für Zeichen-Entsprechung zwischen den Quell- und die abgeleiteten Text an. Ein Wert ungleich NULL bedeutet, dass keine solche direkte Entsprechung vorhanden ist.  
  
 *cwcStartSource*  
 Der Offset aus dem des Quelltexts für einen abgeleiteten Datenblock in den Quell-Block beginnt.  
  
 *chunkBreakType*  
 Der Typ der Pause, die von der aktuellen Block den vorherigen Block trennt. Werte reichen von der CHUNK_BREAKTYPE-Enumeration.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
