---
title: CDaoDatabaseInfo-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoDatabaseInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoDatabaseInfo structure
- DAO (Data Access Objects), Databases collection
ms.assetid: 68e9e0da-8382-4fc6-8115-1b1519392ddb
caps.latest.revision: 14
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
ms.openlocfilehash: ed7eb8612099daf59cb7e722434102095122f3d1
ms.lasthandoff: 02/24/2017

---
# <a name="cdaodatabaseinfo-structure"></a>CDaoDatabaseInfo-Struktur
Die `CDaoDatabaseInfo` Struktur enthält Informationen zu einem Datenbankobjekt für Datenzugriffsobjekte (DAO) definiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CDaoDatabaseInfo  
{  
    CString m_strName;       // Primary  
    BOOL m_bUpdatable;       // Primary  
    BOOL m_bTransactions;    // Primary  
    CString m_strVersion;    // Secondary  
    long m_lCollatingOrder;  // Secondary  
    short m_nQueryTimeout;   // Secondary  
    CString m_strConnect;    // All  
};  
```  
  
#### <a name="parameters"></a>Parameter  
 `m_strName`  
 Das Database-Objekt bezeichnet eindeutig. Um diese Eigenschaft direkt abzurufen, rufen Sie [CDaoDatabase::GetName](../../mfc/reference/cdaodatabase-class.md#getname). Details finden Sie im Thema "Name-Eigenschaft" in der DAO-Hilfe.  
  
 `m_bUpdatable`  
 Gibt an, ob die Datenbank geändert werden kann. Um diese Eigenschaft direkt abzurufen, rufen Sie [CDaoDatabase::CanUpdate](../../mfc/reference/cdaodatabase-class.md#canupdate). Details finden Sie unter "Aktualisierbare Property" in der DAO-Hilfe.  
  
 *m_bTransactions*  
 Gibt an, ob eine Datenquelle Transaktionen unterstützt, die Aufzeichnung einer Reihe von Änderungen, die später rückgängig gemacht werden kann (abgebrochen) oder per Commit (gespeichert). Wenn eine Datenbank auf dem Microsoft Jet-Datenbankmodul basiert, die Transaktionen-Eigenschaft ungleich NULL ist, und Transaktionen können verwendet werden. Datenbankmodule unterstützen möglicherweise keine Transaktionen. Um diese Eigenschaft direkt abzurufen, rufen Sie [CDaoDatabase::CanTransact](../../mfc/reference/cdaodatabase-class.md#cantransact). Details finden Sie im Thema "Transaktionen Property" in der DAO-Hilfe.  
  
 *m_strVersion*  
 Gibt die Version des Microsoft Jet-Datenbankmoduls. Um den Wert dieser Eigenschaft direkt abzurufen, rufen Sie des Datenbankobjekt [GetVersion](../../mfc/reference/cdaodatabase-class.md#getversion) Member-Funktion. Details finden Sie unter dem Thema "Version-Eigenschaft" in der DAO-Hilfe.  
  
 `m_lCollatingOrder`  
 Gibt die Sequenz der Sortierreihenfolge im Text für den Zeichenfolgenvergleich oder die Sortierung an. Mögliche Werte:  
  
- **DbSortGeneral** verwenden Sie die allgemeine Sortierreihenfolge (Englisch, Französisch, Deutsch, Portugiesisch, Italienisch und modernes Spanisch).  
  
- **DbSortArabic** die arabische Sortierreihenfolge verwenden.  
  
- **DbSortCyrillic** verwenden Sie die Sortierreihenfolge für Russisch.  
  
- **DbSortCzech** die Tschechische Sortierreihenfolge verwenden.  
  
- **DbSortDutch** die niederländische Sortierreihenfolge verwenden.  
  
- **DbSortGreek** der griechischen Sortierreihenfolge verwenden.  
  
- **DbSortHebrew** die hebräische Sortierreihenfolge verwenden.  
  
- **DbSortHungarian** Ungarisch Sortierreihenfolge verwenden.  
  
- **DbSortIcelandic** die isländische Sortierreihenfolge verwenden.  
  
- **DbSortNorwdan** Norwegisch oder Dänisch Sortierreihenfolge verwenden.  
  
- **DbSortPDXIntl** verwenden Sie die Sortierreihenfolge für Paradox International.  
  
- **DbSortPDXNor** Paradox Norwegisch oder Dänisch Sortierreihenfolge verwenden.  
  
- **DbSortPDXSwe** Paradox Schwedisch oder Finnisch Sortierreihenfolge verwenden.  
  
- **DbSortPolish** Polnisch Sortierreihenfolge verwenden.  
  
- **DbSortSpanish** die spanische Sortierreihenfolge verwenden.  
  
- **DbSortSwedFin** Schwedisch oder Finnisch Sortierreihenfolge verwenden.  
  
- **DbSortTurkish** der türkischen Sortierreihenfolge verwenden.  
  
- **DbSortUndefined** die Sortierreihenfolge ist nicht definiert oder unbekannt.  
  
 Weitere Informationen finden Sie im Thema "Anpassen von Windows-Registrierung Einstellungen für den Datenzugriff" DAO-Hilfe.  
  
 *m_nQueryTimeout*  
 Die Anzahl der Sekunden an, die das Microsoft Jet-Datenbankmodul, bevor ein Timeout-Fehler wartet tritt auf, wenn eine Abfrage auf eine ODBC-Datenbank ausgeführt wird. Der Standard-Timeoutwert beträgt 60 Sekunden. Wenn QueryTimeout auf 0 festgelegt ist, tritt kein Timeout. Dadurch kann das Programm nicht mehr reagiert. Um den Wert dieser Eigenschaft direkt abzurufen, rufen Sie des Datenbankobjekt [GetQueryTimeout](../../mfc/reference/cdaodatabase-class.md#getquerytimeout) Member-Funktion. Details finden Sie unter dem Thema "QueryTimeout-Eigenschaft" in der DAO-Hilfe.  
  
 `m_strConnect`  
 Enthält Informationen über die Quelle einer geöffneten Datenbank. Weitere Informationen zu Verbindungszeichenfolgen und Informationen direkt das Abrufen des Werts dieser Eigenschaft finden Sie unter der [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) Member-Funktion. Weitere Informationen finden Sie unter dem Thema "Connect-Eigenschaft" DAO-Hilfe.  
  
## <a name="remarks"></a>Hinweise  
 Die Datenbank ist ein DAO-Objekt, das zugrunde liegende ein MFC-Objekt der Klasse [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md). Die Verweise auf die primären, sekundären und alle oben anzugeben, wie die Informationen zurückgegeben werden, durch die [CDaoWorkspace::GetDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) Member-Funktion.  
  
 Informationen abgerufen werden, indem Sie die [CDaoWorkspace::GetDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) -Memberfunktion befindet sich in einer `CDaoDatabaseInfo` Struktur. Rufen Sie `GetDatabaseInfo` für die `CDaoWorkspace` -Objekt in die Auflistung, deren Datenbanken das Datenbankobjekt, das gespeichert wird. `CDaoDatabaseInfo`definiert auch eine `Dump` Memberfunktion im Debugmodus erstellt. Sie können `Dump` auf den Inhalt des Basisklassenobjekts auszugeben ein `CDaoDatabaseInfo` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoWorkspace-Klasse](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoDatabase-Klasse](../../mfc/reference/cdaodatabase-class.md)

