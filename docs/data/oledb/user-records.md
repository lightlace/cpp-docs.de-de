---
title: Benutzerdatensätze | Microsoft Docs
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
ms.openlocfilehash: aea6b4b2ebb1a02e4ef669b437fbe7eb30937f9b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="user-records"></a>Benutzerdatensätze
Um einen statischen Accessor verwenden (d. h. ein Accessor abgeleitet **CAccessor)**, der Consumer muss einen Benutzerdatensatz haben. Der Benutzerdatensatz ist eine C++-Klasse, die Datenelemente Handle Eingabe oder Ausgabe enthält. ATL-OLE DB-Consumer-Assistent generiert einen Benutzerdatensatz für den Consumer. Sie können Methoden Benutzerdatensatzes für optionale Aufgaben wie das Behandeln von Kommentaren hinzufügen.  
  
 Der folgende Code zeigt einen Beispieldatensatz, der Befehle behandelt. In der Benutzerdatensatz `BEGIN_COLUMN_MAP` stellt ein Datenrowset, das an den Consumer von einem Anbieter übergeben. `BEGIN_PARAM_MAP` Stellt einen Satz von Befehlsparametern. Dieses Beispiel verwendet eine [CCommand](../../data/oledb/ccommand-class.md) Klasse, die Befehlsparameter zu behandeln. Die Datenelemente in der Zuordnungseinträge stellen Offsets in einen zusammenhängenden Block von Arbeitsspeicher für jede Instanz der Klasse dar. Die `COLUMN_ENTRY` Makros entsprechen den `PROVIDER_COLUMN_ENTRY` Makros auf der Anbieterseite.  
  
 Weitere Informationen zu den **COLUMN_MAP** und **PARAM_MAP** Makros finden Sie unter [Makros für OLE DB-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).  
  
```  
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
  
## <a name="wizard-generated-user-records"></a>Vom Assistenten generierten Benutzerdatensätze  
 Wenn Sie den ATL OLE DB-Consumer-Assistenten zum Generieren eines Consumers verwenden, müssen Sie die Auswahl der Verwendung von OLE DB-Vorlagen oder OLE DB-Attribute. Der generierte Code unterscheidet sich in jedem Fall. Weitere Informationen zu diesem Code finden Sie unter [vom Klassen](../../data/oledb/consumer-wizard-generated-classes.md).  
  
## <a name="user-record-support-for-multiple-accessors"></a>Datensatz Benutzersupport für mehrere Accessoren  
 Ausführliche Informationen zu den Szenarien, in denen Sie mehrere Accessoren für Ereigniseigenschaften verwenden müssen, finden Sie unter [Verwenden mehrerer Accessoren für ein Rowset](../../data/oledb/using-multiple-accessors-on-a-rowset.md).  
  
 Das folgende Beispiel zeigt die Benutzerdatensatz geändert, um mehrere Accessoren für das Rowset zu unterstützen. Anstelle von `BEGIN_COLUMN_MAP` und `END_COLUMN_MAP`, verwendet er [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md) und [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) für jeden Accessor. Die `BEGIN_ACCESSOR` Makro gibt die Anzahl der Accessor (Offset von 0 (null)) und gibt an, ob der Accessor ein Autoaccessor ist. Autoaccessoren Aufruf `GetData` zum Abrufen von Daten automatisch bei einem Aufruf von [MoveNext](../../data/oledb/crowset-movenext.md). Bei nicht automatische Accessoren müssen Sie explizit die Daten abzurufen. Verwenden Sie automatische, wenn Sie eine große Datenfeld (z. B. ein Bitmapbild), die nicht besser binden abzurufenden für jeden Datensatz.  
  
```  
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