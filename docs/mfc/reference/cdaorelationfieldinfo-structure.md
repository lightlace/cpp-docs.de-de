---
title: CDaoRelationFieldInfo-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoRelationFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationFieldInfo structure
ms.assetid: 47cb89ca-dc80-47ce-96fd-cc4b88512558
caps.latest.revision: 13
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 23d7497502f611cf2311e574556186dc5f7c7d3d
ms.lasthandoff: 02/24/2017

---
# <a name="cdaorelationfieldinfo-structure"></a>CDaoRelationFieldInfo-Struktur
Die `CDaoRelationFieldInfo` Struktur enthält Informationen zu einem Feld in einer Beziehung für Datenzugriffsobjekte (DAO) definiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CDaoRelationFieldInfo  
{  
    CString m_strName;           // Primary  
    CString m_strForeignName;    // Primary  
};  
```  
  
#### <a name="parameters"></a>Parameter  
 `m_strName`  
 Der Name des Felds in der primären Tabelle der Beziehung.  
  
 `m_strForeignName`  
 Der Name des Felds in der fremden Tabelle der Beziehung.  
  
## <a name="remarks"></a>Hinweise  
 Ein DAO-Relation-Objekt gibt die Felder in der primären Tabelle und die Felder in einer Fremdtabelle, die die Beziehung zu definieren. Die Verweise auf die primären in die obige Strukturdefinition anzugeben, wie die Informationen zurückgegeben werden, in der `m_pFieldInfos` Mitglied einer [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) Objekt abgerufen, indem die [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) Memberfunktion der Klasse `CDaoDatabase`.  
  
 Beziehung und Beziehung Feldobjekte werden nicht von einer MFC-Klasse dargestellt. Stattdessen der DAO zugrunde liegenden MFC-Objekte der Klasse Objekte [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) enthalten eine Auflistung von Beziehungsobjekte, die Relations-Auflistung aufgerufen. Jede Relation-Objekt enthält wiederum eine Auflistung von Beziehungsobjekte-Feld. Jedes Feld Beziehungsobjekt korreliert ein Feld in der primären Tabelle mit einem Feld in der fremden Tabelle. Zusammen genommen Beziehung Feldobjekte definieren eine Gruppe von Feldern in jeder Tabelle, die zusammen die Beziehung zu definieren. `CDaoDatabase`ermöglicht den Zugriff auf Beziehungsobjekte mit einer `CDaoRelationInfo` -Objekt durch Aufrufen der `GetRelationInfo` Member-Funktion. Die `CDaoRelationInfo` -Objekt, dann hat einen Datenmember, `m_pFieldInfos`, verweist auf ein Array von `CDaoRelationFieldInfo` Objekte.  
  
 Rufen Sie die [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) -Memberfunktion des enthaltenden `CDaoDatabase` Objekt in dessen Relations-Auflistung ist das Beziehungsobjekt gespeichert Sie interessiert sind. Dann Zugriff auf die `m_pFieldInfos` Mitglied der [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) Objekt. `CDaoRelationFieldInfo`definiert auch eine `Dump` Memberfunktion im Debugmodus erstellt. Sie können `Dump` auf den Inhalt des Basisklassenobjekts auszugeben ein `CDaoRelationFieldInfo` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoRelationInfo-Struktur](../../mfc/reference/cdaorelationinfo-structure.md)

