---
title: CDaoIndexFieldInfo-Struktur | Microsoft Docs
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
ms.openlocfilehash: 7be9a6a9db842f1e80be62f48a9990cff36168e5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cdaoindexfieldinfo-structure"></a>CDaoIndexFieldInfo-Struktur
Die `CDaoIndexFieldInfo` Struktur enthält Informationen über einen Index Field-Objekt für Datenzugriffsobjekte (DAO) definiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CDaoIndexFieldInfo  
{  
    CString m_strName;          // Primary  
    BOOL m_bDescending;         // Primary  
};  
```  
  
#### <a name="parameters"></a>Parameter  
 `m_strName`  
 Eindeutig benennt den Index Field-Objekt. Details finden Sie im Thema "Name-Eigenschaft" DAO-Hilfe.  
  
 *m_bDescending*  
 Gibt an, die Index-Sortierung durch die Index-Objekt definiert. **"True"** absteigender Reihenfolge.  
  
## <a name="remarks"></a>Hinweise  
 Ein Indexobjekt kann eine Reihe von Feldern, der angibt, welche Felder auf einer Tabledef (oder einem Recordset basierend auf einer Tabelle) indiziert ist, haben. Die Verweise auf die oben genannten primären anzugeben, wie die Informationen zurückgegeben werden, in der `m_pFieldInfos` Mitglied ein [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) abgerufenes durch Aufrufen der `GetIndexInfo` Memberfunktion der Klasse [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo).  
  
 Index und Index-Feld-Objekte werden nicht von einer MFC-Klasse dargestellt. Stattdessen die DAO-Objekten zugrunde liegenden MFC-Objekte der Klasse [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) eine Auflistung von indexobjekten, bezeichnet die Auflistung von Indizes enthalten. Jedes Indexobjekt enthält wiederum eine Auflistung von Field-Objekten. Diese Klassen geben Memberfunktionen für den Zugriff auf einzelne Elemente von Indexinformationen, oder Sie auf Sie zugreifen können alle gleichzeitig mit einem `CDaoIndexInfo` Objekt durch Aufrufen der `GetIndexInfo` Memberfunktion Rand des enthaltenden Objekts. Die `CDaoIndexInfo` Objekt hat dann einen Datenmember `m_pFieldInfos`, verweist auf ein Array von `CDaoIndexFieldInfo` Objekte.  
  
 Rufen Sie die `GetIndexInfo` Memberfunktion Rand des enthaltenden Tabledef oder ein Recordset-Objekts, Sammlung, deren Indizes wird, gespeichert, die Index-Objekt, das Sie von Interesse sind. Klicken Sie dann Zugriff auf die `m_pFieldInfos` Mitglied der [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) Objekt. Die Länge der `m_pFieldInfos` Array befindet sich in `m_nFields`. `CDaoIndexFieldInfo` definiert auch einen `Dump` Memberfunktion in Debug-builds. Sie können `Dump` auf den Inhalt des Basisklassenobjekts auszugeben ein `CDaoIndexFieldInfo` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)   
 [CDaoRecordset::GetIndexInfo](../../mfc/reference/cdaorecordset-class.md#getindexinfo)

