---
title: Benutzerdatensätze | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- COLUMN_ENTRY_MAP
dev_langs:
- C++
helpviewer_keywords:
- rowsets [C++], accessors
- COLUMN_ENTRY macro
- COLUMN_ENTRY_MAP macro
- user records, OLE DB consumer templates
- OLE DB consumer templates, user records
- CAccessor class, example
- BEGIN_ACCESSOR_MAP macro
- accessors [C++], rowsets
- accessors [C++], static
- BEGIN_ACCESSOR macro, example
ms.assetid: 2de9e5eb-53ce-42b1-80fa-57d46600a80c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8e9549070acf08e566110ea30f4a0259caeca047
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339671"
---
# <a name="user-records"></a>Benutzerdatensätze
Verwenden Sie einen statischen Accessor (d. h. ein Accessor abgeleitet `CAccessor`), der Consumer muss über ein Benutzerdatensatz verfügen. Der Benutzerdatensatz ist eine C++-Klasse, die Datenelemente Handle Eingabe oder Ausgabe enthält. Der ATL-OLE DB-Consumer-Assistent generiert einen Benutzerdatensatz, für den Consumer. Sie können die Benutzer-Datensatz für optionale Aufgaben wie das Behandeln von Kommentaren Methoden hinzufügen.  
  
 Der folgende Code zeigt einen Beispieldatensatz, der Befehle behandelt. Im Benutzerdatensatz repräsentiert BEGIN_COLUMN_MAP ein Datenrowset an den Consumer von einem Anbieter übergeben. BEGIN_PARAM_MAP stellt einen Satz von Parametern dar. Dieses Beispiel verwendet eine [CCommand](../../data/oledb/ccommand-class.md) -Klasse, die Befehlsparameter zu behandeln. Datenmember der Zuordnungseinträge stellen die Offsets in einen zusammenhängenden Block von Arbeitsspeicher für jede Instanz der Klasse. Bei den-Makros entsprechen die-Makros auf der Anbieterseite.  
  
 Weitere Informationen zu den Makros COLUMN_MAP und PARAM_MAP, finden Sie unter [Makros für OLE DB-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).  
  
```cpp  
class CArtists  
{  
public:  
// Data Elements  
   CHAR m_szFirstName[20];  
   CHAR m_szLastName[30];  
   short m_nAge;  
  
// Column binding map  
BEGIN_COLUMN_MAP(CArtists)  
   COLUMN_ENTRY(1, m_szFirstName)  
   COLUMN_ENTRY(2, m_szLastName)  
   COLUMN_ENTRY(3, m_nAge)  
END_COLUMN_MAP()  
  
// Parameter binding map  
BEGIN_PARAM_MAP(CArtists)  
   COLUMN_ENTRY(1, m_nAge)  
END_PARAM_MAP()  
};  
```  
  
## <a name="wizard-generated-user-records"></a>Vom Assistenten generierte Benutzerdatensätze  
 Wenn Sie die ATL-OLE DB-Consumer-Assistenten zum Generieren eines Consumers verwenden, müssen Sie die Auswahl der Verwendung von OLE DB-Vorlagen oder OLE DB-Attribute. Der generierte Code ist in jedem Fall unterschiedlich. Weitere Informationen zu diesem Code finden Sie unter [vom Klassen](../../data/oledb/consumer-wizard-generated-classes.md).  
  
## <a name="user-record-support-for-multiple-accessors"></a>Datensatz Unterstützung für mehrere Accessoren für Benutzer  
 Weitere Informationen zu den Szenarien, in denen Sie mehrere Accessoren für Ereigniseigenschaften verwenden müssen, finden Sie unter [Verwenden mehrerer Zugriffsmethoden für ein Rowset](../../data/oledb/using-multiple-accessors-on-a-rowset.md).  
  
 Im folgenden Beispiel wird des Benutzerdatensatzes geändert, um mehrere Accessoren für das Rowset zu unterstützen. Anstatt BEGIN_COLUMN_MAP und END_COLUMN_MAP, verwendet es [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md) und [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) für jeden Accessor. Die Accessor-Anzahl (Offset von 0 (null)) und gibt an, ob der Accessor einen Autoaccessor ist, gibt das BEGIN_ACCESSOR-Makro an. Autoaccessoren Aufruf `GetData` zum Abrufen von Daten automatisch bei einem Aufruf von [MoveNext](../../data/oledb/crowset-movenext.md). Bei nicht automatische Accessoren müssen Sie explizit die Daten abzurufen. Verwenden Sie automatische, wenn Sie auf ein Feld großer Datenmengen (z. B. ein Bitmap-Bild) binden, die Sie nicht für jeden Datensatz abrufen möchten.  
  
```cpp  
class CMultiArtists  
{  
public:  
// Data Elements  
   CHAR m_szFirstName[20];  
   CHAR m_szLastName[30];  
   short m_nAge;  
  
// Column binding map  
BEGIN_ACCESSOR_MAP(CMultiArtists, 2)  
   BEGIN_ACCESSOR(0, true)    // true specifies an auto accessor  
    COLUMN_ENTRY(1, m_szFirstName)  
    COLUMN_ENTRY(2, m_szLastName)  
   END_ACCESSOR()  
   BEGIN_ACCESSOR(1, false)   // false specifies a manual accessor  
    COLUMN_ENTRY(3, m_nAge)  
   END_ACCESSOR()  
END_ACCESSOR_MAP()  
};  
```  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)