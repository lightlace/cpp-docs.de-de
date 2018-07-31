---
title: CBookmark-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CBookmark
- ATL::CBookmark<nSize>
- CBookmark
- ATL.CBookmark<nSize>
- ATL::CBookmark
- CBookmark<0>.CBookmark<0>
- CBookmark::CBookmark
- ATL.CBookmark.CBookmark
- CBookmark.CBookmark
- CBookmark
- ATL::CBookmark<0>::CBookmark<0>
- ATL.CBookmark<0>.CBookmark<0>
- CBookmark<0>::CBookmark<0>
- ATL::CBookmark::CBookmark
- ATL.CBookmark<0>.GetBuffer
- ATL.CBookmark.GetBuffer
- ATL::CBookmark<0>::GetBuffer
- ATL::CBookmark::GetBuffer
- CBookmark.GetBuffer
- ATL::CBookmark<nSize>::GetBuffer
- ATL.CBookmark<nSize>.GetBuffer
- CBookmark<0>.GetBuffer
- CBookmark<nSize>::GetBuffer
- CBookmark<0>::GetBuffer
- CBookmark<nSize>.GetBuffer
- CBookmark::GetBuffer
- CBookmark::GetSize
- ATL.CBookmark<nSize>.GetSize
- CBookmark<nSize>.GetSize
- CBookmark.GetSize
- ATL::CBookmark::GetSize
- CBookmark<0>::GetSize
- ATL::CBookmark<nSize>::GetSize
- ATL.CBookmark<0>.GetSize
- ATL::CBookmark<0>::GetSize
- ATL.CBookmark.GetSize
- CBookmark<0>.GetSize
- CBookmark<nSize>::GetSize
- CBookmark<0>::SetBookmark
- ATL.CBookmark<0>.SetBookmark
- CBookmark<0>.SetBookmark
- SetBookmark
- ATL::CBookmark::SetBookmark
- ATL::CBookmark<0>::SetBookmark
- CBookmark.SetBookmark
- ATL.CBookmark.SetBookmark
- CBookmark::SetBookmark
- CBookmark<0>::operator=
- CBookmark<0>.operator=
- ATL.CBookmark.operator=
- CBookmark::operator=
- ATL.CBookmark<0>.operator=
- ATL::CBookmark<0>::operator=
- CBookmark.operator=
- ATL::CBookmark::operator=
dev_langs:
- C++
helpviewer_keywords:
- CBookmark class
- CBookmark class, constructor
- GetBuffer method
- GetSize method
- SetBookmark method
- = operator, with OLE DB templates
- operator =, bookmarks
- operator=, bookmarks
ms.assetid: bc942f95-6f93-41d9-bb6e-bcdae4ae0b7a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9bd662c827650112d0e9bcf1d59086f4205aea58
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337617"
---
# <a name="cbookmark-class"></a>CBookmark-Klasse
Einen Lesezeichenwert enthält in den Puffer.  
  
## <a name="syntax"></a>Syntax

```cpp
template < DBLENGTH nSize = 0 >  
class CBookmark : public CBookmarkBase
  
template <>  
class CBookmark< 0 > : public CBookmarkBase  
```  
  
### <a name="parameters"></a>Parameter  
 *nSize*  
 Die Größe des Lesezeichenpuffers in Byte. Wenn *nSize* ist 0 (null), die Lesezeichen-Puffer wird zur Laufzeit dynamisch erstellt werden.  

## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[CBookmark](#cbookmark)|Der Konstruktor|  
|[GetBuffer](#getbuffer)|Ruft die Zeiger auf den Puffer ab.|  
|[GetSize](#getsize)|Ruft die Größe des Puffers in Bytes ab.|  
|[SetBookmark](#setbookmark)|Legt den Lesezeichenwert.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[operator =](#operator)|Weist ein `CBookmark` Klasse in eine andere.|  
  
## <a name="remarks"></a>Hinweise  
 `CBookmark<0>` ist eine Spezialisierung einer Klassenvorlage von `CBookmark`; des Puffers wird zur Laufzeit dynamisch erstellt.  

## <a name="cbookmark"></a> CBookmark:: CBookmark
Der Konstruktor.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
CBookmark();
   
CBookmark(DBLENGTH nSize);  
```  
  
#### <a name="parameters"></a>Parameter  
 *nSize*  
 [in] Größe des Lesezeichenpuffers in Byte.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Funktion legt Puffer auf NULL und die Puffergröße auf 0 fest. Die zweite Funktion legt die Größe des Puffers auf *nSize*, und der Puffer, in ein Bytearray *nSize* Bytes.  
  
> [!NOTE]
>  Diese Funktion steht nur in `CBookmark<0>`. 
  
## <a name="getbuffer"></a> CBookmark:: GetBuffer
Ruft die Zeiger auf den Puffer Lesezeichen ab.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
virtual BYTE* GetBuffer() const throw();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf der Lesezeichen-Puffer. 

## <a name="getsize"></a> CBookmark:: GetSize
Ruft die Größe des Lesezeichenpuffers ab.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
virtual DBLENGTH GetSize() const throw();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe des Puffers in Byte.  

## <a name="setbookmark"></a> CBookmark:: SetBookmark
Kopiert den Lesezeichenwert verweist *pBuffer* auf die `CBookmark` Puffern und legt die Größe des Puffers auf *nSize*.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT SetBookmark(DBLENGTH nSize, BYTE* pBuffer) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 *nSize*  
 [in] Die Größe des Lesezeichenpuffers.  
  
 *pBuffer*  
 [in] Ein Zeiger auf das Bytearray, das den Wert für Lesezeichen enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard-HRESULT.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion steht nur in `CBookmark<0>`. 

## <a name="operator"></a> CBookmark:: Operator =
Weist eine `CBookmark` zu einem anderen Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
CBookmark& operator =(const CBookmark& bookmark) throw();  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator wird nur in benötigt `CBookmark<0>`.   

## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)