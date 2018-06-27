---
title: CDaoRelationInfo-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoRelationInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationInfo structure [MFC]
ms.assetid: 92dda090-fe72-4090-84ec-429498a48aad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a49bdfb00c3f2ceba424af7bfdfa652cacec929e
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951291"
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
 *m_strName*  
 Eindeutig benennt die Relation-Objekt. Weitere Informationen finden Sie im Thema "Name-Eigenschaft" DAO-Hilfe.  
  
 *m_strTable*  
 Namen die primäre Tabelle in der Beziehung an.  
  
 *m_strForeignTable*  
 Namen die fremde Tabelle in der Beziehung an. Fremdtabelle ist eine Tabelle verwendet, um den Fremdschlüssel enthalten. Im Allgemeinen verwenden Sie eine Fremdtabelle hergestellt oder die referenzielle Integrität erzwingen. Die fremde Tabelle ist in der Regel auf der n-Seite einer 1: n-Beziehung. Beispiele für fremde Tabellen sind Tabellen, die Codes für den US-amerikanischen Bundesstaaten oder kanadischen Provinzen oder kundenbestellungen enthalten.  
  
 *m_lAttributes*  
 Enthält Informationen zu den Beziehungstyp. Der Wert dieses Elements kann eine der folgenden sein:  
  
- **DbRelationUnique** Beziehung 1: 1 ist.  
  
- **DbRelationDontEnforce** Beziehung wird nicht erzwungen (keine referenzielle Integrität).  
  
- **DbRelationInherited** Beziehung in einer-Datenbank, die die beiden angefügten Tabellen enthält.  
  
- **DbRelationLeft** die Beziehung wird ein Linker Join. Eine linke äußere Verknüpfung enthält alle Datensätze aus der ersten (linken) der beiden Tabellen, selbst wenn keine übereinstimmenden Werte für Datensätze in der zweiten (rechten) Tabelle vorhanden sind.  
  
- **DbRelationRight** die Beziehung ist eine richtige Join. Ein rechter äußerer Join schließt alle Datensätze aus der zweiten (rechten) von zwei Tabellen, selbst wenn keine übereinstimmenden Werte für Datensätze in der ersten (linken) Tabelle vorhanden sind.  
  
- **DbRelationUpdateCascade** Updates kaskadiert werden.  
  
- **DbRelationDeleteCascade** Löschvorgänge werden weitergegeben.  
  
 *m_pFieldInfos*  
 Ein Zeiger auf ein Array von [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) Strukturen. Das Array enthält ein Objekt für jedes Feld in der Beziehung. Die *M_nFields* Datenmember gibt die Anzahl der Elemente des Arrays.  
  
 *m_nFields*  
 Die Anzahl der `CDaoRelationFieldInfo` Objekte in der *M_pFieldInfos* -Datenmember.  
  
## <a name="remarks"></a>Hinweise  
 Die Verweise auf die primären und sekundären Datenbank, die oben genannten anzugeben, wie die Informationen zurückgegeben werden, durch die [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) Memberfunktion in Klasse `CDaoDatabase`.  
  
 Relation-Objekte werden nicht von einer MFC-Klasse dargestellt. Stattdessen, die DAO-Objekt, das zugrunde liegende ein MFC-Objekt von der `CDaoDatabase` -Klasse verwaltet eine Auflistung von Objekten Beziehung: `CDaoDatabase` stellt Memberfunktionen einige einzelne Elemente Beziehung Informationen, oder wenn Sie Zugriff auf Sie zugreifen können alle auf einmal mit einem `CDaoRelationInfo` Objekt durch Aufrufen der `GetRelationInfo` Memberfunktion Rand des enthaltenden Datenbankobjekts.  
  
 Informationen, die abgerufen, indem die [CDaoDatabase::GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) Memberfunktion befindet sich in einer `CDaoRelationInfo` Struktur. `CDaoRelationInfo` definiert auch einen `Dump` Memberfunktion in Debug-builds. Sie können `Dump` auf den Inhalt des Basisklassenobjekts auszugeben ein `CDaoRelationInfo` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDaoRelationFieldInfo-Struktur](../../mfc/reference/cdaorelationfieldinfo-structure.md)
