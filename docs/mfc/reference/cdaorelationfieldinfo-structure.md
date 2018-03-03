---
title: CDaoRelationFieldInfo-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoRelationFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationFieldInfo structure [MFC]
ms.assetid: 47cb89ca-dc80-47ce-96fd-cc4b88512558
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a8b9d27154608a19da1e575a46ec424f11eec2e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdaorelationfieldinfo-structure"></a>CDaoRelationFieldInfo-Struktur
Die `CDaoRelationFieldInfo` Struktur enthält Informationen über ein Feld in einer Beziehung für Datenzugriffsobjekte (DAO) definiert.  
  
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
 Ein DAO-Beziehungsobjekt gibt die Felder in einer primären Tabelle und die Felder in einer Fremdschlüsseltabelle, die die Beziehung definieren. Die Verweise auf die primären in die Strukturdefinition, die oben genannten anzugeben, wie die Informationen zurückgegeben werden, in der `m_pFieldInfos` Mitglied ein [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) abgerufenes durch Aufrufen der [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo)Memberfunktion der Klasse `CDaoDatabase`.  
  
 Beziehung und Beziehung Feldobjekte werden nicht von einer MFC-Klasse dargestellt. Stattdessen die DAO-Objekten zugrunde liegenden MFC-Objekte der Klasse [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) enthalten eine Auflistung von Relation-Objekten, die Relations-Auflistung aufgerufen. Jede Relation-Objekt enthält wiederum eine Auflistung von Feldobjekte Beziehung. Jedes Feld Beziehungsobjekt korreliert ein Feld in der primären Tabelle mit einem Feld in der Fremdschlüsseltabelle. Zusammen definieren, die Relation-Feldobjekte eine Gruppe von Feldern in jeder Tabelle, die zusammen die Beziehung definieren. `CDaoDatabase`ermöglicht den Zugriff auf Beziehungsobjekte mit einer `CDaoRelationInfo` Objekt durch Aufrufen der `GetRelationInfo` Memberfunktion. Die `CDaoRelationInfo` Objekt hat dann einen Datenmember `m_pFieldInfos`, verweist auf ein Array von `CDaoRelationFieldInfo` Objekte.  
  
 Rufen Sie die [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) Memberfunktion des enthaltenden `CDaoDatabase` Objekt in dessen Relations-Auflistung ist das Beziehungsobjekt gespeichert Sie von Interesse sind. Klicken Sie dann Zugriff auf die `m_pFieldInfos` Mitglied der [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) Objekt. `CDaoRelationFieldInfo`definiert auch einen `Dump` Memberfunktion in Debug-builds. Sie können `Dump` auf den Inhalt des Basisklassenobjekts auszugeben ein `CDaoRelationFieldInfo` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoRelationInfo-Struktur](../../mfc/reference/cdaorelationinfo-structure.md)
