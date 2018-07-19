---
title: CDaoIndexFieldInfo-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoIndexFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoIndexFieldInfo structure [MFC]
- DAO (Data Access Objects), Index Fields collection
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37149e2a4a2780c97cc7c2774c64e9a6037d37a7
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37337878"
---
# <a name="cdaoindexfieldinfo-structure"></a>CDaoIndexFieldInfo-Struktur
Die `CDaoIndexFieldInfo` Struktur enthält Informationen zu einem Index-Feld-Objekt für Datenzugriffsobjekte (DAO) definiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CDaoIndexFieldInfo  
{  
    CString m_strName;          // Primary  
    BOOL m_bDescending;         // Primary  
};  
```  
  
#### <a name="parameters"></a>Parameter  
 *m_strName*  
 Eindeutig bezeichnet die Index-Field-Objekt. Informationen finden Sie im Thema "Name-Eigenschaft" in-DAO-Hilfe.  
  
 *m_bDescending*  
 Gibt an, die Index-Sortierung definiert, die vom Index-Objekt. TRUE, wenn die Reihenfolge absteigender ist.  
  
## <a name="remarks"></a>Hinweise  
 Ein Indexobjekt haben eine Reihe von Feldern, der angibt, welche Felder auf eine Tabledef (oder ein Recordset basierend auf einer Tabelle) indiziert wird. Die Verweise auf die oben genannten primären anzugeben, wie die Informationen zurückgegeben werden, in der `m_pFieldInfos` Mitglied einer [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) Objekt durch den Aufruf der `GetIndexInfo` Memberfunktion der Klasse [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo).  
  
 Index und Index-Feld-Objekte werden nicht durch eine MFC-Klasse dargestellt. Stattdessen Objekte zum DAO zugrunde liegenden MFC-Objekte der Klasse [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) enthalten eine Auflistung von indexobjekten, die der Indexsammlung aufgerufen. Jedes Indexobjekt enthält wiederum eine Auflistung von Feld-Objekten. Diese Klassen geben Member-Funktionen für den Zugriff auf einzelne Elemente der Informationen zu Indizes an, oder darauf gleichzeitig mit zugreifen eine `CDaoIndexInfo` -Objekt durch Aufrufen der `GetIndexInfo` Memberfunktion Rand des enthaltenden Objekts. Die `CDaoIndexInfo` Objekt hat dann einen Datenmember `m_pFieldInfos`, verweist auf ein Array von `CDaoIndexFieldInfo` Objekte.  
  
 Rufen Sie die `GetIndexInfo` Memberfunktion Rand des enthaltenden Tabledef oder ein Recordset-Objekts, in deren Indizes Auflistung wird, gespeichert, die Index-Objekt, das Sie interessiert sind. Öffnen Sie dann die `m_pFieldInfos` Mitglied der [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) Objekt. Die Länge der `m_pFieldInfos` Array befindet sich in `m_nFields`. `CDaoIndexFieldInfo` definiert auch eine `Dump` -Memberfunktion im Debug-builds. Können Sie `Dump` zum Sichern den Inhalt einer `CDaoIndexFieldInfo` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)   
 [CDaoRecordset::GetIndexInfo](../../mfc/reference/cdaorecordset-class.md#getindexinfo)

