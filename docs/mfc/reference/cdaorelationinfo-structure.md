---
title: CDaoRelationInfo-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoRelationInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationInfo structure
ms.assetid: 92dda090-fe72-4090-84ec-429498a48aad
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 7c3a8195aed2c3b3fe5c78c98afcc6e72a83cc21
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cdaorelationinfo-structure"></a>CDaoRelationInfo-Struktur
Die `CDaoRelationInfo` Struktur enthält Informationen über eine Beziehung zwischen zwei Tabellen in Feldern definiert eine [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CDaoRelationInfo  
{  
    CDaoRelationInfo();
*// Constructor  
    CString m_strName;      // Primary  
    CString m_strTable;     // Primary  
    CString m_strForeignTable;              // Primary  
    long m_lAttributes;     // Secondary  
    CDaoRelationFieldInfo* m_pFieldInfos;   // Secondary  
    short m_nFields;        // Secondary *// Below the // Implementation comment: *// Destructor, not otherwise documented  
};  
```  
  
#### <a name="parameters"></a>Parameter  
 `m_strName`  
 Die Relation-Objekt bezeichnet eindeutig. Weitere Informationen finden Sie im Thema "Name-Eigenschaft" in der DAO-Hilfe.  
  
 *m_strTable*  
 Den Namen der primären Tabelle in der Beziehung.  
  
 *m_strForeignTable*  
 Den Namen der Fremdschlüsseltabelle in der Beziehung. Fremdtabelle ist eine Tabelle mit dem Fremdschlüssel enthält. Im Allgemeinen verwenden Sie eine Fremdtabelle einrichten bzw. die referenzielle Integrität erzwingen. Die Fremdtabelle befindet sich normalerweise auf der n-Seite einer&1;: n-Beziehung. Fremde Tabellen gehören Tabellen, für die American Zustände oder kanadischen Provinzen oder Aufträge des Kunden enthält.  
  
 `m_lAttributes`  
 Enthält Informationen über den Typ der Beziehung. Der Wert dieses Elements kann eines der folgenden sein:  
  
- **DbRelationUnique** Beziehung&1;:&1; ist.  
  
- **DbRelationDontEnforce** Beziehung wird nicht erzwungen (keine referentielle Integrität).  
  
- **DbRelationInherited** Beziehung in einer-Datenbank, die zwei angefügten Tabellen enthält.  
  
- **DbRelationLeft** der Beziehung ist eine linke Verknüpfung. Eine linke äußere Verknüpfung enthält alle Datensätze aus der ersten (linken) der beiden Tabellen, selbst wenn keine übereinstimmenden Werte für Datensätze in der zweiten (rechten) Tabelle vorhanden sind.  
  
- **DbRelationRight** beruht auf einer rechten Verknüpfung. Eine rechte äußere Verknüpfung enthält alle Datensätze aus der zweiten (rechten) von zwei Tabellen, selbst wenn keine übereinstimmenden Werte für Datensätze in der ersten (linken) Tabelle vorhanden sind.  
  
- **DbRelationUpdateCascade** Updates kaskadieren.  
  
- **DbRelationDeleteCascade** Löschvorgänge werden weitergegeben.  
  
 `m_pFieldInfos`  
 Ein Zeiger auf ein Array von [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) Strukturen. Das Array enthält ein Objekt für jedes Feld in der Beziehung. Der `m_nFields` -Datenmember gibt die Anzahl der Elemente des Arrays.  
  
 `m_nFields`  
 Die Anzahl der `CDaoRelationFieldInfo` Objekte in der `m_pFieldInfos` -Datenmember.  
  
## <a name="remarks"></a>Hinweise  
 Die Verweise auf die primären und sekundären oben anzugeben, wie die Informationen zurückgegeben werden, durch die [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) Memberfunktion Klasse `CDaoDatabase`.  
  
 Beziehung zwischen Objekten werden nicht von einer MFC-Klasse dargestellt. Stattdessen, das zugrunde liegende ein MFC-Objekt des DAO-Objekt die `CDaoDatabase` Klasse verwaltet eine Auflistung von Beziehungsobjekte: `CDaoDatabase` stellt Memberfunktionen den Zugriff auf einige einzelne Elemente der Beziehung Informationen, oder Sie können darauf zugreifen, gleichzeitig mit einer `CDaoRelationInfo` -Objekt durch Aufrufen der `GetRelationInfo` -Memberfunktion des enthaltenden Objekts der Datenbank.  
  
 Informationen abgerufen werden, indem Sie die [CDaoDatabase::GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) -Memberfunktion befindet sich in einer `CDaoRelationInfo` Struktur. `CDaoRelationInfo`definiert auch eine `Dump` Memberfunktion im Debugmodus erstellt. Sie können `Dump` auf den Inhalt des Basisklassenobjekts auszugeben ein `CDaoRelationInfo` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDaoRelationFieldInfo-Struktur](../../mfc/reference/cdaorelationfieldinfo-structure.md)

