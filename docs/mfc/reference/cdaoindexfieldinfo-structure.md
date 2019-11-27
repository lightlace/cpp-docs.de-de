---
title: CDaoIndexFieldInfo-Struktur
ms.date: 09/17/2019
f1_keywords:
- CDaoIndexFieldInfo
helpviewer_keywords:
- CDaoIndexFieldInfo structure [MFC]
- DAO (Data Access Objects), Index Fields collection
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
ms.openlocfilehash: 10c786ef4fed9ecb3bbbb93526cd68a11e18d58c
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303662"
---
# <a name="cdaoindexfieldinfo-structure"></a>CDaoIndexFieldInfo-Struktur

Die `CDaoIndexFieldInfo`-Struktur enthält Informationen über ein für Data Access Objects (DAO) definiertes Index Feld Objekt.

DAO wird über Office 2013 unterstützt. DAO 3,6 ist die endgültige Version, die als veraltet eingestuft wird.

## <a name="syntax"></a>Syntax

```
struct CDaoIndexFieldInfo
{
    CString m_strName;          // Primary
    BOOL m_bDescending;         // Primary
};
```

#### <a name="parameters"></a>Parameter

*m_strName*<br/>
Benennt das Indexfeld Objekt eindeutig. Weitere Informationen finden Sie im Thema "Name Property" in der DAO-Hilfe.

*m_bDescending*<br/>
Gibt die durch das Index Objekt definierte Index Reihenfolge an. TRUE, wenn die Reihenfolge absteigend ist.

## <a name="remarks"></a>Hinweise

Ein Index Objekt kann über eine Reihe von Feldern verfügen, die angeben, in welchen Feldern eine Tabledef (oder ein Recordset, das auf einer Tabelle basiert) indiziert ist. Die Verweise auf das primäre Replikat geben an, wie die Informationen im `m_pFieldInfos` Member eines [cdaoindexinfo](../../mfc/reference/cdaoindexinfo-structure.md) -Objekts zurückgegeben werden, das durch Aufrufen der `GetIndexInfo` Member-Funktion der Klasse [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo)abgerufen wird.

Index Objekte und Index Feld Objekte werden nicht durch eine MFC-Klasse dargestellt. Stattdessen enthalten die DAO-Objekte, die den MFC-Objekten der Klasse [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) zugrunde liegen, eine Auflistung von Index Objekten, die als Index Auflistung bezeichnet werden. Jedes Index Objekt enthält wiederum eine Auflistung von Feld Objekten. Diese Klassen stellen Element Funktionen bereit, um auf einzelne Elemente von Indexinformationen zuzugreifen, oder Sie können alle auf einmal mit einem `CDaoIndexInfo` Objekt aufrufen, indem Sie die `GetIndexInfo` Member-Funktion des enthaltenden Objekts aufrufen. Das `CDaoIndexInfo`-Objekt hat dann einen Datenmember `m_pFieldInfos`, der auf ein Array von `CDaoIndexFieldInfo` Objekten zeigt.

Ruft die `GetIndexInfo` Member-Funktion des enthaltenden TableDef-oder Recordset-Objekts auf, in dessen Index Auflistung das Index Objekt gespeichert ist, an dem Sie interessiert sind. Greifen Sie dann auf den `m_pFieldInfos` Member des [cdaoindexinfo](../../mfc/reference/cdaoindexinfo-structure.md) -Objekts zu. Die Länge des `m_pFieldInfos` Arrays wird in `m_nFields`gespeichert. `CDaoIndexFieldInfo` definiert auch eine `Dump` Member-Funktion in Debugbuilds. Sie können `Dump` verwenden, um den Inhalt eines `CDaoIndexFieldInfo` Objekts zu speichern.

## <a name="requirements"></a>Voraussetzungen

**Header:** afxdao.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef:: getIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)<br/>
[CDaoRecordset:: getIndexInfo](../../mfc/reference/cdaorecordset-class.md#getindexinfo)
