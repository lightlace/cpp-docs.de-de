---
title: IAtlStringMgr-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- IAtlStringMgr
- ATLSIMPSTR/ATL::IAtlStringMgr
- ATLSIMPSTR/ATL::Allocate
- ATLSIMPSTR/ATL::Clone
- ATLSIMPSTR/ATL::Free
- ATLSIMPSTR/ATL::GetNilString
- ATLSIMPSTR/ATL::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- shared classes, IAtlStringMgr
- memory, managing
- IAtlStringMgr class
ms.assetid: 722f0346-a770-4aa7-8f94-177be8dba823
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9586c0f15dc098688020acae0fb96c0e363ad285
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43756375"
---
# <a name="iatlstringmgr-class"></a>IAtlStringMgr-Klasse

Diese Klasse stellt die Schnittstelle für eine `CStringT` Speicher-Manager.

## <a name="syntax"></a>Syntax

```
__interface IAtlStringMgr
```

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[zuordnen](#allocate)|Rufen Sie diese Methode, um eine neue Zeichenfolge Datenstruktur reservieren.|
|[Clone](#clone)|Rufen Sie diese Methode, um die Rückgabe eines Zeigers auf einen neuen Zeichenfolge-Manager für die Verwendung mit einer anderen Instanz von `CSimpleStringT`.|
|[kostenlos](#free)|Rufen Sie diese Methode, um eine zeichenfolgendatenstruktur frei.|
|[GetNilString](#getnilstring)|Gibt einen Zeiger auf die `CStringData` Objekt von Objekten der leeren Zeichenfolge verwendet wird.|
|[Zum erneuten Zuweisen](#reallocate)|Rufen Sie diese Methode, um eine String-Datenstruktur zum erneuten zuweisen.|

## <a name="remarks"></a>Hinweise

Diese Schnittstelle verwaltet den Arbeitsspeicher, die von den Klassen der MFC-unabhängigen-Zeichenfolge verwendet. wie z. B. [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), und [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md).

Sie können auch diese Klasse verwenden, um einen benutzerdefinierten Speicher-Manager für die benutzerdefinierte Zeichenfolge-Klasse zu implementieren. Weitere Informationen finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="requirements"></a>Anforderungen

**Header:** atlsimpstr.h

##  <a name="allocate"></a>  IAtlStringMgr::Allocate

Weist eine neue Zeichenfolge-Datenstruktur.

```
CStringData* Allocate(int nAllocLength,int nCharSize) throw();
```

### <a name="parameters"></a>Parameter

*nAllocLength*  
Die Anzahl der Zeichen im neuen Speicherblock.

*nCharSize*  
Die Größe (in Byte) von der Art der Zeichen, die von der Zeichenfolge-Manager verwendet werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf den neu belegten Speicherblock zurück.

> [!NOTE]
>  Signalisieren Sie eine fehlerhafte Zuordnung nicht durch Auslösen einer Ausnahme. Stattdessen sollte eine fehlerhafte Zuordnung angewiesen werden, von NULL zurückgegeben.

### <a name="remarks"></a>Hinweise

Rufen Sie [IAtlStringMgr::Free](#free) oder [IAtlStringMgr::ReAllocate](#reallocate) um den von dieser Methode belegten Arbeitsspeicher freizugeben.

> [!NOTE]
>  Verwendungsbeispiele finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

##  <a name="clone"></a>  IAtlStringMgr::Clone

Gibt einen Zeiger auf einen neuen Zeichenfolge-Manager für die Verwendung mit einer anderen Instanz von `CSimpleStringT`.

```
IAtlStringMgr* Clone() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt eine Kopie der `IAtlStringMgr` Objekt.

### <a name="remarks"></a>Hinweise

Im Allgemeinen vom Framework aufgerufen, wenn ein Zeichenfolgen-Manager für eine neue Zeichenfolge benötigt werden. In den meisten Fällen die **dies** Zeiger zurückgegeben.

Aber wenn der Speicher-Manager nicht unterstützt, die von mehreren Instanzen verwendet wird `CSimpleStringT`, ein Zeiger auf einen freigegebenen zeichenfolgenmanagers zurückgegeben werden sollen.

> [!NOTE]
>  Verwendungsbeispiele finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

##  <a name="free"></a>  IAtlStringMgr::Free

Gibt eine zeichenfolgendatenstruktur frei.

```
void Free(CStringData* pData) throw();
```

### <a name="parameters"></a>Parameter

*pData*  
Ein Zeiger zum Speicherblock freigegeben werden.

### <a name="remarks"></a>Hinweise

Den angegebene Speicherblock von zuvor zugewiesenen frei [Allocate](#allocate) oder [zum erneuten Zuweisen von](../../atl/reference/iatlmemmgr-class.md#reallocate).

> [!NOTE]
>  Verwendungsbeispiele finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

##  <a name="getnilstring"></a>  IAtlStringMgr::GetNilString

Gibt einen Zeiger auf eine zeichenfolgendatenstruktur für eine leere Zeichenfolge zurück.

```
CStringData* GetNilString() throw();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die `CStringData` Objekt verwendet, um eine leere Zeichenfolge darzustellen.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion, um eine Darstellung eine leere Zeichenfolge zurück.

> [!NOTE]
>  Beim Implementieren eines benutzerdefinierten zeichenfolgenmanagers muss diese Funktion niemals Fehler verursachen. Sie können sicherstellen, dass dies durch die Einbettung von einer Instanz von `CNilStringData` in der Manager-Zeichenfolgenklasse, und Rückgabe einen Zeiger an diese Instanz.

> [!NOTE]
>  Verwendungsbeispiele finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

##  <a name="reallocate"></a>  IAtlStringMgr::Reallocate

Ordnet eine zeichenfolgendatenstruktur neu.

```
CStringData* Reallocate(  
CStringData* pData,
int nAllocLength,
int nCharSize) throw();
```

### <a name="parameters"></a>Parameter

*pData*  
Zeiger auf den von diesem Speicher-Manager zuvor belegten Arbeitsspeicher.

*nAllocLength*  
Die Anzahl der Zeichen im neuen Speicherblock.

*nCharSize*  
Die Größe (in Byte) von der Art der Zeichen, die von der Zeichenfolge-Manager verwendet werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf den Anfang des neu belegten Speicherblocks zurück.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion wird zum Ändern der Größe des vorhandenen Speicherblocks, der anhand des *pData*.

Rufen Sie [IAtlStringMgr::Free](#free) um den von dieser Methode belegten Arbeitsspeicher freizugeben.

> [!NOTE]
>  Verwendungsbeispiele finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
[Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)

