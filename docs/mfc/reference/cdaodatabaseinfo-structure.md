---
title: CDaoDatabaseInfo-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoDatabaseInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoDatabaseInfo structure [MFC]
- DAO (Data Access Objects), Databases collection
ms.assetid: 68e9e0da-8382-4fc6-8115-1b1519392ddb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 085d0e525cb00c9fffb3698080194da92a6dbb8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdaodatabaseinfo-structure"></a>CDaoDatabaseInfo-Struktur
Die `CDaoDatabaseInfo` Struktur enthält Informationen über ein Datenbankobjekt für Datenzugriffsobjekte (DAO) definiert.  
  
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
 Eindeutig benennt das Datenbankobjekt. Um diese Eigenschaft direkt abzurufen, rufen Sie [CDaoDatabase::GetName](../../mfc/reference/cdaodatabase-class.md#getname). Details finden Sie im Thema "Name-Eigenschaft" DAO-Hilfe.  
  
 `m_bUpdatable`  
 Gibt an, ob Änderungen an der Datenbank vorgenommen werden können. Um diese Eigenschaft direkt abzurufen, rufen Sie [CDaoDatabase::CanUpdate](../../mfc/reference/cdaodatabase-class.md#canupdate). Details finden Sie im Thema "Aktualisierbare Property" in der DAO-Hilfe.  
  
 *m_bTransactions*  
 Gibt an, ob eine Datenquelle Transaktionen unterstützt, die Aufzeichnung einer Reihe von Änderungen, die später ein Rollback ausgeführt werden können (abgebrochen) oder ein Commit ausgeführt wurde (gespeichert). Wenn eine Datenbank auf dem Microsoft Jet-Datenbankmodul basiert, die Transaktionen-Eigenschaft ungleich NULL ist, und Transaktionen können verwendet werden. Datenbankmodule unterstützen möglicherweise keine Transaktionen. Um diese Eigenschaft direkt abzurufen, rufen Sie [CDaoDatabase::CanTransact](../../mfc/reference/cdaodatabase-class.md#cantransact). Details finden Sie im Thema "Transaktionen Property" in der DAO-Hilfe.  
  
 *m_strVersion*  
 Gibt die Version der Microsoft Jet-Datenbankmodul. Um den Wert dieser Eigenschaft direkt abzurufen, rufen Sie des Datenbankobjekts [GetVersion](../../mfc/reference/cdaodatabase-class.md#getversion) Memberfunktion. Details finden Sie im Thema "Version-Eigenschaft" DAO-Hilfe.  
  
 `m_lCollatingOrder`  
 Gibt die Sequenz der Sortierreihenfolge im Text für den Zeichenfolgenvergleich oder sortieren. Mögliche Werte:  
  
- **DbSortGeneral** verwenden Sie die allgemeine Sortierreihenfolge (Englisch, Französisch, Deutsch, Portugiesisch, Italienisch und Modern Spanisch).  
  
- **DbSortArabic** die arabische Sortierreihenfolge verwenden.  
  
- **DbSortCyrillic** verwenden Sie die Sortierreihenfolge für Russisch.  
  
- **DbSortCzech** die Tschechische Sortierreihenfolge verwenden.  
  
- **DbSortDutch** die Niederländisch Sortierreihenfolge verwenden.  
  
- **DbSortGreek** die griechischen Sortierreihenfolge verwenden.  
  
- **DbSortHebrew** verwenden die hebräische Sortierreihenfolge.  
  
- **DbSortHungarian** Ungarisch Sortierreihenfolge verwenden.  
  
- **DbSortIcelandic** die isländische Sortierreihenfolge verwenden.  
  
- **DbSortNorwdan** Norwegisch oder Dänisch Sortierreihenfolge verwenden.  
  
- **DbSortPDXIntl** verwenden Sie die Sortierreihenfolge Paradox International.  
  
- **DbSortPDXNor** Paradox Norwegisch oder Dänisch Sortierreihenfolge verwenden.  
  
- **DbSortPDXSwe** Paradox Schwedisch oder Finnisch Sortierreihenfolge verwenden.  
  
- **DbSortPolish** die Polnische Sortierreihenfolge verwenden.  
  
- **DbSortSpanish** die spanische Sortierreihenfolge verwenden.  
  
- **DbSortSwedFin** Schwedisch oder Finnisch Sortierreihenfolge verwenden.  
  
- **DbSortTurkish** verwenden Sie die Sortierung der türkischen Sortierreihenfolge.  
  
- **DbSortUndefined** Sortierreihenfolge ist nicht definiert oder unbekannt.  
  
 Weitere Informationen finden Sie im Thema "Anpassen von Windows-Registrierung Einstellungen für den Datenzugriff" DAO-Hilfe.  
  
 *m_nQueryTimeout*  
 Die Anzahl der Sekunden, die das Microsoft Jet-Datenbankmodul, bevor ein Timeout-Fehler wartet tritt auf, wenn eine Abfrage auf eine ODBC-Datenbank ausgeführt wird. Der Standard-Timeoutwert ist 60 Sekunden. Wenn QueryTimeout auf 0 festgelegt ist, tritt kein Timeout. Dies kann dazu führen, dass das Programm nicht mehr reagiert. Um den Wert dieser Eigenschaft direkt abzurufen, rufen Sie des Datenbankobjekts [GetQueryTimeout](../../mfc/reference/cdaodatabase-class.md#getquerytimeout) Memberfunktion. Details finden Sie im Thema "QueryTimeout-Eigenschaft" DAO-Hilfe.  
  
 `m_strConnect`  
 Enthält Informationen zur Quelle des eine geöffnete Datenbank. Informationen zu Verbindungszeichenfolgen und Informationen direkt das Abrufen des Werts dieser Eigenschaft finden Sie unter der [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) Memberfunktion. Weitere Informationen finden Sie im Thema "Verbinden der Eigenschaft" DAO-Hilfe.  
  
## <a name="remarks"></a>Hinweise  
 Die Datenbank ist ein DAO-Objekt, das zugrunde liegende ein MFC-Objekt der Klasse [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md). Die Verweise auf die primäre, sekundäre Datenbank und alle oben anzugeben, wie die Informationen zurückgegeben werden, durch die [CDaoWorkspace::GetDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) Memberfunktion.  
  
 Informationen, die abgerufen, indem die [CDaoWorkspace::GetDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) Memberfunktion befindet sich in einer `CDaoDatabaseInfo` Struktur. Rufen Sie `GetDatabaseInfo` für die `CDaoWorkspace` -Objekt in die Auflistung, deren Datenbanken das Datenbankobjekt gespeichert ist. `CDaoDatabaseInfo`definiert auch einen `Dump` Memberfunktion in Debug-builds. Sie können `Dump` auf den Inhalt des Basisklassenobjekts auszugeben ein `CDaoDatabaseInfo` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoWorkspace-Klasse](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoDatabase-Klasse](../../mfc/reference/cdaodatabase-class.md)
