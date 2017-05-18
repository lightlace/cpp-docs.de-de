---
title: CDaoIndexFieldInfo-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoIndexFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoIndexFieldInfo structure
- DAO (Data Access Objects), Index Fields collection
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
caps.latest.revision: 12
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 975b3a704936adc9d4205938bb2c757ab650f0d9
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

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
 Die Index-Field-Objekt bezeichnet eindeutig. Details finden Sie im Thema "Name-Eigenschaft" in der DAO-Hilfe.  
  
 *m_bDescending*  
 Gibt an, die Index-Sortierung durch die Index-Objekt definiert. **TRUE** absteigender Reihenfolge.  
  
## <a name="remarks"></a>Hinweise  
 Ein Indexobjekt haben eine Reihe von Feldern, der angibt, welche Felder in einer Tabledef (oder ein Recordset basierend auf einer Tabelle) indiziert ist. Die Verweise auf die primären oben anzugeben, wie die Informationen zurückgegeben werden, in der `m_pFieldInfos` Mitglied einer [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) Objekt abgerufen, indem die `GetIndexInfo` Memberfunktion der Klasse [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo).  
  
 Index und Index-Feld-Objekte werden nicht durch eine MFC-Klasse dargestellt. Stattdessen der DAO zugrunde liegenden MFC-Objekte der Klasse Objekte [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) enthalten eine Auflistung von indexobjekten, die die Auflistung von Indizes aufgerufen. Jeder Index-Objekt enthält wiederum eine Auflistung von Field-Objekten. Diese Klassen Memberfunktionen für den Zugriff auf einzelne Elemente von Indexinformationen oder können sie gleichzeitig mit zugreifen ein `CDaoIndexInfo` -Objekt durch Aufrufen der `GetIndexInfo` -Memberfunktion des enthaltenden Objekts. Die `CDaoIndexInfo` -Objekt, dann hat einen Datenmember, `m_pFieldInfos`, verweist auf ein Array von `CDaoIndexFieldInfo` Objekte.  
  
 Rufen Sie die `GetIndexInfo` -Memberfunktion des Tabledef oder DAO-Recordsets Containerobjekts, deren Indizes Sammlung wird, gespeichert, die Index-Objekt, das Sie interessiert sind. Dann Zugriff auf die `m_pFieldInfos` Mitglied der [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) Objekt. Die Länge der `m_pFieldInfos` Array befindet sich in `m_nFields`. `CDaoIndexFieldInfo`definiert auch eine `Dump` Memberfunktion im Debugmodus erstellt. Sie können `Dump` auf den Inhalt des Basisklassenobjekts auszugeben ein `CDaoIndexFieldInfo` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)   
 [CDaoRecordset::GetIndexInfo](../../mfc/reference/cdaorecordset-class.md#getindexinfo)


